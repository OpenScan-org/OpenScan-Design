# Part Printing Guide

The OpenScan devices come in different flavors. The Mini is the typical al-in-one version for smaller objects up to 8-9cm in diameter. The Midi is the larger sister when going for larger objects up to approx 15cm in diameter. The classic allows for easy use of DSLR and mirrorless cameras, which can increase the scan quality (at the expense of owning rather expensive additional equipment). The Mini and Midi come with support of the green shield (V1) and black shield (V2). The classic is currently missing a good looking integration of the black shield (only aesthetics). All parts are located in their corrspondingly named folder. Every part has a preceding number, e.g. "1-base.stl" to help you structure your printing and building process. Some parts come in different variants, e.g. the rotor as unibody part or segmented in two or three, all labeled with "3-..." as preceding number. This indicates that you only need *one* variant of this part. For a full set of parts, you have to print all parts of the corresponding folder for the corresponding model, i.e.

| Version | Needed Parts (incl. Links) |
| :---: | :---: |
| Mini V1 (still going strong) | [**Base Parts Mini V1**](../files/Mini/V1/) and [**Turntables**](../files/turntables/Mini_and_Classic/)|
| Mini V2.2 (fading out) | [**Base Parts Mini V2.2**](../files/Mini/V2.2/) and [**Imaging Unit**](../files/Imaging-Unit/) and [**Turntables**](../files/turntables/Mini_and_Classic/)|
| Mini V2.3 | [**Base Parts Mini V2.3**](../files/Mini/V2.3/) and [**Imaging Unit**](../files/Imaging-Unit/) and [**Turntables**](../files/turntables/Mini_and_Classic/)|
| Midi V2.2 (fading out) | [**Base Parts Midi V2.2**](../files/Midi/V2.2/) and [**Imaging Unit**](../files/Imaging-Unit/) and [**Turntables**](../files/turntables/Midi/)|
| Midi V2.3 | [**Base Parts Midi V2.3**](../files/Midi/V2.3/) and [**Imaging Unit**](../files/Imaging-Unit/) and [**Turntables**](../files/turntables/Midi/)|
| Classic V1 | [**Base Parts Classic V1**](../files/Classic/V1/) and [**Turntables**](../files/turntables/Mini_and_Classic/)|

Also, have a look at the [**Usermods**](../usermods/).

## Print settings and material
The deives was designed with FDM printing in mind. The device should be sturdy since it has some heavy and moving parts attached and the electronics is also generating some heat. Generally, 3-4 walls, 5-6 top and bottom layers, 30-40% infill cuboid/gyroid/hex/grid is recommended. Importantly, all critical dimensions for tolerances and clearances are a multiple of 0.2mm, thus **a layer height of 0.2mm is highly recommended** for proper functionality. All parts are print-in-place.
It is recommended to use a smooth or satin print surface. **Heavily structured print surfaces, such as powder-coated, will impact the dimensional accuracy of the rotor height.** This can cause additional friction or improper alignment.
The cogwheel/gear for the rotor motor might have an over- or undersized center hole, depending on your printer settings and capabilities. *It is recommended to print out this gear in three sizes, 95%, 100%, and 105%*, to ensure that one of the gears fits. The gear should fit snugly in the shaft with sufficient friction to hold it in place, but should not require excessive force to seat it. Alternatively, you can print out cogwheels/gears with varying (inner) hole/perimeter compensation in your slicer settings, which slightly expands or contracts holes of a model.

While it is okay to use PLA, PLA can slowly deform under the warmth and weight of the motors, when having multiple long scanning sessions in warm environments. Thus, it is recommended to use PETG or ABS/ASA (if your printer can reliably print those). Further, when using PLA, it is highly recommended to reduce the V_ref of the drivers to 0.5V to limit the heat generation.
As for color, a matte and dark color is recommended for all, but the translucent polarizer part. This simplifies the process of cutting out background in the images. The translucent polarizer part should be printed in a material that lets through light. Transparent PETG works good or "natural" colored PLA and ABS/ASA that contain very few pigments work great.
SLA resin is not recommended since many resins do not have the ductility or heat resistance (but users made it work).

## Built-in bridging help for V2 versions
![Scanner](/images/bridging-help.png?raw=true)
The V2.X parts are designed as print-in-place, i.e., no part re-orientation or supports are required. When supports are needed, then they are already modeled into the files.
The V2's have included bridging helpers so your printer always takes the shortest bridging path when printing the rotor housing. This remedies the issue with many slicers when printing long but narrow overhang bridges of curved surfaces. No more screwed up bridges because a slicer had a bad day. **You do not need additional, slicer generated supports for the V2 models**. 

## Finished Printing
When all parts are printed, go over to the [**Electronics Start-up guide**](/OpenScanV2-Electronics.md) and confirm that the electronics is working properly. You can then continue with the [**Assembly guide**](/OpenScanV2-Assembly.md).
