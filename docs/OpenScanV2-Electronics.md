# Intro: OpenScan Electronics Start-up Guide
The OpenScan PCBs are meant for tinkerers and people with a little electronics knowledge. They are not a 100% fail-safe product (no electronics really is). In case you are not confident in dealing with electronics, here is a small, step-by-step manual how to get the PCBs tested and running, or how to figure out where an issue is, so that you or others can help you out. This guide is written for the "black shield", but will also work for the V1, "green shield", albeit all images and references are made for the black shield. 

## Chapter 0: "Trust is good, control is better" or "Trust, but verify"
The shields should arrive fully functional and plug-and-play (except when you order the solder-yourself kits), however, you never know what happens during shipping. We all heard horror stories of shipping companies. Before fully assemblying your OpenScan device, you should do a pre-flight electronics check as far as you have the equipment, i.e. a multimeter, an non-conducting underground and perhaps a Philips/Pozidrive screwdriver. You don't need any printed parts for that. *In fact, the whole process is easiest when not fully assembled, the PCBs naked in front of you on an ESD mat.* We now go through all components that can cause issues, when not handled properly.

## Chapter 1: Disconnect all components; Checking the DCDC
Remove all components, RPi, motor drivers and cables, from the shield. You are left with the bare shield that contains only the DCDC and a few passive components. Connect a 12V power cable and switch on the shield. Nothing should happen since nothing is connected, but the DCDC will be active! With a multimeter check if you can verify GND, 12V and 5V (more precisely 5.2V with the black shield). The easiest access points are the three huge solder pads of the DCDC. If that is the case, your DCDC works, no need to check any currents since there is nothing connected that requires power. 
*Green Shield only:* If your 5V is off, you can adjust the voltage with the potentiometer with a screw driver (annoying to adjust, OR flip over the DCDC, cut the potentiometer trace and bridge the "5V" solder jumber. *I highly recommend the solder jumper bridge. It is the most reliable 5V source.*

## Chapter 2: Checking the motor drivers
Switch off the shield again. Now, plug in the motor driver bricks *with correct orientation*! The Black shield has a print written "Top" and the delivered TMC2208 also have this print. They should align. No need to connect the Nema17 motors yet. 
*Green Shield only:* Check that the heat sinks are not bridging components and potentially induce a short circuit (otherwise re-align the heatsinks and fixate them with CA glue).
Switch the shield back on. If it smells funny and perhaps you see smoke, you oriented the motor driver wrongly; the driver is now dead. Otherwise, verify the voltage, V_ref, of the motor drivers. The voltage is measured between GND and the metal case of the potentiometer. Out-of-the-box, it should be approx 0.5V (black shield) or 1V (green shield). With a screwdriver, you can adjust the V_ref, and with that the strength (and heat dissipation!) of the motors. The Mini and Midi only require very low V_ref as there are only small forces needed to turn the rotor and turntable. 0.5V is sufficient. If you measure V_refs beyond 2V , there is a good chance you measured the voltage wrongly, or the driver burned through.

## Chapter 3: Checking the RPi
It is time to plug in the RPi (after you powered down the shield again!). After powering on, the RPi should boot. This usually takes some time. You should be able to access openscan.local eventually if(!) you have correctly set up the wpa config file for Wifi before booting. If not, then I recommend an ethernet cable for the time being and set up Wifi later. Since not much is connected, not much can be done in the software at that point, but that is fine. We can confirm that the shield can power the RPi and the motor drivers. We will need a functioning RPi for the next chapters. *For that, we have to set up the config so that the RPi communicates with the correct pins.* Go to Settings -> Advanced Settings. The config of the green shield is the default and nothing must be changed. However, if you are using the black shield, then configure everything according to the following config:

Pin Config
![Scanner](/images/Black-Shield-Config/BS-Pin-Config.png?raw=true)

Motor Config with activated endstop (see later chapter)
![Scanner](/images/Black-Shield-Config/BS-Rotor-Config-MINI.png?raw=true)

![Scanner](/images/Black-Shield-Config/BS-Rotor-Config-MIDI.png?raw=true)


## Chapter 4: Checking the Ring Light; Correct orientation of the connector
The ring light and shield have a 3-pin "JST-XH" terminal. This terminal prevents accidental flipping of cable connectors, i.e. pins 123 accidentally become 321. However, there are paired-end and twisted-end JST-XH cables! Due to this degree of freedom, it is better to check the pin order of the cable and do not trust that any JST-XH cable will work out of the box (50% chance of getting the wrong one!). Luckily, even if you have a "wrong" one, this will not damage the ring light; the LEDs will just not have enough voltage to turn on and the ring light stays dark. If you connect
*Black Shield only:* First, take the JST-XH cable and plug it into the shield. Leave the other end free so you can test with your multimeter. In the OpenScan interface, switch on the ring light. In older firmware, the slider has 4 steps; take the last (FULL ON). Now, we can measure the voltages of the three pins relative to GND. You should either measure 0V = "GND", 3.3V = "Extra" or 12V = "12V". You will find the named imprints on the ring light "12V/GND/Extra", labeling the correct pin order. Confirm that the pin order of the connector mathces the pin order of the terminal of the shield. If the pin order of your cable does not match the print on your ring light, we can re-arrange the pins: Disconnect the cable, take a small flat screwdriver and remove the (outer) pins and rearrange them accordingly. After rearranging, you can connect the cable and the ring light should turn on. Careful, the ring light is VERY bright.
*Long story short: The cable that comes with the green shield will fit the green shield's ring light. Vice versa for the black shield and its ring light. If you mix and match, then it is likely that you have to switch pin 1 and pin 3**

## Chapter 5: Checking the Motor wiring
Motors come with 4 (sometimes more) connections. They are build up out of two coils, i.e. two wire pairs: the one pair is labeled "1", more specific (A1,B1), and another pair with "2", more specific (A2,B2). Please read the pairing again, the  nomenclature for coil pairs is different than some people would intuitively guess! If(!) you have the tech. datasheet of your motor, you can look up the wiring. You might come across a different, more intuitive naming scheme of the wire pairs, namely (A+,A-) and (B+,B-), indicating with "A" and "B" which wires build a pair, and "+" and "-" to indicate inital current direction that would cause a clockwise movement. If you do not have a datasheet, then you have to figure out which of the four coloured cables are building pairs. There are no serious standards for wire color and coil pairing. You are on your own to figure that out.

*In any case, you start by plugging in the connector in the shield and hope the motors run immediately when commanded to move.* Go to the "Scan" interface of your running OpenScan device. You will have four arrows for manually moving the turntable and rotor motor clockwise and anti-clockwise. You simply check what the motors are doing when you click to move the turntable left/right and rotor up/down. A few cases can happen for turntable and rotor independently.

### Case 1, everything works as intended (45% chance)
The rotor and turntable move in the right directions relative to the arrow pressed. When you press "LEFT", the turntable moves clockwise, vice versa. When you press "UP", the rotor motor moves counter-clockwise, vice versa. Great, you are done, your wires are connected the way the software thinks they are connected. 

### Case 2, everything works, but direction is reversed (45% chance)
The motor moves in the opposite direction, like described in case 1. That can easily be fixed. Instead of physically switching wires of the connector, you can invert the direction  in the software settings, under advanced settings. There is an ON/OFF toggle for the motor and turntable direction, that inverts the the movement direction. After changing settings, your motors should now move in the direction they are supposed to move.

### Case 3 (10% chance)
When clicking the arrow buttons, a motor vibrates very quickly back and forth and makes a buzzing, humming or squeeking sound. One of the pairs is unfortunately twisted. You have to untwist them:
 
*Cavemen method:* randomly pick two wires, e.g. (1,2), take a small screwdriver, carefully remove the metal pins from the connector, and re-plug them in in switched order. Re-do the testing. If you now case 1 or 2, you randomly selected two right wires, congratulations. If not, then now pick one of the previously picked wires and a previously not picked one, e.g. (1,3) or (2,4), and repeat the process. Despite being the least scientific method, this is typically the quickest.

*Scientific method:* The connector on the black board has the orientation (A1,B1),(A2,B2)). Which *direction* the coils are and which coil is "1" and "2" is currently unknown. You measure the resistance with a multimeter across pairs of wires. A pair has a very low resistance, a few Ohms; it is only a coiled up wire after all. That is how you find the pairs. 
This leaves you with guessing "A" and "B", the direction of the coils. Luckily, if you guess wrong twice for both coils, the error cancels out, and you simply invert the moving direction, which the software can fix. If you guessed right and false once, then you get the buzzing/humming/squeeking sound. Then you have to twist *one* coil pair. The motor should now move wothout buzzing.

