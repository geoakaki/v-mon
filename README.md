# Electrical Distribution Board Specification

**English** | [**Read in Georgian (ქართულად)**](README.ge.md)

A complete guide for building a modern, safe electrical distribution panel for a residential property with 13 individual circuits. This design uses high-quality Hager components with individual RCBO protection for each circuit.

## What is This System?

This electrical panel design provides:
- **Individual protection** for every circuit (no shared protection)
- **Automatic voltage monitoring** that disconnects power during voltage problems
- **Lightning protection** to safeguard expensive appliances
- **Earth leakage protection** with 30mA RCBOs on every circuit
- **Selective tripping** - only the faulty circuit disconnects, others stay on

## System Overview

### Main Protection Components (What Comes First)

| Qty | Component | Part Number | Brand | Model | Description |
|-----|-----------|-------------|-------|-------|-------------|
| 1× | **Voltage Monitor** | E1YM400VS10 | TELE | E1YM | Monitors incoming voltage (160-280V range); triggers contactor during under/overvoltage conditions |
| 1× | **Main Contactor** | ESC263 | Hager | ESC | 2P 63A contactor with 230V AC coil; 2 NO contacts; acts as main disconnect controlled by voltage monitor |
| 1× | **Main Circuit Breaker** | MCN163 | Hager | MCN | 1P 63A C-curve; provides overcurrent and short circuit protection (6kA breaking capacity) |
| 1× | **Surge Protection** | SPA911 | Hager | SPA | 2P 25kA Type 1+2 surge arrester; protects against lightning and voltage spikes |
| 9× | **RCBOs - C16** | ADC916R | Hager | ADC | 1P+N 16A C-curve Type A 30mA 6kA; for rooms, bathrooms, AC, laundry, refrigerators, dishwasher |
| 4× | **RCBOs - C25** | ADC925R | Hager | ADC | 1P+N 25A C-curve Type A 30mA 6kA; for oven, electric stove/teapot/toaster, studio AC (50m²) |
| 1× | **RCBOs - C32** | ADC932R | Hager | ADC | 1P+N 32A C-curve Type A 30mA 6kA; for EV charger & MIG welder |

| Component | Image | Description |
|-----------|-------|-------------|
| **Voltage Monitor**<br/>TELE E1YM400VS10 | <img src="imgs/voltage-monitor-tele.jpg" width="200"/> | Watches incoming voltage (160-280V range)<br/>Triggers contactor if voltage problems occur |
| **Main Contactor**<br/>Hager ESC263 | <img src="imgs/contactor-lc1d40a.jpg" width="200"/> | Main ON/OFF switch 63A 2NO<br/>Controlled by voltage monitor |
| **Main Circuit Breaker**<br/>Hager MCN163 | <img src="imgs/breaker-ic60n.jpg" width="200"/> | Overcurrent & short circuit protection<br/>C63 6kA breaking capacity |
| **Surge Protector**<br/>Hager SPA911 | <img src="imgs/rcbo-idpn-vigi.jpg" width="200"/> | Lightning & voltage spike protection<br/>Type 1+2, 25kA, combined protection |
| **RCBO (Individual Circuits)**<br/>Hager ADC916R/925R/932R | <img src="imgs/rcbo-idpn-vigi.jpg" width="200"/> | 14× individual protection circuits<br/>C16/C25/C32, Type A, 30mA per circuit |

### How Everything Connects

**System Diagram:** Complete busbar distribution showing all connections, busbars, and individual circuits.

<picture>
  <source srcset="imgs/busbar-distribution-v4.drawio-dark.png" media="(prefers-color-scheme: dark)">
  <img src="imgs/busbar-distribution-v4.drawio-light.png" alt="Busbar Distribution Diagram" width="100%" />
</picture>

### RCBO Protection Explained

**RCBO = Residual Current Circuit Breaker with Overcurrent protection**

Each circuit gets its own RCBO that provides:
- Overcurrent protection (like a regular breaker)
- Ground fault protection (like a GFCI outlet)
- Instant disconnect if current leaks (30mA sensitivity)

**Benefits:**
- If one room has a problem, only that circuit trips
- Better safety than shared protection
- Easier troubleshooting (you know exactly which circuit failed)

