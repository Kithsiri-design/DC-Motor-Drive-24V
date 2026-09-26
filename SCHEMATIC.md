# Schematic for 24V DC Motor H-Bridge Driver

The following circuit is a practical relay-free H-bridge for a 24V permanent-magnet DC motor.

## Recommended schematic

```text
                         +24V DC
                            |
                            +---- F1 ----+---- +VCC
                                         |
                                         C1
                                         |
                                 +-----------+
                                 |           |
                                 |   U1      |
                                 | DRV8876   |---- OUT1 --- MOTOR A
                                 |           |
                                 |           |---- OUT2 --- MOTOR B
                                 +-----------+
                                       |  |
                                      IN1 IN2
                                       |  |
                              MCU / control logic
                                       |
                                      GND


             +24V supply clamp
                 |
                 +---- D1 (TVS)
                 |
                GND
```

## Functional explanation

- `F1` protects the supply from overcurrent.
- `C1` reduces supply ripple and spikes.
- `U1` is the H-bridge driver that drives the motor in either direction.
- `IN1` and `IN2` determine the motor direction and braking state.
- `OUT1` and `OUT2` connect to the motor terminals.
- `D1` is a TVS diode on the 24V rail for transient suppression.

## Control table

| IN1 | IN2 | Result |
|-----|-----|--------|
| 0   | 0   | Stop / coast |
| 1   | 0   | Forward |
| 0   | 1   | Reverse |
| 1   | 1   | Brake |

## Design notes

- Use a driver rated above the motor's startup current.
- Add a proper ground connection between the microcontroller and the driver.
- Keep power traces wide and short.
- Add a bulk capacitor close to the driver supply.

## Alternative discrete MOSFET version

If a dedicated driver is not available, a four-MOSFET H-bridge can be used instead. In that case, use:
- 4 N-channel MOSFETs
- gate driver with dead-time protection
- flyback diodes or integrated body diode path
- proper thermal management

This can be built as a classic H-bridge, but the integrated driver is simpler and safer for a small design.
