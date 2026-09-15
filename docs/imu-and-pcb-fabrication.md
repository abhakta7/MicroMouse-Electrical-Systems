# IMU and PCB Fabrication

## Accelerometer

- Detects linear motion
- Does not detect instantaneous velocity
- Made up of microscopic structures as shown below:

[IMAGE: Accelerometer microscopic structure]

- The orange section is the proof or seismic mass which is an H-shaped structure with sense fingers extending from it
  - Tethered to the substrate at both ends
  - Allows for the proof mass to move back and forth
- Electrodes are the light and dark blue components that are fixed to substrate and move about when there are acceleration forces on it
- Electrodes and proof mass do not touch together, rather form a comb-like structure
- If a voltage is applied to the proof mass and electrodes while the sense fingers are perfectly centered, they will have an equal build-up of capacitance
- As the accelerometer moves back and forth, the capacitance between the sense fingers and electrodes changes, where the electrode that the sense finger is closer to has a greater capacitance and the further one has a lower capacitance
- The change in different capacitance is converted to a measurement following the flow chart:

[IMAGE: Accelerometer measurement flow chart]

### Benefits of Capacitive Sensing Accelerometer

- High accuracy
- Stability
- Low-power
- Immune to electrical noise
- Simple physical structure

To detect motion in three dimensions, three different sensors need to be mounted at 90º angles to each other.

## Gyroscope

- Can provide information about the variation in the orientation of an object about a fixed axis
- Can provide information about the angular velocity of an object
- Gyroscopes use precession to record rotational speed
  - Precession - the circular motion generated when a rotating object is affected by a force that causes it to change its orientation
- Coriolis Effect Vibrating Gyroscope
  - Coriolis acceleration - the acceleration change that occurs due to angular velocity being equivalent despite a greater distance from the axis of rotation
  - A mass that is connected by springs is used where once it is rotated, some of the springs will push the mass to one side or the other and this is shown below:

[IMAGE: Coriolis effect vibrating gyroscope]

## Optical Gyroscope

- Work based on the Sagnac effect
  - Sagnac effect - a phase shift occurs between two light beams traveling in opposite directions around a closed loop when the loop is rotating
  - This is shown below where two lasers were emitted and the yellow one reached first since the endpoint of the ring was moving towards the starting point of the yellow laser

[IMAGE: Sagnac effect diagram]

- Two light sources are used as then the interference between these two lasers will cause a new source of electromagnetic radiation which can then be used to calculate the angular velocity

## Inertial Measurement Unit (IMU)

- Packs a 3-axis accelerometer and gyroscope, making a 6-axis IMU
- Some include a 3-axis magnetometer, turning them into 9-axis IMUs
- Able to measure specific force, angular rate, and magnetic fields around the device
  - Provides a comprehensive picture of its motion
- The principle axes are pitch, yaw, and roll which provide data on the object's motion and orientation, combining to a full picture in three-dimensional space

A Grove PCB of an IMU can be seen below:

[IMAGE: Grove IMU PCB]

### Accelerometers

- MEMS technology - microelectromechanical systems
- Have a tiny mass connected to a reference system by a spring
- Speed track of movement using capacitors and special electronic components

### Gyroscopes

- MEMS gyroscopes are commonly used, these rely on the Coriolis effect

### Magnetometer

- A device that measures the magnetic field
- Hall Effect Magnetometers
  - Involves the generation of a voltage difference across a conductor when exposed to an applied magnetic field
  - Allows for the use of semiconducting materials

## Types of IMUs

- Silicon MEMS
  - Revolve around miniaturized sensors measuring mass deflection or the force required to hold a mass in place
- Quartz MEMS
  - One-piece inertial sensing element crafted from quartz, driven by an oscillator to vibrate precisely
  - Vibrating quartz sense angular rate, producing a signal that can be converted to DC
- FOG (Fiber Optic Gyro)
  - Beams of light traverse through a coiled optical fiber
- RLG (Ring Laser Gyro)
  - Similar to FOG but used a sealed ring cavity instead of a coiled optical fiber

### Advantages

- Compact and light design
- Versatility in different environments
- Continuous measurements
- Cost-effectiveness

### Disadvantages

- Drift over time
- Susceptibility to noise
- Calibration requirements

## Taking Measurements with IMUs

### Types of IMUs

- 3-DOF - accelerometer
- 6-DOF - accelerometer and gyroscope
- 9-DOF - accelerometer, gyroscope, and magnetometer

### Degrees of Freedom

- How many different ways something can move in 3D space
- Accelerometer - translational 3 DOF
- Gyroscope - rotational 3 DOF
- Magnetometer - 3 DOF with respect to Earth

### Sensor Fusion

- Tracks the pitch, row, and yaw (heading) of the object and can be used to see orientation

## Additional Information for ICs

### STM32F405ZGT6

- The supply voltage can range from 1.8V to 3.3V but not exceed 3.3V
- Pinout Diagram:

[IMAGE: STM32F405ZGT6 pinout diagram]

- Power supply decoupling should be performed as shown in the two images below (note that only one of the two configurations needs to occur)

[IMAGE: STM32F405ZGT6 power supply decoupling configuration 1]

[IMAGE: STM32F405ZGT6 power supply decoupling configuration 2]

- Do not connect VDDA and VREFF+ in this schematic
- If 10nF capacitors are used, they should be good quality ceramic and be placed as close to the chip as possible
- The schematic for the power supply is shown below

[IMAGE: STM32F405ZGT6 power supply schematic]

  - Each power supply must be decoupled and must follow the rules stated above
  - The two 2.2μF capacitors should be replaced by two 100nF decoupling capacitors when the voltage regulator is off
  - The 4.7μF capacitor must be connect to one of the VDD pins
  - VDDA = VDD and VSSA = VSS

### BNO086

- The supply voltage can range from 2.4V to 3.6V
- The ideal operating temperature range is -0ºC to 85ºC
- The pinout is below:

[IMAGE: BNO086 pinout]

- This component uses a standard Fast mode I2C interface and can communicate at 400 kb/s
- The schematic of the I2C connection is shown below

[IMAGE: BNO086 I2C connection schematic]

  - The H_INTN pin is the application interrupt line. This should be tied to a GPIO with wake capability. The interrupt is active low
  - MRST is the reset line and can be either driven by the application processor or the board reset
  - BOOTN is sampled at rest. If low the BNO08X will enter bootloader mode
  - Pin 4 should be pulled high through a 10k resistor
  - To use device firmware update, it is recommended to connect pin 4 to a GPIO pin on the external microcontroller
