# Motors

## Magnetism

- Permanent magnet - made up of smaller magnetic domain that all align
- Opposite poles of magnets attract
- If you take a free spinning magnet and put a magnet to the side of it, it will spin until the opposite poles of the spinning magnet and still magnet align
- Electromagnet - when you take a metal core and wrap a current carrying wire around it, it causes the magnetic domains within the core to align, similar to the alignment in a permanent magnet
  - Can be turned on or off if the current is supplied or not supplied
  - Reversing the polarity - changing the direction of current causes the direction of the poles to change

## Motors

- Take the spinning bolt and place two magnets on the side of it, this will cause it to spin as long as the wires that connect to the battery keep flipping
- Replace the bolt with a shaped wire called an armature and replace the magnets on the side with curved magnets so that it looks like this:

[IMAGE: Motor armature and magnets]

- Connecting the wires created a flat electromagnet such as the one shown below:

[IMAGE: Motor electromagnet]

- Connect the armature to a metal ring called a commutator and then attach brushes, which are not actually brushes, but spring-loaded pieces of metal that will stay in contact with the commutator
- The gap in the commutator allows for the brushes to change the direction of current once they pass over the gap
- You can add more armatures to increase the performance of the motor

[IMAGE: Multiple armatures]

- To increase the torque of the motor, you can:
  - Increase the number of wires (armatures)
  - Make each of the armatures made of multiple wires
  - Use more current/voltage
- The parts that do not move are called the stator - these are the permanent magnets on the side
- The armature is also called the rotor
- The axle is what sticks out of the motor and lets you connect things

The full DC motor can be seen here:

[IMAGE: Full DC motor]

## Types of Motors

### Brushed

- These motors are the ones discussed in the video
- Consists of a stator, commutator, and brushes
- The iron core is not necessary as some may be coreless (where the wires are suspended on nothing)
- A typical brushed motor looks like this:

[IMAGE: Typical brushed motor]

- And a schematic of what the inside looks like is something like this:

[IMAGE: Brushed motor internal schematic]

- Since there is mechanical friction between the brushes and commutator (this is the electrical contact) this type of motor cannot be lubricated
- The brushes and commutator will wear over the lifetime of the motor, meaning eventually the entire thing will need to be replaced
- Requires periodic maintenance
- To change the direction of a brushed motor, an H-bridge needs to be used (simple speed control)

#### Benefits

- High starting torque - ideal for applications that need to get up to speed quickly
- Low cost

#### Advantages

- Medium speed and acceleration
- Medium efficiency
- Low cost

#### Disadvantages

- Short lifetime
- High electrical noise
- Poor acoustic noise and torque ripple

#### Uses

- Toys
- Automatic car windows
- Power tools
- Paper machines
- Car seat adjustment controls
- Cranes
- Steel rolling mills

#### Sources

- https://www.pelonistechnologies.com/fundamentals-of-brushed-dc-motors
- https://www.monolithicpower.com/en/learning/resources/brushless-vs-brushed-dc-motors

### Brushless

- Operate on the same principles as brush motors, but are constructed differently
- The magnetic field of the stator is rotated by electronic communication
- Requires active control electronics
- The rotor has permanent magnets connected has windings attached to the stator
- Can be constructed in two ways
  - With the rotor inside
  - With the rotor on the outside of the windings (called an outrunner motor)
- The number of windings uses is called the number of phases
  - Can be constructed with different number of phases but typically is three
- The three windings are connected in either a star or delta configurations
  - This has no impact on the drive technique and waveforms
- Can be constructed with different magnetic configurations called poles
- Simplest have 2 poles
- High speeds are better accomplished with 2 poles
- To drive a three-phase motor, each phase needs to be drive by input supply voltage or ground
  - To do this, three half-bridge drive circuits are used which consists of two switches as opposed to the four present in an H-bridge
  - This circuit is shown below:

[IMAGE: Three-phase brushless motor drive circuit]

#### Drive Techniques

- Trapezoidal, block, or 120-degree communication
  - At any given time, one of the 3 phases is connected to ground, one is connected to supply voltage, and one is left open
  - If speed or torque needs to be controlled, the phase connected to the supply is pulse width modulated
  - Since phases are switched abruptly, there is some variation in torque as the motor rotates - called torque ripple
  - No sophisticated control electronics needs
    - Simple combinational logic
- Sine or 180-degree communication
  - used for higher performance as it drives current through all three phases at the same time
  - The drive electronics generates a sinusoidal current through each phase that is shifted 120 degrees from the other
  - Minimizes torque ripple, acoustic noise, and vibration
  - Used for high performance or high efficiency drives
  - Control electronics need to now the physical position of the magnets on the rotor relative to the stator
    - Position found using Hall sensors mounted to the stator
  - Sophisticated control electronics required (microcontroller)

#### Advantages

- Long lifetime
- High speed and acceleration
- High efficiency
- Quite electrical noise
- Medium to good acoustic noise and torque ripple

#### Disadvantages

- Adds electronics and cost

#### Uses

- Automobile
- Household appliances
- Industrial field
- Medical devices
- Aerospace
- Aeromodelling
- Any field in which long lifetime and minimal maintenance are required

#### Sources

- https://www.monolithicpower.com/en/learning/resources/brushless-vs-brushed-dc-motors
- https://www.omc-stepperonline.com/support/what-are-the-typical-applications-of-brushless-dc-motor

### Coreless

- The same as a DC brushed motor except it does not contain an iron core in the rotor
- The same applies for a DC brushless motor

#### Classification of Coreless Motors

