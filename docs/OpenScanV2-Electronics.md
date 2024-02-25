# OpenScan V2 Electronics Start-up Guide
The OpenScan PCBs are meant for tinkerers and people with a little electronics knowledge. They are not a 100% fail-safe product (no electronics really is). In case you are not super-confident in dealing with electronics, here is a small, step-by-step manual in how to get the V2 PCBs running, a.k.a. the "black shield" running (but will also work for the V1. "green shield") or how to figure out where an issue is, so that you or others can help you out. 

## "Trust is good, control is better" or "Trust, but verify"
The V2 shields should arrive fully functional and plug and play, however, you never know what happens during shipping. Before fully assemblying your OpenScan device, you should to a pre-flight electronics check as far as you have the equipment, i.e. a multimeter and perhaps a Philips screwdriver. You don't need any printed parts for that. In fact, the whole process is easiest when not fully assembled, the PCBs naked in front of you on an ESD mat.

## Checking the DCDC
Remove all components, RPi and motor drivers and cables. You are left with a shield that contains only the DCDC and a few passive components (they are rarely defect). Connect a 12V power cable and switch on the shield. Nothing should happen since nothing is connected. With a multimeter check if you can verify GND, 12V and 5V (more precisely 5.2V with the V2) at accessible points. If that is the case, your DCDC works. (V1 only) If your 5V is off, you can adjust the voltage with the potentiometer or flip over the DCDC, cut the potentiometer trace and bridge the "5V" solder jumber. *I highly recommend the solder jumper bridge, it is the most reliable 5V source.*

## Checking the motor drivers
Switch of the shield fully. Plug in the motor driver bricks *with correct orientation* but no motors. Switch the shield back on. If it smells funny, you oriented the motor driver wrongly; the driver is gone. Otherwise, verify the voltage, V_ref, of the motor drivers. Out-of-the-box, it should be approx 0.5V (V2) or 1V (V1). With a screwdriver, you can adjust the V_ref. The Mini and Midi only require very low V_ref as there are only small torques to overcome. 0.5V is sufficient. If you measure weird V_refs at the potentiometer, there is a good chance you measured the voltage wrongly, or the driver burned through. (V1 only) Check that the heat sinks are not bridging components and potentially induce a short circuit.

## Checking the RPi
It is time to plug in the RPi (after you powered down the shield again). After powering on, the RPi should boot (takes some time) and you should be able to access openscan.local eventually. Since nothing else is connected, not much can be done in the software at that point, but that is fine. We confirmed that the shield and motor drivers are properly working. Congratulations, your shield works. Now, we can address the motors and ring light.

## Checking the Ring Light
The ring light and shield have a 3-pin JST-XH terminal. This terminal prevents accidental flipping of cable connectors, however, it must be confirmed once at the beginning that the orientation of the cable pins fit. There are paired-end and twisted-end JST-XH cables! Further, the ring light V2 allows few orientations of the terminal. Due to this degree of freedom, it is better to check the pin order of the cable.
First, take the JST-XH cable and plug it into the shield. Leave the other end free so you can test with your multimeter. In the OpenScan interface, switch on the ring light. The slider has 4 steps, take the last (all ON). You should either see 0V="GND", 3.3V="Extra" or 12V="12V". This gives you the info what is "12V/GND/Extra" (V2) or "GND1/12V/GND2" (V1). If the pin order of your cable does not match the print on your ring light, take a small flat screwdriver and remove the pins and rearrange them accordingly.
**Long story short, if you use the cable from your V1 shield with your V2 shield, you must switch the outer pins when placing the JST-XH terminal as indicated on the ring light silkscreen print labeled "V2"**

## Checking the Motor wiring
Motors come with 4 (or more) connections. They are build up out of two coils, i.e. two wire pairs: pair "1" or (A1,B1), and pair "2" or (A2,B2). If(!) you have the tech. datasheet of your motor, you can look up the wiring. If not, then you have to figure out the order yourself, since there is no standard (correction: there are approx. 498323 standards, thus, the concept of "standard" became useless for motors). 

In any case, you start by plugging in the connector and hope the motor runs immediately. Most often, your motor has a reasonable wire config. You simply check what the motor is doing when you click to move the turntable or rotor up/down a little. 

### Case 1
The rotor/turntable moves in the right direction. Great, you are done. (45% chance)

### Case 2
The motor moves in the wrong direction. You can invert the direction pin in the setting. Your motor now moves in the right direction. Done. (45% chance)
### Case 3 
The motor lets the rotor/turntable vibrate very quickly back and forth and makes a buzzing, humming or squeecking sound. (10% chance) One of the pairs is unfortunately twisted. You have to untwist them:
 
The pairs you will find out easily: you measure the resistance with a multimeter. A pair has a very low resistance; it is only a coil after all. Which *direction* the coil is and which coil is "1" and "2" is open to be figured out. The connector on the board has the orientation ((A1,B1),(A2,B2)). Luckily, the OpenScan software can invert the direction. The OpenScan software has can switch the pairing by toggling the direction switch, i.e. the software can swap "1" and "2" for you, in case you guessed wrong.
This leaves you with guessing "A" and "B", the direction of the coils. Luckily, if you guess wrong two times for "1" and "2", you automatically invert the moving direction again, so the software can fix your wrong-guessing.

**Long story short, if your motor makes weird noises:** This leaves us with the config, that only one pair is inverted, i.e. "A1" is switched with "B1" OR "A2" is switched with "B2". Pick ONE pair and twist them. Your motor should now move. If the motor moves in the wrong direction, you have twisted the "wrong" pair, but that you can solve with the direction toggle in the software.




