# Contest and DIY PCB Patterns

Use this reference for electronics contest, student project, and hobby boards where the goal is a practical first or second revision.

## General Bias

- Prefer simple, known-good circuits over clever minimal circuits.
- Prefer debug visibility over compactness.
- Prefer common parts with datasheets, examples, and known footprints.
- Prefer modules when schedule risk is high, especially for wireless, high-power motor control, precision analog, and battery charging.
- Add labels and test points even if the board becomes slightly larger.

## MCU Control Board

Common blocks:

- MCU or MCU module
- 3.3 V regulator
- USB-UART or programming/debug header
- reset and boot buttons where needed
- power LED and user LED
- I2C/SPI/UART/GPIO headers
- sensor/actuator connectors

Checks:

- Boot pins and reset circuit match the MCU datasheet.
- Programming method is available after the board is assembled.
- All required rails and grounds are present on expansion headers.
- Spare pins are not trapped under the MCU with no access.

## Sensor Acquisition Board

Common blocks:

- sensor connectors or sensor ICs
- analog front end if needed
- ADC or MCU analog inputs
- filtering and protection
- clean power rail
- communication interface to main controller

Checks:

- Sensor voltage and logic level match the controller.
- Pull-ups are present for I2C and sized reasonably.
- Analog traces avoid switching regulators, motors, relays, and PWM.
- Input range cannot exceed ADC or sensor limits.
- Calibration/test pads are available.

## Motor or Relay Driver Board

Common blocks:

- logic input connector
- driver IC or transistor/MOSFET stage
- motor/relay power input
- flyback diode or clamp where needed
- bulk capacitance
- status LED or fault output
- screw terminal or rated connector

Checks:

- Driver current and thermal limits exceed expected load.
- Power traces and connector current ratings are adequate.
- Logic and motor power grounds have a sane return path.
- Flyback path is close to the load/driver.
- High-current loops are short and separated from logic/sensor traces.

## Power Board

Common blocks:

- input connector
- fuse/polyfuse or current limiting where useful
- reverse polarity protection when risk exists
- buck/LDO regulator
- input/output capacitors
- power indicator LEDs
- test points on each rail

Checks:

- Regulator input voltage, output current, dropout, heat, and package are suitable.
- Capacitor voltage ratings have margin.
- Inductor/diode/switch current ratings match the design.
- Feedback network follows datasheet layout guidance.
- Each rail is labeled and measurable.

## Communication Board

Common blocks:

- USB/UART/CAN/RS485/wireless module
- ESD protection if exposed to outside world
- termination or bias resistors where required
- level shifting when voltages differ
- connector labels

Checks:

- TX/RX direction is clear.
- Differential pair routing is reasonable for CAN/RS485/USB, but do not overcomplicate low-speed contest boards.
- Termination is included only where appropriate.
- Connector pinout matches the cable or external module.

## First-Revision Rules

- Add version text: `REV A`, date, and project name.
- Add at least one GND test point near each functional area.
- Add a power LED per important rail.
- Add a current measurement jumper or series resistor option for uncertain power paths when useful.
- Leave space around hot or replaceable parts.
- Avoid placing tall connectors where they block probes or buttons.
- Keep a short bring-up checklist with expected rail voltages and firmware/programming steps.
