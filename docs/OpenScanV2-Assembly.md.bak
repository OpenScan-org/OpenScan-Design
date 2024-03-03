# Building Manual OpenScan Mini & Midi V2

![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/OpenScanMiniV2.jpg?raw=true)

## Intro
Various parts and hardware were updated from V1 to V2 to improve rigidity and user-friendliness, especially in printing. No more part orientation and support structure settings in your slicer. Just print-in-place parts. The V2 design natively supports the V2 shields ("black shield"), which are currently inofficially available as a prototype via a development channel on Discord.  

V2 also uses heat inserts M3x4x5 (thread size x length x outer diameter), widely popularized in 3D printing, especially in Voron-style printers. For them, a *soldering iron* with a spare (or sacrificial) tip or special heat insert tip is required. Make-shift solutions with M3 bolts and lighter are not recommended due to the serious risk of burning your fingers.
All other hardware parts are summarized in the following tables. Not listed items, such as RPi and Arducam IMX519, have not changed from the V1 and are omitted here.

### Essential Bill of Material (BOM)
These are the parts you need to build a Mini/Midi V2. Some M3 bolts can be recycled, but most hardware parts have changed.
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| M3x8mm SHCS/BHCS | 8+3 | for mounting Nema17 motors, base cover |
| M3x10mm SHCS/BHCS | 4 | base imaging unit (IU) and cover |
| M3x40mm+ SHCS/BHCS | 1 | mounting IU to rotor, any M3 equal or longer than 40mm will work, M3x70mm would be perfect, see non-essential BOM |
| Heat Inserts M3x4x5 | 3+1+4 | coined "Voron" inserts for base, rotor, and imaging unit. They require a soldering iron to melt them in. It must be 5mm in diameter! 4.6mm diameter will not fit securely.  |
| M2.5x10mm standoff | 4 | female-male standoffs, fixating (black) shield to base cover, screwed directly into plastic, brass recommended |
| M2.5x10mm SHCS | 4 | fixating RPI and RPI cover to base cover |

### Non-Essential BOM (Luxury and tinkerer upgrades)
These parts are not needed for a functioning V2 but might make life here and there a little easier. This list is mainly based on many user mods incorporated in the V2 design.
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| lubricant | 2-3 ml | lubricant that doesn't dissolve printed parts, i.e., white lithium grease, for cog wheel |
| microswitch w or w/o lever | 1 | endstop: standard microswitch found in many 3D printers, quality ones prefered (eg Omron D2FC) |
| M1.6x12 (or M2 self-tapping) | 2 | endstop: through the endstop and directly into the plastic of the base, self-tapping screws work better |
| Heat Inserts M3x4x5 | 2 | mounting points: eg for lighting dome mod |
| M3x15mm standoff | 2 | mounting points: will replace two M3x8 from turntable. e.g., for light dome mod |
| F692 (2x6x3) mm | 4 | rotor guide: bearing with flange, will guide the rotor, reduce wobble and friction |
| M2x12 SHCS/BHCS | 4 | rotor guide: will fixate the bearings in the base |
| M3x70mm SHCS/BHCS | 1 | mounting cam holder to the rotor, put a heat insert on the *opposite* side of the rotor, extra stiffness |
| Fan 3010 or similar | 1 | motors and drivers are producing heat which can soften PLA (and PETG) over time; a 30mm fan helps to prevent that; 3V3, 5V, or 12V |
| M3x16 SHCS/BHCS | 4 | for mounting the fan into the housing |
| M3 nuts | 4 | for mounting the fan into the housing |

## Printing and preparing the parts
All V2 parts are designed as print in place, i.e., no part re-orientation or supports are required. When supports are needed, then they are already modeled into the files. The recommended print settings are 4 perimeters and approx. 40% cubic infill. Printing with 0.2mm layer height is highly recommended because all dimensions and clearances of the parts are modeled as multiples of 0.2mm! Also, the rotor height is critical when you want to use the optional bearing upgrade. If you print the rotor on a powder coated sheet, then it will be slightly wider than anticipated. It is recommended to print it on a smooth or satin sheet.
The parts should be printed in PETG or ABS/ASA if your printer can handle it. PLA can also work, but due to the enclosed design, excessive heat from the motors and drivers can slowly deform PLA in the long term. When printing PLA, the motor currents MUST be adjusted to a working minimum to prevent heat creep of PLA (approx. 0.5A).
The cogwheel/gear for the rotor motor might have an over- or undersized center hole, depending on your printer settings and capabilities. It is recommended to print out this gear in three sizes, 95%, 100%, and 105%, to ensure that one of the gears fits. The gear should fit snugly in the shaft with sufficient friction to hold it in place.

![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/bridging-help.jpg?raw=true)

Some parts have overhangs and bridges. Those have to be checked, and dangling filament parts should be cleaned. Take special notice of the base part since sacrificial bridges are modeled into it. Those intentional bridges are for helping your slicer slice and properly place bridges in the arced overhang for the rotor. The sacrificial bridges around the bearing insert points should be removed carefully to be able to insert bearings later on. Those bridges can be left untouched when not planning on using bearings at all.
As a last step, all required heat inserts should be appropriately set. Please take a look at the images below. Orange spots are mandatory heat inserts, and yellow spots are optional heat inserts for mods.

