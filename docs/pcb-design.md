# PCB Design

## Board Outline and Layer Stackups

- Having a good outline shape in place from the mechanical designer will greatly assist with the pre-layout planning stages
- Board layer stackups should be finalized before the layout starts
  - Choose materials based on key properties such as dielectric constant and dissipation factor
  - Important to select board materials based on dielectric constants, insulating qualities, moisture absorption rating, and dissipation factors

PCB Material Comparison:

[IMAGE: PCB material comparison]

## Best Practices for Schematic Setup

- Symbol spacing on the schematic sheet
- Component information such as reference designators, part numbers, values, and pin numbers
- Colors for net objects such as symbols, net lines, buses of nets, and text
- Net spacing and naming conventions

## Placing PCB Components

- Have components as close together as possible for short and direct paths
- Along circuits and power components need to be placed to make the sensitive or high-current lines as short as possible
  - Helps reduce inductance and increase signal and power integrity
  - May need to be spread apart to accommodate bus routing or thermal separation
- Place components so that they are as easily manufacturable as possible
  - Depends on what components you are using and what type of printing process is used
- Human interfaces should be accessible so they can be tested easily

## PCB Routing

- Components should be arranged in the optimum position for short and direct trace routing
- The board must be laid out so that all the nets can be completely routed
- Signal and Power Integrity
  - Short and direct high-speed transmission line routing
  - Trace width, spacing, and allowed board layers for controlled impedance routing
  - Specified trace lengths and length tolerances for matched length routing
  - Differential pair trace widths and spacing requirements
  - Width and spacing for sensitive signals such as clock and control lines
  - Via types for different nets
  - Trace widths and spacing for analog circuitry
  - Trace widths and copper weight for high-current power circuits

PCB Routing Best Practices:

[IMAGE: PCB routing best practices]

## Effective Power and Ground Planes

- Best grounding strategy is to use one or more continuous ground planes on internal layers
  - Gives protection from EMI and ensures clear signal paths, improving signal integrity
  - Avoid routing traces across any ground voids
  - Noise can result in a lack of a continuous and adjacent ground plane to a signal plane
- Ground planes need to be adjacent to signal layers in board layer stackup with high-speed routing
  - Help shield the high-speed routing from interference and provide a good reference plane for the signal return paths
- Thermal relief pads need to be used and carefully managed for power and ground connections to the planes
  - Must be wide enough to conduct high currents while eliminating those connections' chances of acting as a heat sink
- Plan power connections and split power planes carefully to ensure adequate power delivery

## Silkscreen Guidelines

- Line widths should be no smaller than 6 mils
- Font sizes should be no smaller than 50 mils
- Rename component reference designators according to a corporate grid pattern to help locate specific parts on the board
- Move and rotate the reference designators so that they are easily readable
- Include polarity and pin one marking where needed

Source:

https://resources.pcb.cadence.com/blog/2023-pcb-design-layout-guidelines-for-engineers

[IMAGE: PCB layout example]
