# **1) Especificación de Data Wrangling y Estructura (antes de tocar Sheets)**

  

## **1.1 Decisiones de diseño (las 12 preguntas que definen todo)**

  

### **A) Granularidad y llaves**

1. **¿Vamos a registrar ventas a nivel Ticket o Ítem de línea?**
    
    - **Recomendación**: _Ítem de línea_ si existe POS con exportación; si no, **Ticket + top ítems** por muestreo los primeros 30 días.
        
    - Impacto: sin ítem de línea no hay ingeniería de menú sólida ni CM por plato.
        
    
2. **¿Qué identificador único existe para cada venta?**
    
    - POS: ticket_id + fecha_hora
        
    - Manual: fecha + turno + correlativo_caja (lo creas en el formulario)
        
    
3. **¿Qué es un “turno” en este negocio?**
    
    - Definir: ALMUERZO (12–16) / CENA (19–23) o lo que aplique.
        
    - Sin esto, no existe CM/h ni productividad.
        
    
4. **¿Qué moneda y unidad vamos a usar?**
    
    - Moneda: BOB (bolivianos)
        
    - Unidades: **gramos** para recetas, **kilogramos** para compras, **porciones** para ventas.
        
    - Regla: todo se convierte a una unidad estándar al entrar al sistema.
        
    

  

### **B) Definiciones de venta e impuestos (modelo simple “operable”)**

5. **¿La “venta” que captura caja incluye IVA/IT o es el total cobrado?**
    
    - En campo, normalmente capturas **total cobrado**.
        
    - Definimos columnas separadas: venta_total_cobrada y luego una venta_neta_estimada (por factor).
        
    
6. **¿Qué régimen tributario aplica al restaurante y qué tan consistente es la facturación?**
    
    - No lo resolvemos “contable perfecto”, pero sí definimos **una regla operacional**:
        
    - Opción A (ideal): POS separa impuestos → usas neto real.
        
    - Opción B (realista): aplicas **factor de neteo** configurable y lo documentas.
        
    
7. **¿Cómo trataremos ventas sin factura / efectivo “informal”?**
    
    - Se registran igual como venta (para gestión).
        
    - Se marca documento_fiscal = sí/no para separar análisis.
        
    

  

### **C) Tratamiento de nulos, errores y datos sucios**

8. **¿Qué hacemos con comandas ilegibles / ítems no registrados?**
    
    - Regla: nunca dejar “vacío”.
        
    - Usar categorías: ITEM_DESCONOCIDO, CORTES_VARIOS, BEBIDA_VARIAS con monto asociado.
        
    - Luego, limpieza semanal con el encargado.
        
    
9. **¿Qué hacemos con facturas de carne sin desglose por corte?**
    
    - Dos caminos:
        
    - (1) Registrar como CARNE_SIN_DESGLOSE y **no costear por corte** esa compra (solo food cost global).
        
    - (2) Obligar a proveedor: si no desglosa, se pierde control → política de compras.
        
    
10. **¿Cómo detectamos duplicidad (misma factura cargada dos veces)?**
    

  

- Definir un “fingerprint” único de compra:
    
- proveedor + nro_factura + fecha + total + foto_hash
    
- Si no hay nro_factura, usar proveedor + fecha + total + revisión manual.
    

  

11. **¿Qué hacemos si el proveedor entrega en libras y la receta en gramos?**
    

  

- Convertidor fijo:
    
- 1 lb = 453.592 g
    
- El sistema convierte automáticamente a **kg** (compras) y **g** (recetas).
    

  

12. **Frecuencia de actualización realista (para no quemar al personal)**
    

  

- **Caja**: diario (obligatorio, 60 segundos)
    
- **Recepción carne**: cada compra (obligatorio, 90 segundos)
    
- **Merma**: diario por turno (60 segundos, con categorías)
    
- **Limpieza**: semanal (30–60 min contigo o encargado)
    

---

## **1.2 Normalización de nombres (cortes y menú)**

  

**Problema**: “Picaña” vs “Punta de S.” vs “Tapa de cuadril”.

  

### **Reglas**

- Se crea una tabla maestra **Dim_Corte** con:
    
    - corte_id (interno)
        
    - corte_estandar
        
    - sinonimos (lista)
        
    - categoria (premium/medio/económico)
        
    - rendimiento_objetivo (%)
        
    
- Al capturar compra, **NO se escribe libre**: se elige de lista desplegable (corte_estandar).
    
- Si llega un nombre nuevo → se registra como “NUEVO_CORTE” y tú lo mapeas semanalmente.
    

---

# **2) Kit de Captura “Guerrilla” (3 Google Forms exactos)**

  

> Consejo operativo: cada formulario debe poder completarse en menos de 90 segundos. Si tarda más, no lo usarán.

  

