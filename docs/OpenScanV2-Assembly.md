# Building Manual OpenScan Mini & Midi V2

![Scanner](../images/OpenScanMiniV2.png?raw=true)

# Intro

Various parts and hardware were updated from V1 to V2 to improve rigidity and user-friendliness, especially in printing. No more part orientation and support structure settings in your slicer. Just print-in-place parts. The V2 design natively supports the V2 shields ("black shield"), which are currently inofficially available as a prototype on Discord.  

V2 also uses heat inserts M3x4x5 (thread size x length x outer diameter), widely popularized in 3D printing, especially in Voron-style printers. For them, a *soldering iron* with a spare (or sacrificial) tip or special heat insert tip is required. Make-shift solutions with M3 bolts and lighter are not recommended due to the serious risk of burning your fingers.
All other hardware parts, such as RPi and Arducam IMX519, have not changed from the V1.

**have a look at the [**Assembly Photo Guide**](../images/assembly/) under ../images/assembly/ ! A kind user shared an extensive collection of assembly photos**


# Printing and preparing the parts

All V2 parts are designed as print in place, i.e., no part re-orientation or supports are required. When supports are needed, then they are already modeled into the files. The recommended print settings are 4 perimeters and approx. 40% cubic infill. *Printing with 0.2mm layer height is highly recommended* because all dimensions and clearances of the parts are modeled as multiples of 0.2mm! Also, the rotor height is critical when you want to use the optional bearing upgrade. If you print the rotor on a powder-coated sheet, it will be slightly wider than anticipated. *Printing the rotor on a smooth or satin sheet is recommended*.
The parts should be printed in *PETG or ABS/ASA* if your printer can handle it. PLA can also work, but due to the enclosed design, excessive heat from the motors and drivers can slowly deform PLA in the long term. When printing PLA, the motor currents MUST be adjusted to a working minimum to prevent heat creep of PLA (approx. 0.5A).
The cogwheel/gear for the rotor motor might have an over- or undersized center hole, depending on your printer settings and capabilities. *It is recommended to print out this gear in three sizes, 95%, 100%, and 105%*, to ensure that one of the gears fits. The gear should fit snugly in the shaft with sufficient friction to hold it in place.

![Scanner](../images/bridging-help.jpg?raw=true)

Some parts have overhangs and bridges, and dangling filament parts should be cleaned. Take special notice of the base part since sacrificial bridges are modeled into it. Those intentional bridges are for helping your slicer slice and properly place bridges in the arced overhang for the rotor. The sacrificial bridges around the bearing insert points should be removed carefully to be able to insert bearings later on. Those bridges can be left untouched when not planning on using bearings at all.
As a last step, all required heat inserts should be appropriately set. Please take a look at the images below. Orange spots are mandatory heat inserts, and yellow spots are optional heat inserts for mods.

## Base

![Scanner](../images/heatinserts-base.png?raw=true)
![Scanner](../images/heatinserts-base-2.png?raw=true)

Three inserts for the side cover are required. The additional ones at the bottom are for fixating the scanner to a table or optional turntable holder platform. The two optional ones on the top are for the light dome mod for more uniform illumination.


## Rotor

![Scanner](../images/heatinserts-rotor.png?raw=true)

*Only melt in ONE heat insert, depending on your available M3 bolt length!* M3x70 is recommended since it gives the most stability and secure fixation, but M3x70 is sometimes hard to source. If you have an M3x70, melt in the heat insert on the side with the little endstop nose. If you cannot source an M3x70 for a reasonable price (or low quantity), pick the longest M3 you can find. Instead, melt the heat insert into the conical side, labeled with M3x40.

## Imaging Unit Cover

![Scanner](../images/heatinserts-IU-cover.png?raw=true)

Melt in four heat inserts as indicated. Try to leave the small ridges around the insertion point intact. They will help align the camera module later. There are some closed cut-outs. You have to remove the one that suits your JST-XH connector you solder onto (or you break away all cut-outs, you monster).

# Assembly

When all parts are printed and prepared, assembly is mainly straightforward. The STEP file I've shared here provides a 3D model of the whole assembly. Here is roughly a step-by-step assembly:

## Rotor

- (Segmented rotor) If you print the segmented rotor, the pieces should slide firmly into each other. If it does not slide well enough, take some fine sanding paper and sand the center fin a little, and try again. 

- (Segmented rotor) The nine holes of the segments should align. You can either guide 10mm filament pieces or 10mm M2 grub screws through the nine holes for locking the rotor parts into place. A little dab of CA glue permanently fixates them.

- (Unibody rotor) Nothing. The unibody rotor does not need further assembly.

