# Sallen-Key Filter

## What is a Sallen-Key Filter?

- Is a second order active filter design based around a single non-inverting op-amp and two resistors
- Creates a voltage-controlled voltage-source (VCVS) with filter characteristics of high input impedance, low output impedance and good stability
  - Allows for Sallen-key filters to be cascaded together for higher order filters

## RC Network Characteristics

### Voltage Divider

- When two (or more) resistors are connected together across a DC supply voltage, each resistor will have different voltage values
- Resistive Voltage Divider:

[(docs/images/Resistive voltage divider.png)]

### Resistive Voltage Divider Transfer Function

- The transfer function shows how an output voltage will change based on the input voltage and resistance of each resistor

$$\Large A_v = \frac{V_{OUT}}{V_{IN}} = \frac{R_2}{R_1 + R_2}$$

- Thus:

$$\Large V_{OUT} = V_{IN} \frac{R_2}{R_1 + R_2}$$

## RC Voltage Divider

- In an AC circuit, the capacitor has a property called capacitive reactance
- Impedance of the capacitor depends on the frequency
- At very low frequencies, the capacitor acts as an open
- At very high frequencies, the capacitor acts as a short

Voltage divider transfer function:

$$\Large A = \frac{V_{OUT}}{V_{IN}} = \frac{R}{R + X_C}$$

## RC Filter Circuit

- At low frequencies, the voltage gain is extremely low as the input signal is blocked by the reactance of the capacitor
- At high frequencies, the voltage gain is high as the reactance causes the capacitor to act as a short circuit
- Cut-off frequency defines where the circuit changes from blocking frequencies to allowing frequencies to pass through

$$\Large f_c = \frac{1}{2\pi RC}$$

## Active High Pass Filter

- The RC filter part of the circuit responds the same as before
- The op-amp is configured as a non-inverting amplifier which allows for a voltage gain of the ratio between R1 and R2

[IMAGE: Active high-pass filter schematic]

- Cut-off frequency equation:

$$\Large A_v = 1 + \frac{R_1}{R_2}$$

## Second-order RC Filter

- Consists of two RC sections cascaded together
- The input and output impedances of the two RC stages should not affect each other's operation (non-interacting)
- High Pass Filter Circuit

[IMAGE: Second-order RC high-pass filter circuit]

- Cascading one RC filter stage with another does not work very well as each subsequent stage loads the previous one, thus causing the cut-off frequency to move away from the desired frequency

## Sallen and Key Filters

- Sallen-Key is one of the most common filter configurations for designing first and second order filters
- Building block for higher order filters

### Advantages

- Simplicity and Understanding of their Basic Design
- The use of a Non-inverting Amplifier to Increase Voltage Gain
- First and Second-order Filter Designs can be Easily Cascaded Together
- Low-pass and High-pass stages can be Cascaded Together
- Each RC stage can have a different Voltage Gain
- Replication of RC Components and Amplifiers
- Second-order Sallen-key Stages have Steep 40dB/decade roll-off than cascaded RC

### Limitations

- The voltage gain and magnification factor are closely related due to the use of an op-amp
- Any Q values greater than 0.5 can be used since the voltage gain will always be greater than 1 but less than 3 (becomes unstable after)

## Sallen-key High Pass Filter

[IMAGE: Sallen-key high-pass filter schematic]

- The resistor RA is no longer grounded, but instead provides positive feedback for the amplifier
- At low frequencies, the capacitors act as open circuits and at high frequencies they act as short circuits
- Around the cut-off frequencies, the impedance of the capacitors will be the same values of the resistance in the resistors and the positive feedback provides voltage gain and increases the output signal magnification
  - This magnification allows for the signal that we actually want to see to be easier to recognize

### Sallen-key Cut-off Frequency Equation

$$\Large f_c = \frac{1}{2\pi\sqrt{R_1 R_2 C_1 C_2}}$$

### Magnification Factor

The magnification factor is calculated with this equation:

$$\Large Q = \frac{1}{3 - A}$$

## Sallen-key Filter Response

[IMAGE: Sallen-key filter response graph]

- We can see that the greater the value of Q the more distinct the frequency can be
- The lower the value of Q the more stable
- The higher the value, the more unstable
- A negative Q value would lead to oscillations
- If you want to set the value of A (voltage gain), you can use this equation:

$$\Large A = \frac{3Q - 1}{Q} = \frac{V_{OUT}}{V_{IN}} = 1 + \frac{R_1}{R_2}$$

- Using these equations, you can find the value of resistors you want to implement

## Sallen-Key Fusion Simulation

- I picked values of 5.6kΩ, 2.2kΩ, 0.47µF, and 1µF as those are similar to the values I have in my kit
- The op-amp has 1V power because that seemed the most realistic and the resistor values chosen for the voltage gain were 10kΩ and 6kΩ, resulting in a voltage gain of 2.67 V.
- These resistor values were also chose so that the cut off frequency could be as close to 60 Hz as possible, with it being 66.14 Hz
- The results of the simulation along with the Fusion Schematic are show below:

### Fusion Schematic

[IMAGE: Fusion Schematic]

### Fusion Simulation

[IMAGE: Fusion Simulation]

- It can be seen that the output signal did increase slightly as a result of the Salen-key filter as the AC frequency is close to the cut-off frequency
- This could be better seen if I used a higher frequency AC source (adjusting the filter design to compensate) and if I calculated an appropriate voltage gain for a specific value of Q, such as Q equals 3

## Sallen-Key PCB Layout

- I created a Fusion schematic to practice creating PCBs and how to effectively map traces on a PCB

[IMAGE: Sallen-Key PCB schematic]

- The layout is very basic as it was my first one, but I followed the rules of PCB design; keep the traces short and components close together
- I believe this PCB was made using a dual op-amp IC