## All 13 Circuits - What Gets Protected

Every circuit uses **Hager ADC** RCBOs with these specifications:
- **Type A** - suitable for modern electronics, computers, LED lights
- **30mA sensitivity** - trips in 0.03 seconds if current leaks (very safe)
- **1P+N** - single phase + neutral (standard residential)
- **C-curve** - handles startup surges from motors, compressors

## Complete Circuit List

### 1-4: Living Spaces (All Rooms)
| # | What It Powers | RCBO | Max Load | Notes |
|---|----------------|------|----------|-------|
| 1 | Room 1 - all outlets & lights | C16 | 3,680W | Computers, TV, lamps, phone chargers |
| 2 | Room 2 - all outlets & lights | C16 | 3,680W | Same as above |
| 3 | Room 3 - all outlets & lights | C16 | 3,680W | Same as above |
| 4 | Studio - all outlets & lights | C16 | 3,680W | Workspace equipment, lighting |

### 5-6: Bathrooms
| # | What It Powers | RCBO | Max Load | Notes |
|---|----------------|------|----------|-------|
| 5 | Bathroom 1 - lights, outlets, fan | C16 | 3,680W | Hair dryer, electric razor, etc. |
| 6 | Bathroom 2 - lights, outlets, fan | C16 | 3,680W | Same as above |

### 7-8: Air Conditioning
| # | What It Powers | RCBO | Max Load | Notes |
|---|----------------|------|----------|-------|
| 7 | Room 1 AC unit | C16 | 3,680W | Handles startup surge for standard room |
| 8 | Studio AC unit (50m²) | C25 | 5,750W | Large 2-2.5 ton unit for 50 square meter space |

### 9-12: Kitchen Appliances
| # | What It Powers | RCBO | Max Load | Notes |
|---|----------------|------|----------|-------|
| 9 | Refrigerators (main + wine fridge) | C16 | 3,680W | Standard protection for refrigerators |
| 10 | Electric oven | C25 | 5,750W | Heavy-duty circuit for high power |
| 11 | Electric stove, teapot, toaster oven | C25 | 5,750W | Combined circuit for cooking appliances |
| 12 | Dishwasher | C16 | 3,680W | Heating element draws significant current |

### 13: Laundry Room
| # | What It Powers | RCBO | Max Load | Notes |
|---|----------------|------|----------|-------|
| 13 | Washing machine & Clothes dryer | C16 | 3,680W | Combined circuit for both appliances |

### 14: Heavy Equipment
| # | What It Powers | RCBO | Max Load | Notes |
|---|----------------|------|----------|-------|
| 14 | EV Charger & MIG Welder | C32 | 7,360W | **WARNING:** Never run both simultaneously at full power |

## Shopping List - What to Buy

### Main Control Components (4 items)
| Qty | Part Number | Description | Approx. Price Range |
|-----|-------------|-------------|---------------------|
| 1 | TELE E1YM400VS10 | Voltage monitor relay | ₾200-300 (€80-120) |
| 1 | Hager ESC263 | Contactor 63A 2NO + coil (230V AC) | ₾120-180 (€50-70) |
| 1 | Hager MCN163 | Main breaker 1P C63 6kA | ₾70-100 (€30-40) |
| 1 | Hager SPA911 | Surge protection device Type 1+2 2P 25kA | ₾150-250 (€60-100) |

### Individual Circuit Protection (14 RCBOs)
| Qty | Part Number | For Which Circuits | Approx. Price Each |
|-----|-------------|--------------------|--------------------|
| 9 | Hager ADC916R | Rooms, bathrooms, AC, dishwasher, laundry, refrigerators (C16 Type A 30mA) | ₾100-140 (€40-55) |
| 4 | Hager ADC925R | Electric oven, electric stove/teapot/toaster, studio AC 50m² (C25 Type A 30mA) | ₾100-140 (€40-55) |
| 1 | Hager ADC932R | EV charger & MIG welder (C32 Type A 30mA) | ₾100-140 (€40-55) |