## **2.1 Formulario 1 —** 

## **Cierre de Caja Diario**

  

**Nombre del Form**: GF_01_Cierre_Caja_Diario

  

**Campos**

1. fecha — **Fecha** (requerido)
    
2. turno — **Lista**: [Almuerzo, Cena, Otro] (requerido)
    
3. hora_cierre — **Hora** (opcional, útil)
    
4. venta_total_cobrada — **Número (moneda)** (requerido)
    
5. tickets_total — **Número entero** (requerido)
    
6. covers_estimados — **Número entero** (opcional pero recomendado)
    
7. ventas_por_canal — **Sección repetida (si no se puede repetir, usar 3 campos fijos)**
    
    - venta_salon — Número
        
    - venta_delivery — Número
        
    - venta_takeaway — Número
        
    
8. pagos_efectivo — Número
    
9. pagos_tarjeta — Número
    
10. pagos_qr — Número
    
11. descuentos_total — Número (default 0)
    
12. devoluciones_total — Número (default 0)
    
13. observaciones — Texto corto
    
14. foto_cierre — **Archivo/Foto** (requerido si no hay POS)
    

  

**Validaciones (reglas)**

- tickets_total >= 1 si venta_total_cobrada > 0
    
- venta_salon + venta_delivery + venta_takeaway ≈ venta_total_cobrada (permitir diferencia ±2% por propinas/redondeos)
    
- efectivo + tarjeta + qr ≈ venta_total_cobrada (tolerancia ±1–2%)
    
- descuentos_total <= 0.20 * venta_total_cobrada (si supera, dispara alerta)
    

---

## **2.2 Formulario 2 —** 

## **Merma y Devoluciones**

  

**Nombre**: GF_02_Merma_Turno

  

**Campos**

1. fecha — Fecha (requerido)
    
2. turno — Lista [Almuerzo, Cena] (requerido)
    
3. tipo_evento — Lista [Merma, Devolución cliente, Error comanda, Sobre cocción]
    
4. categoria — Lista [Corte premium, Corte medio, Guarnición, Bebida, Otro]
    
5. item — Lista (si no hay lista aún: Texto corto + “Otros”)
    
6. cantidad — Número (puede ser porciones o unidades)
    
7. peso_estimado_g — Número (opcional, para carne)
    
8. costo_estimado_bob — Número (opcional al inicio; luego se calcula)
    
9. causa — Lista [Sobre cocción, Caducidad, Mal almacenamiento, Error pedido, Cliente no le gustó, Otro]
    
10. responsable — Lista [Cocina, Salón, Delivery, Proveedor]
    
11. foto — Archivo/Foto (opcional pero útil)
    
12. comentario — Texto
    

  

**Validaciones**

- Si categoria contiene “corte” entonces peso_estimado_g recomendado y cantidad > 0
    
- cantidad no puede ser 0
    
- Si tipo_evento = Devolución cliente → comentario requerido
    

---

## **2.3 Formulario 3 —** 

## **Recepción de Carne / Compras de Proteína**

  

**Nombre**: GF_03_Recepcion_Carne

  

**Campos**

1. fecha_recepcion — Fecha (requerido)
    
2. proveedor — Lista desplegable (requerido)
    
3. nro_factura — Texto corto (si no hay, “SIN_NRO”)
    
4. corte_estandar — Lista desplegable desde Dim_Corte (requerido)
    
5. unidad_compra — Lista [kg, lb, caja, unidad] (requerido)
    
6. cantidad — Número (requerido)
    
7. precio_unitario — Número (moneda por unidad) (requerido)
    
8. total_linea — Número (opcional, se puede calcular)
    
9. calidad — Lista [A, B, C] o [Excelente, OK, Mala]
    
10. temperatura_recepcion — Número (opcional)
    
11. foto_factura — Archivo/Foto (requerido)
    
12. observaciones — Texto corto (opcional)
    

  

**Validaciones**

- cantidad > 0
    
- precio_unitario > 0
    
- Alertas (no bloquear, solo marcar):
    
    - precio_unitario fuera de rango por corte (rango definido en Dim_Corte: min/max esperado)
        
    
- Si unidad_compra = lb, convertir automáticamente en backend.
    

---

# **3) Motor de Cálculo (Backend en Google Sheets)**

  

## **3.1 Arquitectura de pestañas (layout recomendado)**

  

**Este es el esqueleto.** No lo compliques.

  

### **Tablas “Raw” (no se editan manualmente)**

1. RAW_Caja (respuesta GF_01)
    
2. RAW_Merma (respuesta GF_02)
    
3. RAW_Carne (respuesta GF_03)
    
4. (Opcional) RAW_VentasLineas_POS (si logras export del POS)
    