## Chapter 6, Installing an endstop for the rotor
The OpenScan device has no knowledge of the rotor position when freshly booted, thus also no knowledge of how far up and down it can move the rotor before an accident would happen, either rotor disengaging from the gear or bumping into the base. Without an endstop, it is the users resposibility to manually move the rotor to its starting position before every scan. This potential error source can be eliminated when installing an endstop to the V2 Mini and Midi. The endstop is triggered shortly before the rotor hits the base, thereby immediately end all movement, hence its name. This position can then be used as starting point for a trustworthy coordinate system for the OpenScan device. The endstop implementation follows the industry quasi-standard of fail-safe endstop implementation:

![Scanner](/images/Black-Shield-Config/microswitch-function.jpg?raw=true)

(1) The endstop is used as "normally closed" = NC, i.e. the right terminals for NC must be used. "Normally Closed" means, the endstop closes the circuit between "Common" or "Com" or "C" terminal and the "NC" terminal when the button is NOT pressed. Vice versa, this circuit is cut, when the button is pressed.
(2) The GPIO is connected to NC terminal of the endstop. The COM terminal is connected to GND. Thus, The circuit is normally closed to GND.
(3) This GPIO will be configured to internal pull-up, i.e. the GPIO will be HIGH (3.3V) when nothing pulls down its voltage level. Many microcontrollers have GPIO with configurable internal pull-up configuration, if not, then a hardware pull-up with a 100k resistor between the GPIO and 3.3V level is fine, too.
(4) Since the circuit is normally closed, the circuit to GND wins the "battle" against the pull-up. This means the GPIO senses LOW.
(5) When sensed HIGH on the GPIO (caused by the pull-up), the endstop routine will be triggered.

Fail-safe explained: Whenever the endstop is pressed *OR* the circuit fails/breaks for whatever reason, the GPIO will set itself with the help of the built-in pull-up to HIGH. This triggers the endstop routine. This is often coined a fail-safe implementation because the endstop routine will also be triggered when your cat/dog/hamster chews through the cables or anything else happens to the circuit.

All you have to do, is to install the endstop like described and images below, and enabling the endstop routine in the advanced settings.

![Scanner](/images/Black-Shield-Config/endstop-base.jpg?raw=true)

![Scanner](/images/Black-Shield-Config/endstop-shield.jpg?raw=true)

Whenever you start your scanning routine, the rotor will first move to the base, trigger the endstop, and then uses that position as reference for moving to the scan positions.