### Base

![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/heatinserts-base.png?raw=true)
![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/heatinserts-base-2.png?raw=true)

Three inserts for the side cover are required. The additional ones at the bottom are for fixating the scanner to a table or optional turntable holder platform. The two optional ones on the top are for the light dome mod for more uniform illumination.

### Rotor

![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/heatinserts-rotor.png?raw=true)

*Only melt in ONE heat insert, depending on your available M3 bolt length!* M3x70 is recommended since it gives the most stability and secure fixation, but M3x70 is sometimes hard to source. If you cannot source an M3x70 for a reasonable price (or low quantity), pick the longest M3 you can find and melt it in the heat insert onto the short side, labeled with M3x40.

### Imaging Unit Cover

![Scanner](https://github.com/probably-Erwins-Cat/OpenScan-Design/blob/main/images/heatinserts-IU-cover.png?raw=true)

Melt in four heat inserts as indicated. Try to leave the small ridges around the insertion point intact. They will help align the camera module later. There are some closed cut-outs. You have to remove the one that suits your JST-XH connector you solder onto it (or you break away all cut-outs, you monster).

# Assembly
When all parts are printed and prepared, assembly is mainly straightforward. The STEP file I've shared here provides a 3D model of the whole assembly. Here is roughly a step-by-step assembly:

## Assembly of the Base of Mini/Midi
- Optional: Install tiny bearings with M2 screws for the rotor. They screw directly into the plastic. Those M2 screws are for straight alignment, not for high clamping force, so do NOT overtighten them.
- Add the gear to the rotor Nema 17. Depending on the printer and print setting, the gear can be too large or too small. If that is the case, reprint the gear 5% smaller or larger. The gear should have an good friction and form fit.
- Check and align the motor before screwing them fully in. The cable connector might be challenging to reach if you orient them to the wrong side.
- Before bolting down the rotor motor, check the cogwheel/gear height first. The rotor motor has slotted M3 holes, so the distance between the gear and rotor can be adjusted to minimize gear play.
- When the rotor motor and the rotor is installed, the rotor should have only minimal play without the motor moving
- Optional: Installing the rotor endstop is done with either M1.6 normal or M2 self-tapping screws. Check orientation of the end stop first so that the nose of the rotor surely hits the switch. Currently, the endstop only prevents the rotor to swoop agains the base, but is not using the endstop as homing point (might change with software update soon)

## Assembly Imaging Unit
- The imaging unit is a sandwich of parts, secured at the end with 4 M3 screws. Proper alignment before sandwiching them with bolts makes the job quite easy. Many parts have rotational symmetry to allow for easier modding.
- The sandwich order from bottom to top is: IU cover, camera mount (with camera), ring light PCB, IU frame,  camera polariser (opaque), light polariser (translucent)
- Use the screw-in or slide-in mount (slide-in recommended) for the camera and align it to the center. If the slide-in mount feels too tight, scratch off some plastic to widen the gap first.
- Take the IU cover and feed the CSI camera cable through the slotted hole. Take care of the proper orientation. Connect the cable to the camera.
- The camera mount can be placed and aligned with the small ridges close to the heat inserts of the IU cover.
- Check what JST-XH connector, angled or straight, and ring light you have and which cut-out of the imaging unit cover you have to clear. Note: Changing the connector's side also changes its pinout's order!
- Carefully place the ring light PCB and the IU frame with already inserted M3 bolts onto the sandwich assembly and bolt it down.
- The opaque camera polarizer and ring light polarizer *must be aligned for cross-polarization*, i.e., virtually no light comes through when placing two cross-polarized filters onto each other. If not correctly cut and aligned, they cannot properly reduce reflections, and scan results will be significantly diminished.

## Assembly Shield and RPi Cover
- Place the shield onto the shield cover and screw the M2.5 standoffs directly into the plastic of the cover. Again, they are not meant to bear large forces! Do not overtighten them; otherwise, you strip the plastic. 
- Place/press the RPi with its cover on top. The 2x20 connector has quite high friction, so take your time and do not accidentally bend the pins. 
- Place RPi cover on thr RPi. You might have to angle it a little so that the cover does not collide with the I/O of the RPi.
- Use M2.5 screws to secure the cover to the RPI+shield assembly. Once again, those should not be overtightened as they directly transfer excessive torque through the standoff into the plastic of the shield PCB.
- Screwing the base cover onto the base should be the last step when all wiring and alignments are done.
- Your Mini/Midi is ready now.

 
## Modding your OpenScan
There are some user mods already available. My favorite is the illumination dome mod, which places a half-cylinder/half-sphere shell around the scanned area, minimizing auto-focus issues and smoothing illumination. You can freely share your mods on printables, Thingiverse, GitHub, or Discord. When sharing mods, ideally, you also provide print instructions, e.g., "print-in-place, N perimeters, M% infill, etc.". 




