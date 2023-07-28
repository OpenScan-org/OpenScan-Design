# OpenScan - 3D Scanner Designs

Here you can find, discuss and improve the existing 3d scanner designs (and current developments). The inital version was created in SketchUp and we plan on re-creating the OpenScanners in proper CAD software. If you are able to "translate" the designs into some other, more accessible format, you can also share it here.


## OpenScan Mini V1
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanMini.jpg?raw=true)

The OpenScan Mini is the smallest version of the scanners. It has an approx. scan volume of a sphere with radius of 9cm, perfect for small and detailed parts. It features a built-in LED lighting and polarizers to uniformly illuminate parts and to supress reflections.
Version 1 is the current release with configured OpenScan software and which is described in the documentation.

## OpenScan Mini v2 RC1
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanMiniV2Beta.jpg?raw=true)

A Beta version of version 2 is also available. We have seen various user mods to add functionality to the OpenScan platform. We aim to incorporate as many user mods as possible in the new design and to make it more user-friendly to add mods. The idea is to increase printability, stability and stiffness, include mounting options for user mods, and allow modular use of various cameras and lightings.
The beta design of version 2 is aimed for the OpenScan Shield version 2 but can also be used for version 1 (when printing a fitting enclosure for the version 1 OpenScan Shield). The BOM will be different from v1:

### Essential BOM

| Part | Amount | Short Description |
| :--- | :---: | :---: |
| M3x8mm SHCS/BHCS | 8+3 | Nema17 motors, shield cover |
| M3x16mm SHCS/BHCS | 4 | cam holder and cam cover |
| M3x40mm+ SHCS/BHCS | 1 | mounting camholder to rotor, any M3 equal or longer than 40mm will work, M3x65mm would be perfect, see non-essential BOM |
| Heat Inserts M3x4x5 | 3+1+4 | so-called "Voron" inserts for base, rotor, and cam mount, requires a solder iron to melt them in |
| M2.5x10mm standoff | 4 | fixating v2 shield to shield cover |
| M2.5x10mm SHCS | 4 | fixating rpi and rpi cover to shield cover |
| lubricant | 1-2 ml | lucricant that doesn't dissolve printed parts, ie white lithium grease, for cog wheel and rotor |

### Non-Essential BOM (Luxury and tinkerer upgrades)
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| microswitch w or w/o lever | 1 | endstop: standard microswitch found in many 3D printers, quality ones prefered (eg Omron D2FC) |
| M1.6x12 (self-tapping optional) | 2 | endstop: through the endstop and directly into plastic of the base, self-tapping screws also work great |
| Heat Inserts M3x4x5 | 2 | mounting points: eg for lighting dome mod |
| M3x15mm standoff | 2 | mounting points: will replace two M3x8 from turntable. eg for light dome mod |
| F692 (2x6x3) mm | 3 | rotor guide: bearing with flange, will guide the rotor, reduce wobble and friction |
| M2x12 SHCS/BHCS | 3 | rotor guide: will fixate the bearings in the base |
| M3x65mm SHCS/BHCS | 1 | mounting camholder to rotor, put a heat insert on the *opposite* side of the rotor, extra stiffness |
| Fan 3010 or 3007 | 1 | motors and drivers are producing heat which can soften PLA (and PETG) over time, a fan helps to prevent that, 3V3, 5V or 12V |
| M3x14 SHCS/BHCS | 4 | for mounting the fan into the housing |
| M3 nuts | 4 | for mounting the fan into the housing |



## OpenScan Classic
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanClassic.jpg?raw=true)

The OpenScan Classic is for larger objects and potential usage of external cameras. The Classic is scaled to fit much larger items. It very much functions the same as the Mini, except the camera is in a fixed position and the object is rotated and tilted. 


# User Mods for OpenScan Scanners
You can actively helping with designing the OpenScan Scanners and provide user mods for others. We have seen many design tweaks and changes from various users on Thingiverse and other platforms. Unfortunately, the user mods on other platforms are slowly getting lost or are not up-to-date. Here, we want to provide a platform for you to exchange your user mods and also provide the option to curate mods so they are not getting lost in time and space. 

## Design "rules"
We recommend to stick to common design rules of 3D-printing. A user mod has the largest impact when it helps users the must and that typically includes the easyness of manufacturing, 3D printing and maybe sourcing the hardware parts like screws and heat inserts. When designing a part, printability should always be in the back of your mind, i.e., try to provide angles larger than 45° and, if not preventable, try to include support structures already in the model so that other users will have an easier time printing. The designed part should also be rotated such that is ready to print. For hardware parts, try to stick for parts that are commonly used in 3D printing, e.g. metric screws like M3x8mm, heat inserts like in Voron and other printers, or bearings like from skateboards or Bontech idlers.

## How to contribute Designs and provide  Mods
If you are familiar to github, then you probably already know how to contribute in projects. In case you are new to github, the way would be to create an account, create your own fork of the project (fork = personal copy you can edit), then you can add (and/or change) user mods (user mods have a dedicated folder). Finally, you can create a pull request of your changes and user mods to the official OpenScan Project. After checking and approving your report and pull request, your user mods will be listed in the official github page. If you are unsure about the whole process or simple want to share a single STL with the community, you can also ask for help on our discord channel. The curators of the github project can help you there.

