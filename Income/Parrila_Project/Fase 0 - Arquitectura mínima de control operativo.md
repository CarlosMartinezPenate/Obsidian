
1. Reconstrucción de ingresos reales 8 semanas.
    
    - Ventas netas por día.
    - Separación efectivo / QR / tarjeta.
    - Identificación de inconsistencias.
    
2. Estimación preliminar de food cost real.
    
    - Total compras proteína / total ventas.
    
3. Detección de fugas.
    - Contaminacion de Caja
    - Descuentos sin responsable.
    - Eventos “salón” sin proporción clara.

4. Diagnóstico en 5 páginas.
    
    - Qué se puede medir.
    - Qué no.
    - Qué está generando riesgo.
    - Qué acción concreta tomar en 90 días.

## **1) Qué significa “base de datos retrógrada”**

  

Un repositorio (Sheets o DB) que reconstruye el historial con:

- **Ventas** (ideal: por ítem; si no, por ticket/turno/día)
    
- **Pagos** (efectivo/QR/tarjeta) para conciliación
    
- **Compras** (especialmente carne) con unidad, peso y precio
    
- **Merma + inventario** (aunque sea semanal)
    
- **Catálogos** (mapeos: nombres sucios → estándar)
    

  

Objetivo: que puedas calcular KPIs sin esperar a que el software esté instalado.

---

## **2) Modelo mínimo (tablas/hojas) para un solo local**

  

Si lo haces en Google Sheets, esto son pestañas; si lo haces en DB, son tablas.

  

### **A)** 

### **dim_item**

###  **(catálogo estándar)**

- item_id (código)
    
- item_name_std (nombre estándar)
    
- categoria (carne / guarnición / bebida / postre / etc.)
    
- canal_aplica (opcional)
    
- active (sí/no)
    

  

### **B)** 

### **map_item_alias**

###  **(traducción de nombres sucios)**

- alias_raw (como aparece en comanda/POS)
    
- item_id
    
- nota (ej: “picaña” = “punta de S”)
    

  

### **C)** 

### **fact_sales_ticket**

###  **(ventas por ticket)**

- ticket_id (si existe; si no, date + turno + correlativo)
    
- date
    
- time (si existe)
    
- turno (almuerzo/cena)
    
- canal (salón/delivery/takeaway)
    
- subtotal
    
- descuento_total
    
- impuesto (si existe)
    
- total
    
- status (ok/anulado)
    

  

### **D)** 

### **fact_sales_line**

###  **(ventas por ítem)** 

### **si se puede**

- ticket_id
    
- line_id
    
- alias_raw
    
- item_id (después del mapeo)
    
- qty
    
- precio_unit
    
- importe
    

  

> Si no hay líneas, haces KPIs “v0” por ticket/día y dejas ingeniería de menú para cuando haya datos.

  

### **E)** 

### **fact_payments**

###  **(medios de pago)**

- date
    
- turno
    
- medio_pago (efectivo/QR/tarjeta/transfer/mixto)
    
- monto_reportado_sistema
    
- monto_real (caja/banco)
    
- diferencia (calculado)
    
- evidencia (foto cierre, extracto)
    

  

### **F)** 

### **fact_purchases**

###  **(compras; clave para carne)**

- purchase_id
    
- date
    
- proveedor
    
- item_compra_raw (corte como viene)
    
- item_compra_std (normalizado)
    
- unidad (kg/lb/pieza)
    
- cantidad
    
- peso_kg (convertido)
    
- precio_unit (por kg si aplica)
    
- total
    
- con_factura (sí/no)
    
- evidencia (foto/pdf)
    

  

### **G)** 

### **fact_waste**

###  **(merma / cortesías / staff)**

- date
    
- tipo (merma/cortesía/staff)
    
- item_std
    
- cantidad (ideal kg o unidades)
    
- costo_estimado (si no hay exacto)
    
- motivo
    

  

### **H)** 

### **fact_inventory_weekly**

