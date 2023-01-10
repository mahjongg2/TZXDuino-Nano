# TZXDuino-Pico REVISION 1.2 CASSETTE RECORDER EMULATOR IN MINIATURE FORMAT

A small board that can be built into a home computer, that can send .TZX cassette data read from an SD-Card to its cassette input
With one button you can page through the available files (games) and by pressing another button start playback, after first entering CLOAD "" on the Spectrum (or the ZX-81 if you use ZX-81 .TZX Files)

This device can use the (arduino) software of a regular TZXDuino (or compatible device like a CASDuino), but has been simplified and normally doesn't have a display or a full set of buttons (although both can be added if you want). you can also modifiy the software so that it sends its display output to the serial port of the Arduino, so you can see it on the built in terminal software of the Arduino IDE, you can use it to debug the system.

You can read more about it on my Revspace wiki project page here: https://revspace.nl/TZXDuino_pico

This project is open source, so I also uploaded the CAD files (for KiCad 6) so you can create your own version.

This device can also be used (perhaps with modified software) for other projects where you want an Arduino that has an SD-Card interface to read or safe data to.
when ordering PCB's you can enter that it is 37.1mm wide, and 47.2mm high, and is a 2 layer board.
as for component ordering the only specific part is the Hirose DM3D-SF push/pull micro SD-card connector, Farnell part # 1764377 , or mouser part 798-DM3D-SF . The buttons are standard 6x6mm buttons type MCDTS6-2N farnell code "9471707", or mouser code "179-TS026650BK160SCR" or reichelt code "taster 9302"
The same buttons as used in the ZX81+38 keyboard, although it is perhaps preferable to buy a type with a shorter stem lenght. 

This is revision 1,2 It has a 180 degrees rotated card holder, as the card needed to be sticked in from the side with the solderpads, and with the first revision that side was on the side of the resistors, so you could not insert the sd-card!
Also I changed all the (1206 size) resistors to the more common 0805 size
so from jan 10, 2023 the files here are for revision 1,2

I added a .png picture showing a 3D preview of a partially built up TZXDuino-pico, but the only parts missing are the Arduino-nano, and the two buttons. See TZXDuino-pico preview. Note that besides the rotated card holder and 0805 resistors, I now also have indicated the orientation of the Arduino nano, with the USB connector on top. I suggest using angled pinheaders for the buttons, the audio output, and the GND and +5V connectorns, so you can use simple Dupont cables with the connectors cut of at one end to make the connections. I also suggest twisting the two wires to the EAR connector to minimise interference, and make sure that you connect the GND wire to the GND pin of the EAR connector, using a multimeter to find which of the 3.5mm jack connector is connected to GND, you can use the cooling plate for the 7805 voltage regulator as a GND point. Also, be carefull not to switch the +5V and GND wires, to places on the Spectrum carrying GND and +5V. Use black and red wires to indicate which wire is GND (black) and 5V.
You can use this picture https://forums.raspberrypi.com/viewtopic.php?t=254492&start=175#p2064969 as an example of the wiring. 
As for the buttons, I used the simple pushbuttons in a cylindrical body with a mushroom shaped button, I drilled two 7mm holes through which the thread of the buttons went, and a hex nut to mount the buttons to the back of the raspberry PI.
I used the cheapest normally open buttons like this https://www.reichelt.nl/us/en/miniature-push-button-on-0-5-a-250-vac-red-t-113a-rt-p45166.html?&trstct=pos_0&nbc=1 but if you have another idea, then go ahead, as long as you use normally open buttons it will be fine.
I suggest using two different colors for the play (J3) and next (J2) button.

# How to use the TZXDuino-pico
Place one or more .TZX files for the computer you use in the root of the sd-card. With the card inserted in the TZXDuino-pico power up the spectrum, and start a cassette load (Press LOAD and two quotes "") and press enter. the screen will blank. now choose the game you want to load using the "next" button (or don't press the button at all if you just want the default (first) game in the list, in the order you put files on the card) then press the "play" button, and if all is well (No wiring errors, and the Arduino loaded with the default TZXDuino software) the TZXDuino-pico will start sending the cassette audio, and the screen will respond by showing the loading pattern (horizontal stripes) indicating loading has started, after a few seconds the Spectrum will show the name of the file you are loading, then resume the load. Depending of the game sometimes a loading screen will appear on the screen before the actual game is loaded. During the load you will hear the cassette audio from the Spectrum's speaker.
Note that the TZXDuino-pico will work with the default software, and it does not matter if the software is configured for the LCD or the OLED display.