- Single-phase induction motor - rotor has one winding and is attached to phase of the voltage supply
- Three-phase induction motor - rotor has three windings attached to the delta connection

#### Working Principles

- An epoxy material is attached to the rotor to replace the core
  - Hardens the coils so they are not damaged
- Stator is made of earth magnets and stays on the inner side of the motor
- Brushes and commutator are used to regulate current

#### Advantages

- Lighter weight
- Smaller size
- Less noise
- Increased efficiency
- Less sparking
- Low current consumption
- Fast and smooth operation

#### Disadvantages

- More expensive
- Thermal overloads
- Additional electronics (decoders)

#### Applications

- Lightweight and high-speed devices
- Medical devices
- Robotics
- Actuators

#### Sources

- https://www.progressiveautomations.com/blogs/products/cored-vs-coreless-dc-motors-which-should-you-choose
- https://assunmotor.com/blog/dc-coreless-motor/

### Stepper

- The shaft rotates by performing steps; moving a fixed amount of degrees
- Stator has teeth on which the coils are wired
- Rotor is either a permanent magnet or a variable reluctance iron core
- The cross-sections looks as such:

[IMAGE: Stepper motor cross-section]

- By energizing one or more of the stator phases, a magnetic field is generated and the rotor aligns with this field
- This motion can be seen here:

[IMAGE: Stepper motor motion]

#### Rotor Types

- Permanent magnet - guarantees a good torque and detent torque; motor will resist any change in position
  - Drawbacks: lower speed and lower resolution
- Variable reluctance - made of an iron core and specific shape that allows it to align with the magnetic field
  - Drawbacks: lower torque and no detent torque
- Hybrid - combination of variable reluctance and permanent magnet
  - Has two caps with alternating teeth
  - Magnetized axially

#### Advantages

- High resolution
- High speed
- High torque

#### Disadvantages

- More complex construction thus higher cost

#### Stator

- Main characteristics are number of phases and pole pairs and wire configuration
- Two-phase motors are most common and three- and five-phase motors are less common

## Control

- Transistor bridge physically controls the electrical connection to the motor coils
- Pre-driver is a device that controls the activation of the transistors and is controlled by the MCU
- Microcontroller generates specific signals for the pre-driver

Motor schematic:

[IMAGE: Stepper motor schematic]

### Driver Types

- Step/direction - sending a pulse on the Step pin causes the motor to perform a step in the direction determined by the level of the direction pin
- Phase/enable - for each stator winding phase, Phase determines the current direction and triggers Enable if the phase is energized
- PWM - directly controls the gate signals on the low and high side FETs
- Unipolar motor - one of the leads is connected to the central point of the coil
  - Allows the direction of current to be easily controlled using a simple circuit and components
  - Only half the copper is used in the motor at a time; magnetic field is at half strength

Unipolar driving circuit:

[IMAGE: Unipolar driving circuit]

- Bipolar motor - each coil has only two leads available and to control the direction, an H-bridge must be used

Bipolar driving circuit:

[IMAGE: Bipolar driving circuit]

### Driving Techniques

- Wave mode - only one phase is energized at a time, results in 90º rotations
- Full-step mode - two phases are energized at the same time, higher torque
- Half-step - combination of wave and full-step modes and allows the step size to be reduced to 45º
- Micro-stepping - further enhancement of the half-step mode as the step size can be reduced even more

### Advantages

- Do not require a sensor to detect motor position
- Control is simple
- Good torque at low speeds

### Disadvantages

- Can miss a step if load torque is too high
- Inefficient and overheating due to constantly draining maximum current even when not rotating
- Low torque and noisy at high speeds
- Low power density and low torque to inertia ratio

### Applications

- Printers
- 3D printers
- Robotic arms
- DSLR camera apertures
- Video cameras
- Engraving machines
- ATM machines

#### Source

- https://www.monolithicpower.com/en/learning/resources/stepper-motors-basics-types-uses

## Motor Comparison Table

| Motor Type | Key Features | Best For | Drawbacks | Additional |
|---|---|---|---|---|
| Brushed | Uses brushes and commutator to control speed | Cheap applications where lifespan is not an issue | Short lifespan; noisy; high torque ripple | See notes |
| Brushless | Does not have brushes, but rather rotates the magnet instead of the wires | Applications in which lifespan is important and where noise (electrical and acoustic) is a great issue | Requires additional electronics to run properly, adding to costs | See notes |
| Coreless | Lacks an iron core and holds together the shape by using epoxy | Applications where weight is a great factor but thermals are not | Expensive; requires decoders to work properly; thermal overloads | See notes |
| Stepper | The magnet moves in steps and this allows for the position of the magnetic field to be known at all times; allows for an understanding of how far the device has travelled | Applications in which knowing how far the device has travelled or rotated in crucial | Steps can be missed if the torque is too high; low torque and noisy at high speeds; constantly drains maximum current | See notes |

## Best Motor

- Based on all of this information, the best motor to use in the micro mouse is the coreless motor.
- This is because the coreless mouse has the best benefits specifically for the mouse while having very little drawbacks.
- The benefits are the lightweight and high torque output of the motor, allowing for the mouse to move faster and not have the weight of the motor limit the speed of the mouse as much. Furthermore the low current consumption also allows it to be connected to the MCU with relative ease.
- The drawbacks such as cost and thermal overloads are somewhat justified; however, the potential gain in performance by using a coreless motor outweigh the issues of cost and the thermal issue should not be a big deal since the motors will be running at high speeds for only a short period of time.
- The issue of decoders is not an issue at all as they are not too difficult to implement and should not take up too much room on the PCB and will not require a strenuous amount of code to function properly.
