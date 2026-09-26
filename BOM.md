# Bill of Materials (BOM) - 24V DC Motor H-Bridge Driver

## Power Semiconductors

| Reference | Description | Part Number | Quantity | Unit Price | Total | Supplier | Notes |
|-----------|-------------|------------|----------|-----------|-------|----------|-------|
| Q1, Q2, Q3, Q4 | N-Channel MOSFET, 30V, 10A, Logic-Level, TO-220 | IRLZ44N or IRF540N | 4 | $0.80 | $3.20 | DigiKey/Mouser | Rds(on) ≤ 0.05Ω @ Vgs=10V |
| D1, D2, D3, D4 | Schottky Diode, 40V, 5A, DO-201AD | SB540 or MBR20100 | 4 | $0.35 | $1.40 | DigiKey/Mouser | Flyback protection |
| D_suppress | Bidirectional TVS Diode, 24V, SMD | SMAJ26A or P6KE24A | 1 | $0.25 | $0.25 | DigiKey/Mouser | Supply transient clamp |

## Gate Driver IC

| Reference | Description | Part Number | Quantity | Unit Price | Total | Supplier | Notes |
|-----------|-------------|------------|----------|-----------|-------|----------|-------|
| IC1 | H-Bridge Gate Driver, 600V, 2A | IR2104 DIP-8 | 1 | $2.50 | $2.50 | DigiKey/Mouser | Bootstrap high-side drive |
| OR IC1_ALT | Motor Driver IC, Integrated H-Bridge | DRV8876PWPR (QFP-16) | 1 | $3.80 | $3.80 | DigiKey/Mouser | **Simpler alternative** - All-in-one |

## Passive Components - Resistors

| Reference | Description | Value | Tolerance | Quantity | Unit Price | Total | Supplier | Notes |
|-----------|-------------|-------|-----------|----------|-----------|-------|----------|-------|
| R1, R2, R3, R4 | Gate Drive Resistor | 10Ω | 1/4W, 5% | 4 | $0.05 | $0.20 | DigiKey/Mouser | Limits dI/dt stress |
| R5, R6, R7, R8 | Pull-down Resistor (optional) | 100kΩ | 1/4W, 5% | 4 | $0.05 | $0.20 | DigiKey/Mouser | Gate discharge safety |
| R_bootstrap | Bootstrap Current Limiting (opt) | 1kΩ | 1/4W, 5% | 1 | $0.05 | $0.05 | DigiKey/Mouser | Optional, for IC1 design |

## Passive Components - Capacitors

| Reference | Description | Value | Voltage | Package | Quantity | Unit Price | Total | Supplier | Notes |
|-----------|-------------|-------|---------|---------|----------|-----------|-------|----------|-------|
| C1, C2 | Bootstrap Capacitor | 100nF | 100V | 0805 (SMD) | 2 | $0.08 | $0.16 | DigiKey/Mouser | Ceramic X7R, low ESR |
| C3 | Bulk Supply Decoupling | 1000µF | 35V | Radial | 1 | $0.85 | $0.85 | DigiKey/Mouser | Aluminum electrolytic |
| C4, C5 | Gate Drive Decoupling | 100nF | 16V | 0603 (SMD) | 2 | $0.08 | $0.16 | DigiKey/Mouser | Ceramic X7R |
| C6 | Input Filter Capacitor | 10µF | 50V | 0805 (SMD) | 1 | $0.15 | $0.15 | DigiKey/Mouser | Optional, noise filtering |

## Protection & Fusing

| Reference | Description | Part Number | Quantity | Unit Price | Total | Supplier | Notes |
|-----------|-------------|------------|----------|-----------|-------|----------|-------|
| F1 | Fuse Holder, Blade (ATC) | ATC Fuse Holder Panel | 1 | $0.50 | $0.50 | DigiKey/Mouser | For 24V supply input |
| F1_fuse | Fuse, 5A, Fast-Blow | ATC 5A 32V | 1 | $0.15 | $0.15 | DigiKey/Mouser | Replace if circuit faults |
| PTC1 | PolyFuse (optional) | 500mA, 30V | 1 | $0.25 | $0.25 | DigiKey/Mouser | Secondary over-current protection |

## Connectors & Headers

