# OpenScan - 3D Scanner Designs

Here you can find, discuss and improve the existing 3d scanner designs (and current developments). The inital version was created in SketchUp and we plan on re-creating the OpenScanners in proper CAD software. If you are able to "translate" the designs into some other, more accessible format, you can also share it here.


## OpenScan Mini V1
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanMini.jpg?raw=true)

The OpenScan Mini is the smallest version of the scanner. It has an approx. scan volume of a sphere with a diameter of 8-9cm, perfect for small and detailed parts. It features built-in LED lighting and polarizers to uniformly illuminate parts and to suppress reflections.
Version 1 is the current release with configured OpenScan software, which is described in the documentation. All hardware kits sold with the current kits are for the Mini V1 and the Classic

## OpenScan Mini V2 
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanMiniV2.jpg?raw=true)

Version 2 is also available. We have seen various user mods to add functionality to the OpenScan platform. We aim to incorporate as many user mods as possible in the new design and to make adding mods more user-friendly. The idea is to increase printability, stability, and stiffness, include mounting options for user mods, and allow modular use of various cameras and lighting.
The design of version 2 is aimed at the OpenScan Shield Version 2 ("black shield", not released yet, for info, visit the Discord channel) but can also be used for the current "green shield". The BOM is slightly different from V1, various screws can be recycled, and the remaining is not exotic:

Head over to the building instructions in the Documentation: 

### Essential BOM

| Part | Amount | Short Description |
| :--- | :---: | :---: |
| M3x8mm SHCS/BHCS | 8+3 | Nema17 motors, base cover |
| M3x10mm SHCS/BHCS | 4 | base imaging unit (IU) and cover |
| M3x40mm+ SHCS/BHCS | 1 | mounting IU to rotor, any M3 equal or longer than 40mm will work, M3x70mm would be perfect, see non-essential BOM |
| Heat Inserts M3x4x5 | 3+1+4 | so-called "Voron" inserts for base, rotor, and cam mount. Must be 5mm diameter! 4.6mm diameter will not sit securely. They require a soldering iron to melt them in. |
| M2.5x10mm standoff | 4 | fixating (black) shield to base cover, screwed directly into plastic |
| M2.5x10mm SHCS | 4 | fixating RPI and RPI cover to base cover |
| lubricant | 2-3 ml | lubricant that doesn't dissolve printed parts, ie, white lithium grease, for cog wheel |

### Non-Essential BOM (Luxury and tinkerer upgrades)
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| microswitch w or w/o lever | 1 | endstop: standard microswitch found in many 3D printers, quality ones prefered (eg Omron D2FC) |
| M1.6x12 (self-tapping optional) | 2 | endstop: through the endstop and directly into the plastic of the base, self-tapping screws work better |
| Heat Inserts M3x4x5 | 2 | mounting points: eg for lighting dome mod |
| M3x15mm standoff | 2 | mounting points: will replace two M3x8 from turntable. eg for light dome mod |
| F692 (2x6x3) mm | 4 | rotor guide: bearing with flange, will guide the rotor, reduce wobble and friction |
| M2x12 SHCS/BHCS | 4 | rotor guide: will fixate the bearings in the base |
| M3x70mm SHCS/BHCS | 1 | mounting cam holder to rotor, put a heat insert on the *opposite* side of the rotor, extra stiffness |
| Fan 3010 or 3007 | 1 | motors and drivers are producing heat which can soften PLA (and PETG) over time; a fan helps to prevent that; 3V3, 5V or 12V |
| M3x14 SHCS/BHCS | 4 | for mounting the fan into the housing |
| M3 nuts | 4 | for mounting the fan into the housing |


## OpenScan Midi
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanMidi.jpg?raw=true)

A scaled-up version of the Mini allows for larger objects to be scanned. The scanning volume is approx. a sphere with 14-15cm diameter. This is the largest size before the flat cable for the camera slowly loses signal integrity, resulting in occasional camera hiccups. The Midi uses the same BOM as the Mini V2.
The rotor has a diameter of 30cm and is too large for many build plates. Thus, a segmented version is also provided. The segments slide into each other and are fixated afterwards with filament pieces through the 9 holes (and a little CA glue if necessary) or via M2/M2.5 grub screws of approx length 10mm. The large rotor benefits from the non-essential bearing upgrades.

## OpenScan Classic
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanClassic.jpg?raw=true)

The OpenScan Classic is for larger objects and potential usage of external cameras. The Classic is scaled to fit much larger items. It very much functions the same as the Mini, except the camera is in a fixed position and the object is rotated and tilted. 

# User Mods for OpenScan Scanners
You can actively help design the OpenScan Scanners and provide user mods for others. We have seen many design tweaks and changes from various users on Thingiverse and other platforms. Unfortunately, the user mods on other platforms are slowly getting lost or outdated. Here, we want to provide a platform for you to exchange your user mods and the option to curate mods so they are not getting lost in time and space. 

## Design "rules"
We recommend sticking to common design rules of 3D printing. When designing a part, printability should always be in the back of your mind, i.e., try to avoid angles larger than 45° and, if not preventable, try to include support structures already in the model so that other users will have an easier time printing. The designed part should also be rotated such that it is ready to print. For hardware parts, try to stick for parts that are commonly used in 3D printing, e.g., metric screws like M3x8mm, heat inserts like in Voron and other printers, or bearings like from skateboards or Bontech idlers.

## How to contribute Designs and provide  Mods
If you are familiar with Git Hub, you already know how to contribute to projects. In case you are new to GitHub, the way would be to create an account, create your fork of the project (fork = personal copy you can edit), then you can add (and/or change) user mods (user mods have a dedicated folder). Finally, you can create a pull request of your changes and user mods to the official OpenScan Project. After checking and approving your report and pull request, your user mods will be listed on the official GitHub page. If you are unsure about the whole process or simply want to share a single STL with the community, you can also ask for help on our Discord channel. The curators of the GitHub project can help you there.

