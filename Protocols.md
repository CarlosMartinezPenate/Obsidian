---
type: protocol
project: Dino cultures
topic: OD measurement
bench_type: vertical clean bench
status: draft
tags:
  - protocol
  - dinoflagellates
  - OD
  - clean-bench
  - sterile-technique
---

# OD Measurement Workflow in Vertical Clean Bench

## Goal

Measure OD from dinoflagellate cultures while minimizing contamination risk to the stock cultures.

This workflow assumes the OD sample is **not returned to the culture**. Once culture is transferred into an OD cuvette, that sample is treated as a dead-end sample: **measure and discard**.

## Main contamination-control rule

> Never cross used tips, used cuvettes, dirty gloves, or waste movements over an open culture.

Preferred sequence:

```text
Open → pipette OUT → close → return closed culture → pipette INTO cuvette → waste
```

## Bench zone map

```text
BACK WALL / REAR SLOTS
──────────────────────────────────────────────────────────────
🟥🟥🟥🟥🟥   🟩🟩🟩🟩🟩🟩🟩🟩   🟩🟩🟩🟩🟩🟩
 WASTE        MEDIA + CLOSED CULTURES      TIPS + PIPETTES
 dirty        clean stock                  clean tools


🟥🟥🟥       🟨🟨🟨🟨🟨🟨🟨       🟩🟩🟩🟩
waste-side   ACTIVE CULTURE ZONE           clean tool side
             open ONE flask here
             pipette here
             close immediately


🟨🟨🟨       🟨🟨🟨🟨🟨           🟧🟧🟧🟧🟧
clear hand   clear working space           CUVETTE TRAY
space                                      clean OD area


FRONT OPENING / YOUR HANDS
──────────────────────────────────────────────────────────────
```

## Legend

```text
🟩 Green  = clean stock / clean tools
🟨 Yellow = active work zone / controlled movement
🟧 Orange = clean but not sterile OD area
🟥 Red    = dirty endpoint / waste
```

## Zone definitions

### 🟩 Media + closed cultures

Use this area for:

- closed culture flasks
- closed media bottles
- blanks
- clean stock items

Do not open cultures here if the active culture zone is available.

### 🟩 Tips + pipettes

Use this area for:

- sterile tip boxes
- pipette stand
- clean pipettes

Keep this area dry and separate from waste.

### 🟨 Active culture zone

Use this area for the critical manipulation:

- bring one closed culture here
- open the culture
- pipette out the OD aliquot
- close the culture immediately

Only one culture should be open at a time.

### 🟨 Clear hand space

This is not a storage zone. It is an empty movement lane for hands.

Use this area for:

- entering the hood with gloved hands
- reaching toward tips, cultures, cuvettes, or waste
- repositioning closed items briefly

Do not use this area for:

- opening cultures
- parking used tips
- placing waste
- leaving cuvettes permanently
- crowding with boxes, racks, or bottles

### 🟧 Cuvette tray

Use this as a clean but not sterile OD area.

Use this area for:

- clean unused OD cuvettes
- filled OD cuvettes waiting for measurement
- temporary OD handling

Do not spray the optical faces of the cuvettes with 70% ethanol. If the cuvettes are clean and unused from a clean bag or box, handle them with clean gloves and avoid touching the optical windows.

### 🟥 Waste

Use this area for:

- used tips
- used cuvettes
- discarded OD samples
- contaminated disposable material

Waste movements should happen only after the culture is closed and returned to the clean culture zone.

## OD workflow

1. Prepare the 🟧 cuvette tray with clean unused cuvettes.

2. Take a sterile tip from the 🟩 tips area.

3. Bring ONE closed culture from 🟩 MEDIA + CLOSED CULTURES into the 🟨 ACTIVE CULTURE ZONE.

4. Open the culture only in the 🟨 active zone.

5. Pipette OUT the aliquot from the culture.

6. Close the culture immediately.

7. Move the CLOSED culture back to the 🟩 MEDIA + CLOSED CULTURES zone.

8. Pipette the aliquot INTO the cuvette in the 🟧 cuvette tray.

9. Only after the culture is closed and returned, move the used tip to 🟥 WASTE.

10. Move the filled cuvette to the OD reader.

11. After reading, discard the cuvette/sample as waste.

## Movement logic

```text
Clean path:
🟩 tips → 🟨 open culture → pipette OUT

Protected return:
🟨 closed culture → 🟩 closed culture zone

OD path:
sample in tip → 🟧 cuvette tray → OD reader

Dirty path:
used tip → 🟥 waste
used cuvette/sample → 🟥 waste
```

## Practical sequence for 5 cultures

Example strain order:

```text
SSA01 → SSA02 → SSA03 → SSB01 → SSE01
```

For each strain:

```text
closed culture to active zone
→ open
→ pipette OUT aliquot
→ close
→ return closed culture
→ pipette INTO cuvette
→ discard tip
→ measure OD
→ discard sample
```

## Notes

- The cuvette does not need to be sterile if the sample is not returned to the culture.
- The culture stock must remain protected.
- The highest-risk moment is when the culture is open.
- The culture should be open for the shortest practical time.
- Do not keep all five cultures open or crowded in the active zone.
- Work one strain at a time.
- Avoid touching cuvette optical faces.
- Label cuvettes on the top/frosted side, not on the optical window.
- If the cuvette has droplets or fingerprints on the optical window, clean gently with lint-free tissue before reading.
- Do not pour or pipette anything from the OD cuvette back into the original culture.
- Keep the front/clear hand space mostly empty to avoid blocking airflow and to allow controlled hand movement.
- Do not place large objects directly over or in front of open culture work if they disturb the downward clean airflow.

## Key reminder

```text
The bench zones help, but the real rule is movement:
dirty movements must not pass over open cultures.
```