###  **(inventario semanal mínimo)**

- week_start
    
- item_std
    
- stock_inicial
    
- compras_semana
    
- stock_final
    
- unidad / kg
    

---

## **3) Flujo de limpieza (retro) – sin volverte loco**

  

### **Paso 0: define ventana retro**

- Recomendación: **últimas 8 semanas** (56 días).
    
    Suficiente para ver patrones por día/turno y detectar fugas.
    

  

### **Paso 1: “ingest” (copiar tal cual, sin corregir)**

- Crea hojas “RAW”: RAW_ventas, RAW_pagos, RAW_compras, RAW_merma.
    
- Regla: **nunca edites los RAW**. Todo arreglo va en “CLEAN”.
    

  

### **Paso 2: normalización de claves**

- Estándar de fechas y turnos.
    
- Si no hay ticket_id: crea ticket_key = YYYYMMDD + turno + nro.
    

  

### **Paso 3: limpieza de nombres (catálogo)**

- Genera lista única de productos vendidos (o de comandas).
    
- Construye map_item_alias y regla:
    
    - Si alias_raw no mapea → queda como **“UNMAPPED”** y se reporta.
        
    

  

### **Paso 4: unidades y conversiones (compras)**

- Estándar: **todo a kg**.
    
- Tabla map_units (lb→kg, caja→kg promedio si aplica).
    
- Si hay facturas sin desglose: registra como “compra agregada” con nota (no inventar detalle).
    

  

### **Paso 5: deduplicación**

- Compras: dup típico = misma factura/foto cargada dos veces.
    
- Regla simple: mismo proveedor + fecha + total + evidencia ⇒ revisar.
    

  

### **Paso 6: conciliación de caja/pagos**

- Comparar:
    
    - ventas_totales_sistema vs (efectivo + QR + tarjeta reales)
        
    
- Diferencia se guarda como dato, **no se “arregla”**.
    

  

### **Paso 7: dataset “CLEAN”**

- Export de hojas “CLEAN” que alimentan KPIs.
    

---

## **4) KPIs que sí puedes sacar con una base retro (aunque falten cosas)**

  

### **Nivel diario/turno (rápidos y vendibles)**

- Ventas totales por día/turno/canal
    
- Ticket promedio (si hay tickets)
    
- Mix de pagos (% efectivo vs QR)
    
- Diferencia de caja (monto y %)
    
- Compras de carne por semana (monto, precio/kg promedio)
    
- Merma (si existe) por semana
    

  

### **Nivel margen (cuando tengas compras + algo de inventario/merma)**

- Food Cost % **observado** (compras carne / ventas) por semana
    
    > No es perfecto sin inventario, pero sirve como señal temprana.
    
- Costo promedio por kg por proveedor/corte
    
- Pérdidas por mermas/cortesías (estimado) si registran
    

  

### **Ingeniería de menú (solo si hay ventas por ítem)**

- Ventas y contribución estimada por ítem
    
- Top items por volumen vs por margen estimado
    

---

## **5) Entregable “vendible” (lo que tú le cobras)**

  

Lo que normalmente vendes como paquete:

1. Base retro limpia (Sheets/DB) + diccionarios (alias/unidades)
    
2. Reporte de calidad (qué falta, qué es confiable)
    
3. Tablero v0 (8–12 KPIs) + 3 hallazgos accionables
    

---

## **6) Para empezar hoy (sin preguntar más)**

  

Si no tienes todavía sus datos digitales, tu “plan de ataque” retro es:

- **Ventas:** fotos o reportes de cierres diarios (X/Z) de 8 semanas
    
- **Pagos QR:** capturas/descargas del banco por 8 semanas
    
- **Compras carne:** fotos de facturas/notas/WhatsApps por 8 semanas
    
- **Inventario:** 1 conteo semanal (aunque sea aproximado) de carne/alcohol desde hoy en adelante
    

  

Con eso ya montas un v0 decente.