| Reference | Description | Part Number | Quantity | Unit Price | Total | Supplier | Notes |
|-----------|-------------|------------|----------|-----------|-------|----------|-------|
| J1 | Power Input Connector, 5.5mm barrel or XT60 | - | 1 | $0.50 | $0.50 | DigiKey/Mouser | 24V DC input |
| J2 | Motor Output Connector, 2-pin Molex | KK 2.54mm | 1 | $0.30 | $0.30 | DigiKey/Mouser | To motor terminals |
| J3 | Control Signal Header, 4-pin | 2.54mm pin header | 1 | $0.20 | $0.20 | DigiKey/Mouser | FWD, REV, PWM, GND |
| J4 | Auxiliary 5V Output (optional) | 2-pin header | 1 | $0.10 | $0.10 | DigiKey/Mouser | For gate driver bias |

## Thermal Management (Optional but Recommended)

| Reference | Description | Part Number | Quantity | Unit Price | Total | Supplier | Notes |
|-----------|-------------|------------|----------|-----------|-------|----------|-------|
| HS1, HS2 | Heatsink, TO-220, Aluminum | Fischer UK 2x2, 0.4K/W | 2 | $0.75 | $1.50 | DigiKey/Mouser | For Q1, Q2 if continuous 2A+ |
| TIM | Thermal Interface Material, Pad | Arctic Silver AS-50-05 | 1 | $3.00 | $3.00 | Amazon/DigiKey | Heatsink mounting |

## PCB & Miscellaneous

| Description | Quantity | Unit Price | Total | Supplier | Notes |
|-------------|----------|-----------|-------|----------|-------|
| PCB (4-layer, 100mm × 80mm) | 1 | $15.00 | $15.00 | JLC PCB / PCBWay | Gerber files provided |
| Solder & Flux | As needed | $5.00 | $5.00 | Local | Rosin core, 60/40 or lead-free |
| Wire, connectors, standoffs | As needed | $3.00 | $3.00 | Local | M3 nylon standoffs, AWG 16-18 |

---

## **TOTAL BOM COST ESTIMATE**

### Minimum Build (IR2104 Version)
| Category | Subtotal |
|----------|----------|
| Power Semiconductors | $4.85 |
| Gate Driver | $2.50 |
| Resistors | $0.45 |
| Capacitors | $1.32 |
| Protection/Fusing | $0.90 |
| Connectors | $1.20 |
| PCB & Assembly | $15.00 |
| **TOTAL (without heatsinks)** | **~$26.22** |
| **TOTAL (with heatsinks)** | **~$30.72** |

### Simpler Build (DRV8876 Version)
| Category | Subtotal |
|----------|----------|
| Motor Driver IC | $3.80 |
| Resistors | $0.25 |
| Capacitors | $0.80 |
| Protection/Fusing | $0.90 |
| Connectors | $1.20 |
| PCB & Assembly | $15.00 |
| **TOTAL (without heatsinks)** | **~$21.95** |

---

## Recommended Suppliers

- **DigiKey**: [https://www.digikey.com](https://www.digikey.com) – Fastest shipping, best selection
- **Mouser Electronics**: [https://www.mouser.com](https://www.mouser.com) – Equivalent to DigiKey
- **Arrow Electronics**: [https://www.arrow.com](https://www.arrow.com) – Alternative
- **AliExpress / eBay**: Cheaper but 2-4 week lead time
- **Local Electronics Supplier**: Check for same-day availability

---

## Alternative Gate Driver Options

If IR2104 is unavailable:

1. **IR2110** – Higher voltage rating (600V), slightly more expensive
2. **IR2104S** – Surface-mount version
3. **DRV8870 / DRV8876** – Integrated H-bridge (all components in 1 IC)
4. **L298N** – Budget option but not recommended (high voltage drop)
5. **TLE6233-2** – Integrated H-bridge with current limiting

---

## Assembly Notes

1. **Soldering order**: Passive components first → ICs → Power semiconductors → Connectors
2. **IC mounting**: Use IC sockets for DIP-8 (IR2104) for easy replacement/testing
3. **MOSFET mounting**: Ensure TO-220 packages have good thermal contact if heatsinks used
4. **Flux cleaning**: Wash board with isopropyl alcohol after soldering
5. **Testing**: Continuity test all traces before power-on

---

## Storage & Safety

- Store MOSFETs in ESD-safe bags
- Keep gate resistors at hand (replaceable if damaged)
- Store fuses separately
- Mark polarity clearly on PCB (+24V, GND)
