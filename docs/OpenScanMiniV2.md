# Building Manual OpenScan Mini & Midi V2

## Intro
Various parts and hardware were update from V1 to V1 to improve rigidity and user-friendlyness, especially in terms of printing. No more part orientation and support structure settings in your slicer. Just print-in-place. The V2 design natively supports the V2 shields ("black shield") which is currently inofficially available as prototype via development channel on discord.  

V2 also makes use of heat inserts M3x4x5 (diameter x length x diameter), widely popularized in 3D printing, especially in Voron style printers. For them, a *soldering iron* with spare (or sacrificial) tip or special heat insert tip is required. Make-shift solutions with M3 bolts and lighter are not recommended due to serious risk of burning your fingers.
All other hardware parts are summarized in the following tables. Not listed items, such as RPI and arducam 519, have not changed from the V1 and are omitted here.

### Essential Bill of Material (BOM)
The parts you definitely need to build a Mini/Midi V2. Some M3 bolts can be recycled but most hardware parts have changed.
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| M3x8mm SHCS/BHCS | 8+3 | for mounting Nema17 motors, base cover |
| M3x10mm SHCS/BHCS | 4 | base imaging unit (IU) and cover |
| M3x40mm+ SHCS/BHCS | 1 | mounting IU to rotor, any M3 equal or longer than 40mm will work, M3x70mm would be perfect, see non-essential BOM |
| Heat Inserts M3x4x5 | 3+1+4 | coined "Voron" inserts for base, rotor, and imaging unit. Must be 5mm diameter! 4.6mm diameter will not sit securely. They require a soldering iron to melt them in. |
| M2.5x10mm standoff | 4 | female-male standoffs, fixating (black) shield to base cover, screwed directly into plastic, brass recommended |
| M2.5x10mm SHCS | 4 | fixating RPI and RPI cover to base cover |

### Non-Essential BOM (Luxury and tinkerer upgrades)
Parts that are not needed for a functioning V2 but might make life here and there a little easier. This list is mainly based on many user mods that were incorporated in the V2 design.
| Part | Amount | Short Description |
| :--- | :---: | :---: |
| lubricant | 2-3 ml | lubricant that doesn't dissolve printed parts, ie, white lithium grease, for cog wheel |
| microswitch w or w/o lever | 1 | endstop: standard microswitch found in many 3D printers, quality ones prefered (eg Omron D2FC) |
| M1.6x12 (self-tapping optional) | 2 | endstop: through the endstop and directly into the plastic of the base, self-tapping screws work better |
| Heat Inserts M3x4x5 | 2 | mounting points: eg for lighting dome mod |
| M3x15mm standoff | 2 | mounting points: will replace two M3x8 from turntable. eg for light dome mod |
| F692 (2x6x3) mm | 4 | rotor guide: bearing with flange, will guide the rotor, reduce wobble and friction |
| M2x12 SHCS/BHCS | 4 | rotor guide: will fixate the bearings in the base |
| M3x70mm SHCS/BHCS | 1 | mounting cam holder to rotor, put a heat insert on the *opposite* side of the rotor, extra stiffness |
| Fan 3010 or similar | 1 | motors and drivers are producing heat which can soften PLA (and PETG) over time; a 30mm fan helps to prevent that; 3V3, 5V or 12V |
| M3x15 SHCS/BHCS | 4 | for mounting the fan into the housing |
| M3 nuts | 4 | for mounting the fan into the housing |