5. RAW_MenuRecetas (si no existe, se crea manual inicial)
    

  

### **Dimensiones (catálogos)**

6. DIM_Corte (cortes estándar + sinónimos + rendimiento)
    
7. DIM_MenuItem (platos/bebidas, categoría, si usa proteína, etc.)
    
8. DIM_Impuestos_Config (tasas y factores)
    
9. DIM_CostosIndirectos (empaques, comisiones delivery, carbón por turno, etc.)
    

  

### **Tablas “Model” (limpias y estandarizadas)**

10. FACT_VentasDiaTurno (de RAW_Caja)
    
11. FACT_ComprasCarne (de RAW_Carne con unidades convertidas)
    
12. FACT_Merma (de RAW_Merma con costos imputados)
    
13. MODEL_Costeo_Menu (costo teórico por plato)
    

  

### **Outputs / Dashboards**

14. DASH_Propietario
    
15. DASH_Gerente
    

---

## **3.2 Lógica de limpieza clave (pseudocódigo / Excel lógica)**

  

### **3.2.1 Estandarización de unidades (compras)**

  

En FACT_ComprasCarne:

- cantidad_kg = IF(unidad="kg", cantidad, IF(unidad="lb", cantidad*0.453592, IF(unidad="caja", cantidad*kg_por_caja, ... )))
    
- precio_por_kg = total_linea / cantidad_kg
    

  

**Nota**: si no hay total_linea, calculas: cantidad * precio_unitario.

---

## **3.3 Food Cost Real vs Teórico (carne)**

  

### **A) Food Cost Real (lo que “se fue” de inventario)**

  

En un mundo ideal harías inventario inicial + final. En bajo recurso, lo hacemos por aproximación:

  

**Opción práctica v0 (sin inventario formal):**

- carne_consumida_kg_aprox = compras_kg - (stock_final_estimado - stock_inicial_estimado)
    
- Si no hay stock → aproximas: carne_consumida ≈ compras en ventanas semanales, y luego ajustas.
    

  

**Food Cost Real % (proteína)**

- food_cost_proteina_real = SUM(costo_compras_carne_periodo) - ajustes_stock
    
- food_cost_proteina_% = food_cost_proteina_real / venta_neta_operativa
    

  

### **B) Food Cost Teórico (lo que “debería” costar según ventas)**

  

Requiere (aunque sea parcial) **mix de ventas** + **gramaje por plato**.

  

En MODEL_Costeo_Menu:

- Para cada menu_item:
    
    - gramaje_proteina_g
        
    - corte_id
        
    - costo_teorico_proteina = (gramaje_proteina_g/1000) * costo_kg_usable
        
    - costo_teorico_total = costo_teorico_proteina + costo_guarniciones + empaques + comision_delivery_aplica
        
    

  

**Clave parrilla: costo_kg_usable**

- costo_kg_usable = costo_kg_comprado / rendimiento_desposte
    
    - Ej: si rendimiento 0.70, entonces kg usable es más caro.
        
    

  

**Teórico por periodo**

- food_cost_teorico_periodo = SUM( unidades_vendidas_item * costo_teorico_total_item )
    

  

### **C) “Gap” de control (la señal más poderosa)**

- gap_food_cost = food_cost_real - food_cost_teorico
    
- Si gap es positivo → fuga (porciones grandes, merma no registrada, robo, compras caras, rendimiento bajo).
    

---

## **3.4 Contribución Marginal considerando IVA e IT (modelo operativo)**

  

**Importante**: en restaurante chico puede haber mezcla de formal/informal. El dashboard debe permitir ambos escenarios.

  

### **Configuración mínima en** 

### **DIM_Impuestos_Config**

- iva_rate (ej. 0.13 si aplica en tu modelo)
    
- it_rate (ej. 0.03 si aplica en tu modelo)
    
- modo_neteo = [“separado”, “factor”]
    

  

### **Definición operativa de venta neta**

- Si tienes separación de impuestos:
    
    - venta_neta = venta_total - iva - it
        
    
- Si NO tienes separación:
    
    - venta_neta = venta_total / (1 + iva_rate + it_rate)  _(aproximación operativa; configurable)_
        
    

  

### **CM por ítem (si tienes ítem de línea)**

- CM_item = venta_neta_item - costo_variable_item
    
- Donde costo_variable_item incluye:
    
    - costo_ingredientes_teorico (proteína + guarnición)
        
    - empaques si canal ≠ salón
        
    - comision_delivery si canal = delivery
        
    

  

### **CM por turno/día (si solo tienes caja)**

- CM_turno ≈ venta_neta_turno - food_cost_real_turno - costos_variables_estimados_turno
    
    - costos variables estimados: empaques, comisiones, carbón proporcional, etc.
        
    

  

> En v0, CM será “estimado” pero útil para tendencias y decisiones.

