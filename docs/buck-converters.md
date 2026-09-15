# Buck Converters

## Key Components

This is the power stage circuit schematic:

[IMAGE: Buck converter power stage circuit schematic]

- Q1 is the MOSFET
  - Primary function - acts as a switch that allows for the input voltage source to flow through the inductor
  - Key parameters when selecting a MOSFET
    - Drain-to-source voltage rating
    - Current rating
    - Power dissipation rating
    - Thermal characteristics
- L1 is the inductor
  - Inductors resist the change in current flowing through it
  - There will be a gradual incline in current as opposed to a spike
  - Can store energy in their magnetic field and release it later
    - Done to prevent the current from changing
  - Key parameters when selecting an inductor
    - Inductance
    - Current rating
    - Saturation current rating
    - Equivalent series resistance
- Co is the output capacitor
  - Capacitor wants to keep a constant voltage drop across it
  - Key parameters when selecting a capacitor
    - Voltage rating
    - Capacitance
    - Equivalent series resistance
    - Ripple current rating
- Ci is the input capacitor
  - Helps smooth out the voltage spikes due to the MOSFET
  - Prevents any noise from propagating back to the voltage supply source
- D1 is the rectifier diode
  - Works in reverse with the MOSFET
    - When current is off, it provides another path for current to go into the inductor
  - Key parameters when selecting a diode
    - Reverse voltage breakdown
    - Forward voltage
    - Current rating
    - Power dissipation rating

## Modes of Operation

- Analysis when the MOSFET is on and when the MOSFET is off
- Charging phase - when the MOSFET is first turned on and the inductor is resisting the current change and starts storing energy in its magnetic field
- When the MOSFET is turned off, the inductor starts to release its magnetic field energy to keep the current constant
  - As such, there will be a linear decrease in current as the inductor slowly loses its energy
  - The diode allows for the current to flow in an alternate path, which allows the inductor to release its energy
- By opening and closing the switch periodically, the average current flowing through the inductor can be controlled
- The average current flowing through the inductor will also be the average current flowing through the load
- The average current through the inductor is equivalent to the duty cycle of the MOSFET
- The voltage across the load is dictated by Ohm's law

The opening and closing of the MOSFET creates a square wave.

[IMAGE: Buck converter switching waveform]

Connected a capacitor in series with the load creates a low-pass filter which turns the square wave into something more similar to a constant DC voltage.