### Additional Materials Needed
- Distribution board enclosure (min. 22 modules wide)
- Busbar (single-phase + neutral)
- Wire: 2.5mm² for C16, 4mm² for C25, 6mm² for C32
- Circuit labels and marker
- Din rail clips and cable ties

**Note:** No main RCD required - all circuits protected by individual 30mA RCBOs

**Estimated Total Cost: ₾2,550 - ₾3,900 (€1,030 - €1,560)** (parts only, excluding labor)

## Critical Installation Instructions

### ⚠️ DANGER - Read Before Installing

**1. Neutral Segregation (MOST IMPORTANT)**
- Each RCBO has its own neutral terminal
- **NEVER** share neutrals between circuits
- Wrong: Two circuits sharing one neutral = RCBO won't work
- Right: Circuit 1 neutral → RCBO 1, Circuit 2 neutral → RCBO 2
- **Violation causes**: nuisance tripping, safety hazards, fire risk

### 2. Proper Connection Sequence
Follow this order exactly:
1. Install main breaker first (grid connection)
2. Install contactor after breaker
3. Wire voltage monitor to contactor coil
4. Install surge protector on separate branch
5. Install all 14 RCBOs in a row
6. Connect busbar to distribute power to all RCBOs

### 3. Wiring Standards
- Use **2.5mm²** copper wire for C16 RCBOs (16A circuits)
- Use **4mm²** copper wire for C25 RCBOs (25A circuits)
- Use **6mm²** copper wire for C32 RCBO (32A EV charger circuit)
- All connections must be tight (use torque screwdriver: 2-2.5 Nm)

### 4. Testing Procedure
Before connecting any loads:
1. Test main breaker operation (manual trip)
2. Test each RCBO test button (should trip at 30mA)
3. Verify voltage monitor triggers contactor
4. Measure voltage at each RCBO output

### 5. Labeling
Print and attach labels to each RCBO:
```
Circuit 1: Room 1 Outlets/Lights
Circuit 2: Room 2 Outlets/Lights
Circuit 3: Room 3 Outlets/Lights
Circuit 4: Studio Outlets/Lights
Circuit 5: Bathroom 1
Circuit 6: Bathroom 2
Circuit 7: AC - Room 1
Circuit 8: AC - Studio (50m² / 2-2.5 ton unit)
Circuit 9: Refrigerators
Circuit 10: Electric Oven
Circuit 11: Electric Stove/Teapot/Toaster
Circuit 12: Dishwasher
Circuit 13: Washing Machine & Dryer
Circuit 14: EV Charger & MIG Welder (Never both at full power)
```

## Advanced Options

### Upgrade to Type F RCBOs (Optional)
If you have modern inverter-based appliances:
- **Consider Type F** for circuits 7-8 (AC units), 13 (washing machine & dryer), and 14 (EV charger & inverter welder)
- Type F RCBOs handle DC fault currents better from inverter-based equipment
- Cost: ~€10-15 more per unit
- **Highly recommended for circuit 14 (EV charger and inverter welder)**

### Heavy Equipment Notes
**Studio AC (Circuit 8):**
- 50 square meter studio requires 2-2.5 ton AC unit (18,000-24,000 BTU)
- Typical draw: 16-20A at 230V (~4,000-5,000W)
- C25 RCBO provides adequate protection with headroom
- Use 4mm² copper wire for this circuit

**EV Charger & MIG Welder (Circuit 14):**
- **CRITICAL WARNING:** Never operate both devices simultaneously at full power
- EV Charger: 32A circuit provides ~7.3kW charging (Level 2)
- MIG Welder (IPOTOOLS MIG 225SYN): 225A output, ~20A input at 230V, draws 4-5kW at maximum
- Combined potential draw: 25-27A peak (exceeds 32A rating if both at full power)
- Use 6mm² copper wire minimum
- **Strongly recommend Type F RCBO for this circuit**
- Typical usage: charge EV overnight, weld during day (not simultaneously)

### Why Refrigerators Use C16
- Refrigerators typically draw 1-3A during normal operation
- C16 provides adequate protection without nuisance tripping
- Handles compressor startup surges reliably
- Standard rating simplifies component inventory

---

*Document prepared with assistance*