## Printing and preparing the parts
All V2 parts are designed as print in place, i.e. no part re-orientation or supports are required. When supports are needed, then they are already modelled into the files. The recommended print settings are 4 perimeters and approx. 40% cubic infill. It is highly recommended to print with 0.2mm layer height because all dimensions and clearances in the parts are modelled as multiples of 0.2mm! 
The parts fshould be printed in PETG or ideally ABS/ASA if your printer can handle it. PLA can also work, but due to the enclosed design, excessive heat from the motors and drivers can slowly deform PLA in the long term. When printing PLA, the motor currents MUST be adjusted to a working minimum to prevent heat creep of PLA (approx. 0.5A).
The cog wheel/gear for the rotor motor might have an over- or undersized center hole, depending on your printer settings and capabilities. It is recommended to print out this gear in three sizes, 95%, 100% and 105% to ensure that one of the gears fits. The gear should fit snug in the shaft with sufficient friction to hold it in place.
Some parts have overhangs and bridges. Those have to be checked and dangling filament parts should be cleaned. Take special notice of the base part since there are sacrificial bridges modelled into it. Those intentional bridges are for helping your slicer to properly slice and place bridges the arced overhang for the rotor. The sacrificial bridges around the bearing insert points should be removed carefully in order to be able to insert bearings later on. When not planning on using bearings at all, those bridges can be left untouched.
As a last step, all required heat inserts should be set properly, see images below. Orange spots are mandatory heat inserts, and yellow spots are optional heat inserts for mods.

###Base
*link photo here*
*link photo here*
Three inserts for the side cover are required. the additional at the bottom are for fixating the scanner to a table or optional turntable holder platform. The two optional on top are for the light dome mod for more uniform illumination.

###Rotor
*link photo here*
*Only melt in ONE heat insert depending on your available M3 bolt length!* M3x70 is recommended since it gives the most stability and most secure fixation, but M3x70 is sometimes hard to get. If you cannot source a M3x70 for a reasonable price (or low quantity), then pick the longest M3 you can find and melt in the heat insert onto the short side.

###Imaging Unit Cover
*link photo here*
Melt in four heat inserts as indicated. Try to leave the small ridges around the insertion point intact. They will help aligning the camera module later. There are some closed cut-outs. YOu have to remove the ones that suit your JST-XH connector you solder onto it (or you simply break away all cut-outs, you monster).

##Assembly of the Base
When all parts are printed and prepared, assembly is mainly straight-forward. The provided STEP file provides you a 3D model of the whole assembly. Here are some advices for assembly:

- Optional: Install tiny bearings with M2 bolts for the rotor. They bolt directly into plastic. Those M2 bolts are for straight alignment not for high clamping force, so do NOT overtighten them.
- Add the gear to the rotor Nema 17. Depending on printer and print setting, the gear can be a little to large or small. If that is the case, reprint the gear 5% smaller or larger. The gear should have a nice friction and form fit.
- Check and align motor before bolting them in. The cable connector might be hard to reach if you orient them to the wrong side otherwise.
- Before bolting down the rotor motor, check the proper height of the cog wheel/gear first. The rotor motor has slotted M3 holes so the distance between gear and rotor can be adjusted to minimize gear play.

- The imaging unit is a sandwich of parts, secured at the end with 4 M3 bolts. Proper alignment before sandwiching them with bolts makes the job easier. Many parts have rotational symmetry to allow of easier modding.
- Use the screw-in or slide-in mount (recommended) for the camera and align it to the center. If the slide-in mount feels to tight, scratch off some plastic to widen the gap first 
- The cam holder can be aligned with the small ridges close to the heat inserts.
- Check what JST-XH connector, angled or straight, and ring light you have and which cut-out of the imaging unit cover you have to clear. Note: Changing the side of the connector also changes the order of its pinout.
- Carefully place the ring light and the IU base with already inserted M3 bolts onto the sandwhich assembly and bolt it down.
- The opaque camera polarizer and ring light polarizer *must be aligned for cross-polarization*, i.e. when placing two cross-polarized filters onto each other, virtually no light comes through. If not properly cut and aligned, then they cannot properly reduce reflections and scan results will be greatly diminished.

- Place the shield onto the cover and screw the M2.5 standoffs directly into the plastic of the cover. Again, they are not meant to bear large forces, do not overtighten them, otherwise you strip the pastic. 
- Place/press the RPI with its cover on top. The 2x20 connector has quite high friction, so take your time and do not accidentally bend the pins. Use M2.5 screws to secure the cover to the RPI+shield assembly. Once again, those should not be overtightened as they directly transfer excessive torque through the standoff into plastic.
- Bolting the base cover onto the base should be the last step, when all wiring and alignment is done.



