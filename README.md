# OpenScan - 3D Scanner Designs

Here you can find, discuss and improve the existing 3d scanner designs (and current developments). The inital version was created in SketchUp and we plan on re-creating the OpenScanners in proper CAD software. If you are able to "translate" the designs into some other, more accessible format, you can also share it here.

The documentation is separated in parts, and can be found in the /docs/ folder:

[**Printing Guide**](/docs/OpenScanV2-Part-Printing.md)

[**Assembly Guide for Mini and Midi**](/docs/OpenScanV2-Assembly.md)

[**Electronics Guide for green and black shield**](/docs/OpenScanV2-Electronics.md)


# OpenScan Mini V1
![Scanner](/images/OpenScanMini.jpg?raw=true)

The OpenScan Mini is the smallest version of the scanner. It has an approx. scan volume of a sphere with a diameter of 8-9cm, perfect for small and detailed parts. It features built-in LED lighting and polarizers to uniformly illuminate parts and to suppress reflections.
Version 1 is the current release with configured OpenScan software, which is described in the documentation. All hardware kits sold with the current kits are for the Mini V1 and the Classic

# OpenScan Mini V2.X
![Scanner](/images/OpenScanMiniV2.jpg?raw=true)

Version 2 is also available. We have seen various user mods to add functionality to the OpenScan platform. We aim to incorporate as many user mods as possible in the new design and to make adding mods more user-friendly. The idea is to increase printability, stability, and stiffness, include mounting options for user mods, and allow modular use of various cameras and lighting.
The design of version 2 is aimed at the OpenScan Shield Version 2 ("black shield", not released yet, for info, visit the Discord channel) but can also be used for the current "green shield". The BOM is slightly different from V1, various screws can be recycled, and the remaining is not exotic.

## BOM V2.0

[**BOM V2.0**](/docs/BOM-V2.0.md)

## BOM V2.1 + V2.2

[**BOM V2.1**](/docs/BOM-V2.1.md)

# OpenScan Midi V2.X
![Scanner](/images/OpenScanMidi.jpg?raw=true)

A scaled-up version of the Mini allows for larger objects to be scanned. The scanning volume is approx. a sphere with a 16cm diameter. This is the largest size before the flat cable for the camera slowly loses signal integrity, resulting in occasional camera hiccups. The Midi uses the same BOM as the Mini V2.
The rotor has a diameter of 30cm and is too large for many build plates. Thus, a segmented version is also provided. The segments slide into each other and are fixated afterwards with filament pieces through the 9 holes (and a little CA glue if necessary) or via M2/M2.5 grub screws of approx length 10mm. The transition of the segments must not have imperfections which could otherwise get caught in the cog wheel or brearing flanges. The large rotor benefits from the non-essential bearing upgrades to reduce wobble.

## BOM V2.0

[**BOM V2.0**](/docs/BOM-V2.0.md)

## BOM V2.1 and V2.2

[**BOM V2.1**](/docs/BOM-V2.1.md)


# OpenScan Classic
![Scanner](/images/OpenScanClassic.jpg?raw=true)

The OpenScan Classic is for larger objects and potential usage of external cameras. The Classic is scaled to fit much larger items. It functions the same as the Mini, except the camera is in a fixed position and the object is rotated and tilted. 

# User Mods for OpenScan Scanners
You can actively help design the OpenScan Scanners and provide user mods for others. We have seen many design tweaks and changes from users on Thingiverse and other platforms. Unfortunately, the user mods on other platforms are slowly getting lost or outdated. Here, we want to provide a platform for you to exchange your user mods and the option to curate mods so they are not getting lost in time and space. 

## Design "rules"
We recommend sticking to common design rules of 3D printing. When designing a part, printability should always be in the back of your mind, i.e., try to avoid angles larger than 45° and, if not preventable, try to include support structures already in the model so that other users will have an easier time printing. The designed part should also be rotated such that it is ready to print. For hardware parts, try to stick for parts that are commonly used in 3D printing, e.g., metric screws like M3x8mm, heat inserts like in Voron and other printers, or bearings like from skateboards or Bontech idlers.

## How to contribute Designs and provide Mods
If you are familiar with Git Hub, you already know how to contribute to projects. In case you are new to GitHub, the way would be to create an account, create your fork of the project (fork = personal copy you can edit), and then you can add (and/or change) user mods (user mods have a dedicated folder). Finally, you can create a pull request of your changes and user mods to the official OpenScan Project. After checking and approving your report and pull request, your user mods will be listed on the official GitHub page. If you are unsure about the whole process or want to share a single STL with the community, you can also ask for help on our Discord channel. The curators of the GitHub project can help you there.