---

# **4) Arquitectura del Dashboard v0 (layout y gráficos)**

  

## **4.1 DASH Propietario (Estratégico)**

  

**Estructura en 2 columnas**

  

**Fila 1: Resumen (tarjetas KPI)**

- KPI1: Venta neta MTD (Tarjeta)
    
- KPI2: Cash collected MTD (Tarjeta)
    
- KPI3: Food Cost % proteína (Tarjeta + semáforo)
    
- KPI4: Labor % (si lo tienes; si no, “pendiente”)
    

  

**Fila 2: Gráficos de control**

- Ventas por día (línea)
    
- Food cost % por semana (línea)
    
- CM/h por semana (línea)
    

  

**Fila 3: Alertas**

- Tabla “Top 5 desvíos”:
    
    - gap food cost
        
    - días con descuentos altos
        
    - días con diferencias caja vs pagos
        
    - compras con precio/kg fuera de rango
        
    

  

**Gráficos recomendados**

- Línea: tendencias (ventas, CM/h, food cost)
    
- Barras apiladas: ventas por canal
    
- Tabla con formato condicional: alertas
    
- Evitar gauges al inicio (se vuelven “decoración”). Si usas uno, solo para Food Cost %.
    

---

## **4.2 DASH Gerente (Operativo)**

  

**Fila 1: Operación del día/semana**

- Covers por turno (tarjeta)
    
- Ticket promedio (tarjeta)
    
- Rotación estimada (tarjeta)
    

  

**Fila 2: Eficiencia**

- Tiempo de salida platos estrella (barras)
    
- Mix de ventas top 10 (barras horizontales)
    

  

**Fila 3: Control de pérdidas**

- Merma por causa (barras apiladas)
    
- Merma premium (línea semanal o barras)
    

  

**Fila 4: Stock / compras**

- Tabla: precio/kg por corte vs rango (con semáforo)
    
- Quiebres de stock (lista)
    

---

# **Extra) Gobierno de Datos mínimo (quién manda cuando no cuadra)**

  

## **Roles (mínimos)**

- **Data Owner (Dueño)**: define reglas y aprueba definiciones (venta neta, descuentos permitidos).
    
- **Data Steward (Encargado)**: responsable de que se capture y que el cierre diario exista.
    
- **Auditor de caja (rotativo)**: quien revisa discrepancias 10 min al día.
    

  

## **Regla de “Fuente de la verdad” (cuando caja ≠ dinero físico)**

1. **El “hecho” oficial del día es el Cierre de Caja (GF_01)**, pero…
    
2. Si efectivo + tarjeta + QR no cuadra con venta_total:
    
    - Se crea un registro en una pestaña INCIDENCIAS_CAJA con:
        
        - fecha, turno, diferencia, motivo, responsable, resolución.
            
        
    
3. **Jerarquía de evidencia**
    
    - Extractos QR/tarjeta > POS > caja manual > “memoria”
        
    
4. Si la diferencia se repite 3 días en 7 → acción correctiva:
    
    - simplificar método de cobro, o
        
    - separar roles (quien cobra no cierra), o
        
    - auditoría sorpresa de 15 min.
        
    

---

# **Checklist final para que lo armes hoy**

1. Crear 3 Google Forms con campos exactos (arriba).
    
2. En Google Sheets, crear pestañas RAW (auto) + DIM (manual) + FACT/MODEL (cálculo).
    
3. Cargar DIM_Corte con 12–20 cortes reales + sinónimos.
    
4. Elegir 15 ítems top del menú y definir gramajes (aunque sea estimado).
    
5. Montar los 2 dashboards v0 con tendencias y alertas.
    

---

Si quieres, en el próximo mensaje te dejo **plantillas listas** (en texto) para:

- DIM_Corte (columnas exactas + ejemplo de 10 cortes con sinónimos),
    
- DIM_MenuItem y RAW_MenuRecetas,
    
- y fórmulas concretas tipo Google Sheets (ARRAYFORMULA / QUERY) para construir FACT_ComprasCarne y FACT_VentasDiaTurno.

## **A) Plantillas listas para tu Google Sheets (v0)**

  

### **A1)** 

### **DIM_Corte**

###  **(catálogo maestro de cortes + sinónimos + rendimientos)**

  

Crea una pestaña llamada **DIM_Corte** con estas columnas:
|**corte_id**|**corte_estandar**|**categoria**|**rendimiento_objetivo**|**unidad_base**|**sinonimos_csv**|**rango_precio_kg_min**|**rango_precio_kg_max**|**notas**|
|---|---|---|---|---|---|---|---|---|
> Nota: deja los rangos de precio en “0 / 999999” hasta que tengas 2–3 semanas de datos y luego pones rangos reales.