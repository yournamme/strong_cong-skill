# JLC EDA / EasyEDA Pro Workflow

Use this reference when coaching a user through the actual board drawing process in JLC EDA Professional / EasyEDA Pro.

## Project Setup

1. Create a new project with clear names for schematic and PCB files.
2. Set units and grid before drawing. Use a coarse grid for symbols/connectors and a finer grid only when needed.
3. Decide early whether the board is 2-layer or 4-layer. For student contest and DIY boards, start with 2 layers unless routing, noise, or power integrity clearly demands more.
4. Create schematic pages or sections by function: power, MCU, sensors, drivers, communication, user interface, connectors.

## Schematic Steps

1. Place each module's main IC or connector first.
2. Add required support circuits from the datasheet or a trusted reference design:
   - decoupling capacitors close to power pins
   - pull-ups/pull-downs
   - boot/config pins
   - oscillator or clock parts
   - reset and programming circuit
   - input protection where needed
3. Name nets intentionally: `5V`, `3V3`, `VIN`, `GND`, `UART_TX`, `UART_RX`, `I2C_SCL`, `I2C_SDA`, `MOTOR_A`, etc.
4. Add connectors with visible pin labels and pin 1 orientation.
5. Add test points for rails, reset, UART, boot, critical analog signals, and driver outputs.
6. Add notes in schematic for current limits, voltage ranges, connector direction, and risky assumptions.
7. Assign footprints only after checking package dimensions and solderability.
8. Run schematic checks/ERC where available. Treat warnings as review prompts, not noise.

## Footprint Selection

- Prefer 0805 or 0603 passives for hand-soldered boards.
- Prefer SOT-23, SOT-223, SOP/SOIC, TSSOP, terminal blocks, and 2.54 mm headers for beginner-friendly assembly.
- Use QFN only when necessary and warn about soldering difficulty.
- Avoid BGA for student DIY unless using an assembled module.
- Verify symbol pin numbers match the footprint and datasheet.
- For connectors, verify pitch, orientation, height, and whether the mating cable/module blocks nearby components.

## PCB Setup

1. Update/import the PCB from schematic.
2. Draw the board outline before placement.
3. Add mounting holes and mechanical keepouts early.
4. Configure design rules based on the board house and user skill:
   - trace width/clearance
   - via size
   - copper-to-board-edge clearance
   - net classes for power and high-current nets
5. Use wider traces for power and motor paths. Calculate or conservatively estimate current needs instead of using signal-width traces everywhere.

## Placement Order

1. Mechanical constraints: board outline, mounting holes, panel edges, connector locations.
2. User-facing parts: USB, buttons, switches, LEDs, displays, terminals.
3. Power entry and regulators.
4. High-current/noisy devices: motor drivers, relays, switching regulators.
5. MCU/module near the signals it controls.
6. Decoupling capacitors next to IC power pins.
7. Sensors and analog circuits away from noisy switching/high-current areas.
8. Test points where probes can reach them.

## Routing Priorities

1. Main power input and high-current paths.
2. Ground return strategy and copper pours.
3. Sensitive analog, clock, USB, crystal, feedback, and switching regulator loops.
4. Communication buses: UART, I2C, SPI, CAN.
5. General GPIO and low-speed signals.

Keep loops small for switching regulators and motor drivers. Do not route sensitive analog traces parallel to noisy power or PWM traces for long distances.

## Ground and Copper

- Use a solid ground pour on at least one layer when possible.
- Avoid splitting ground casually on a simple 2-layer board.
- Keep high-current return paths short and predictable.
- Add stitching vias near connectors, regulators, and noisy sections when they help current return.
- Ensure copper pours actually connect where intended after DRC.

## Labels and Debuggability

Add silkscreen labels for:

- board name and version
- connector names and pin functions
- voltage rails
- switch/button meaning
- LED meaning
- programming/debug headers
- polarity marks

Keep labels readable and away from pads, vias, and board edges.

## Checks Before Ordering

1. Run DRC and inspect each violation.
2. Check ERC/schematic warnings.
3. Confirm every part has the intended footprint.
4. Confirm connector orientation and pin 1.
5. Confirm board outline, mounting holes, and mechanical clearances.
6. Confirm power trace widths and regulator thermal concerns.
7. Confirm silkscreen is not covering pads.
8. Confirm test points and programming headers are reachable.
9. Export Gerber/production files.
10. Open the generated preview if available and inspect every layer visually.
11. Confirm manufacturing options: layer count, thickness, copper weight, solder mask, surface finish, quantity.

## Teaching Style

Batch instructions at the module level, not the single-step level. Default to giving the user everything needed to finish one coherent module in a single response — every part to place, its rough position, exact values, net names to type, and the order to do them in — rather than handing out one line and waiting.

**How to size a turn:**

- One coherent module (e.g., "3.3 V regulator + input/output caps + power LED", "MCU + decoupling + boot/reset circuit", "one connector's full pin assignment and labeling") = one turn, fully spelled out.
- Several small, low-risk modules that don't require new decisions can be combined into one turn (e.g., "power LED + reset button + boot button" together).
- A large or unusually dense module (e.g., routing 20+ signals, a busy connector fan-out) can still be one turn if it's mechanical and low-risk — write it as a checklist rather than a paragraph so it stays easy to follow. Only split it across turns if it's genuinely too much to execute without losing track, and say why you're splitting it.
- Do not artificially chop a small, cohesive task into multiple turns just to keep messages short — that is the failure mode to avoid.

**When to actually pause and hand back to the user:**

- The current module is genuinely finished and the next module depends on a choice, a measurement, a datasheet check, or a screenshot/export for review.
- A real risk or ambiguity needs the user's input before it's safe to continue (e.g., an unconfirmed footprint, an unclear mechanical constraint).
- The remaining work is large enough that doing it all at once would be overwhelming to follow — state why you're pausing so it doesn't read as arbitrary.

When you do pause, end with one clear, specific ask — "画完这一块后发一张原理图截图" or "确认一下这个封装的引脚间距对不对" — not a vague "继续" or "还有问题吗".

Prefer concrete instructions like "place the 3.3 V regulator within 2 cm of the power input and put its input/output capacitors next to the pins" over broad advice like "optimize power layout" — but give ALL the concrete instructions needed for the current module in the same turn, not one instruction per message.