## Base of Mini/Midi
- (Optional) Install tiny bearings with M2 screws for the rotor. They are located at the entrance and exit where the rotor is inserted. The flanges should point downwards. The tiny M2 screws screw directly into the plastic. Those screws are for straight alignment only, NOT for high clamping force, so do NOT overtighten them. 
- Install a Nema17 (preferably the 40Ncm) for the Rotor ([angled position](https://github.com/OpenScan-org/OpenScan-Design/blob/main/images/assembly/06_base_motor.JPG)). The slotted M3 holes are for proper gear meshing of the cog wheel and rotor later. Tighten the M3x8 screws only lightly at first. Add the best-fitting cog wheel/gear to the rotor Nema 17. The gear should have a reasonable friction and form fit. Check and align the motor before screwing them fully in. The cable connector might be challenging to reach if you orient them to the wrong side.

- For proper gear meshing, the height of the cog wheel on the Nema 17 shaft and the distance between the cog wheel and rotor must be adjusted. Insert the rotor into the base a little and set the position of the cogwheel on the shaft so that it aligns with the gear teeth of the rotor. Afterwards, loosen the M3 screws of the Nema 17, push the motor closer and tighten the screws again. Move the rotor forward and backward to check that the cog wheel is seated. You should be able to feel the friction of the stepper motor, 200 tiny "bumps" per rotation. 

- Optional: Installing the rotor endstop is done with either M1.6 regular or M2 self-tapping screws. Check the orientation of the end stop first so that the nose of the rotor surely hits the switch. Currently, the endstop only prevents the rotor from swooping against the base but does not use the endstop as a homing point (might change with a software update soon)

## Base Cover and Electronics Cover

- Place the shield in reverse, 2x20 connector points upwards, all remaining components downwards, onto the base cover and screw the M2.5 standoffs directly into the plastic of the cover. *They are not meant to bear large forces*. Do not overtighten them; otherwise, you strip the plastic. 

- (black shield) Insert the flat CSI camera cable into the RPi. Take care of the correct orientation since only one side has contacts. Guide the CSI cable through the slot of the black shield. Take care of proper orientation to prevent a kink in the cable.

- Place/press the RPi into the 2x20 connector carefully. The 2x20 connector has quite high friction, so take your time and do not accidentally bend the pins. Place the RPi cover on the RPi. You might have to angle it a little so that the cover does not collide with the I/O of the RPi.

- Use M2.5 screws to secure the cover to the RPI+shield assembly. Again, those should not be overtightened as they directly transfer  torque through the standoff into the plastic of the base cover.

- For now, do *not* screw the base and electronics cover to the base. We have to install some cables first, which is easier with an opened scanner. We build the Imaging Unit next.

# Imaging Unit

![Scanner](../images/ImagingUnitV2.jpg?raw=true)

- The imaging unit is a sandwich of parts, secured at the end with four M3 screws. Proper alignment before sandwiching them with screws makes the job quite easy. 

- The sandwich order from bottom to top is IU cover, camera mount (with camera), *ring light PCB*, IU frame,  camera polariser (opaque), and light polariser (translucent). Precisely like the numbering of the STL files (plus the ring light)

- Place the IU Cover in front of you. This will be the "base bread layer" of the sandwiched unit. Place the scanner base and cover next to it. You will need it soon.

- Use the screw-in OR slide-in (recommended) mount for the camera, and place and align the lens in the center of the mount. The Ardcam IMX519 has an offset of 0.4mm of its lens from the center line (Arducam's fault), which is corrected in the mounts and its screw holes. If the lens looks very offset-ish, you probably rotated the camera wrongly. If the slide-in mount feels too tight, scratch off some plastic with a screwdriver to widen the gap.

- Connect the cable to the camera. Take care of the proper orientation and *guide the cable through the slot in the scanner base first.* Then, take the IU cover and feed the flat CSI cable through the slotted hole. Again, check orientation. Lastly place the camera mount with camera onto the four screw holes. The small ridges close to the heat inserts of the IU cover should help with alignment.

- Check what JST-XH terminal, angled or straight, and ring light you have and which cut-out of the imaging unit cover you have to clear. Note, changing the terminal's orientation also changes its pinout order. Thus, the JST-XH connector pinout order has to flip, too.

- After deciding on the JST-XH terminal, carefully place the ring light PCB on the camera mount. The lens should also be in the center of the PCB. Afterwards, place the IU frame with already inserted M3 bolts onto the sandwich assembly and screw it down. The imaging part is now finished. 

## Polariser Unit

- In order to get the best quality pictures for photogrammetry, the images should not include reflections and bright spots. The simplest way to reduce reflections is to illuminate with linear polarised light, e.g. horizontally polarized, and then capture only cross-polarized light, i.e. vertically polarized light, with the camera. This is what the polarizer unit does. The opaque camera polarizer and translucent light polarizer sheet *must be aligned for cross-polarization*.

- Place a polarisation sheet in front of you and place the translucent polariser flat on top. Trace the outline with an exacto-knife, scalpel, or any sharp object. *Ideally, the orientation of the part should be parallel or perpendicular to the shape of the polariser sheet.* Cut the polariser sheet to size, including cutting out the camera hole, and glue the sheet on the outside of the translucent polariser. 

- Take the polariser sheet again and cut out a rectangular piece of 20x12mm (approx. 3/4"x 1/2") either  *parallel OR perpendicular to the outline of the already cut-out sheet* for the translucent polariser. Slide this piece into the slot of the opaque camera polariser.

- The octagonal opaque camera polariser fits into the translucent light polariser in multiple ways. *You have to press it in so that the two polarising sheets are oriented cross-polarized*. If you did not keep track of the orientation of the polarising sheets, look into a mirror in a bright room. Look through the camera polariser into the mirror and onto the light polariser. Now, slowly rotate the light polariser. It should slowly change brightness between grey and black. *When the polariser looks black, you find the cross-polarising orientation of the two polarisers.* Now press the camera polariser into the light polariser. A tiny droplet of CA glue might help to bond it together.

- Clip the polariser unit onto the IU. Done.

## Cabling, Electronics, and finishing the Build

The last step is connecting all wires and electronics to your OpenScan unit. Head over to the [electronics manual](../docs/OpenScanV2-Electronics.md) for pre-flight electronics checks. Then continue

- When you confirm that the electronics work and everything is adjusted, you can connect all the remaining wires and close the scanner.

# Modding your OpenScan
There are some user mods already available. My favorite is the illumination dome mod, which places a half-cylinder/half-sphere shell around the scanned area, minimizing auto-focus issues and smoothing illumination. You can freely share your mods on printables, Thingiverse, GitHub, or Discord. When sharing mods, ideally, you also provide print instructions, e.g., "print-in-place, N perimeters, M% infill, etc.". 




