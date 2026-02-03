# BOM V2.4

Mini and Midi are using the exact same BOM for the basic hardware parts. The only difference in the required parts is the length of the needed electronics cables, i.e. ring light cable and camera cable.

## Essential BOM V2.4

| Part | Amount | Short Description |
| :--- | :---: | :---: |
| M3x8mm SHCS/BHCS | 8+3+4 | Nema17 motors, base cover, imaging unit (IU) |
| M3x40mm+ SHCS/BHCS | 1 | mounting IU to rotor, any M3 equal or longer than 40mm will work, M3x70mm would be perfect, see non-essential BOM |
| Heat Inserts M3x4x5 | 3+1+4 | sometimes called "Voron" inserts for base, rotor, and cam mount. Must be 5mm diameter! 4.6mm diameter will not sit securely. They require a soldering iron to melt them in. |
| M2.5x18mm standoff *female-female* | 4 | standoffs sandwiched between RPi and black shield |
| M2.5x10mm SHCS | 8 | fixating RPi, shield, electronics cover and base cover |
| M2x8mm SHCS | 2 | optional screws for fixating camera if friction fit is not enough |
| lubricant | 2-3 ml | lubricant that doesn't dissolve printed parts, i.e., white lithium grease, for cog wheel |

## Non-Essential BOM (Luxury and tinkerer upgrades)

### Endstop
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| microswitch w or w/o lever | 1 | endstop: standard microswitch found in many 3D printers, quality ones prefered (e.g. Omron D2FC) |
| M1.6x12 or M2 self-tapping | 2 | endstop: fixating the endstop, screw directly into the plastic |

### Lighting Dome
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| Heat Inserts M3x4x5 | 2 | mounting points: for lighting dome mod |
| M3x35mm SHCS/BHCS | 2 | mounting points: will replace two M3x8 from turntable, for lighting dome mod, sandwich dome mod adapter  |
| M3x12mm SHCS/BHCS | 2 | for lighting dome mod, fixating the dome and adapter to the base |

### Anti-wobble Rotor
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| stripes of satin/velvet sheets | 3-5 | glue 5-10mm wide stripes of 0.5mm thickness satin along rotor, strong dampening effect, reduce rotor wobble |

### Sturdy IU mounting
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| M3x70mm SHCS/BHCS | 1 | mounting IU to the rotor, put a heat insert on the *opposite* side of the rotor, extra stiffness |

### CSI Cable Extender
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| CSI Cable Extender | 1 | the extender should respect the pin flip, e.g. adafruit extender or Black Shield Extender |
| M3x8mm SHCS/BHCS | 2 | fixating CSI cable extender to base |
| M3 nuts | 2 | fixating CSI cable extender to base |

### Cooling Fan
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| Fan 3010 or 3007 | 1 | motors and drivers are producing heat which can soften PLA over time; 3V3, 5V, or 12V |
| M3x14 SHCS/BHCS | 4 | for mounting the fan into the housing |
| M3 nuts | 4 | for mounting the fan into the housing |
