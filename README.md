# macPPM

* Virtual joystick for OS X using the PPM output of RC transmitters. Like SmartPropoPlus or ppjoy but for OS X.
 Tested with a NineEagles J6 Pro on OS X 10.11.4.

* License exception: If you are a developer of a commercial mac helicopter sim you are not allowd to use the parts of this software written by me, unless
   I get a free life-time license key ;-)

# Installation
1. Build and install foohid.kext from http://github.com/unbit/foohid
2. Download macPPM source or the release. It includes a binary of libportaudio, which the makefile expects in the src directory. If you prefer to build this library on your own feel free to do so.
3. Make [or buy] a nice cable connecting your Transmitter to your soundcard input
4. Ensure that the audio input device is correctly set in the system preferences 	       
   (i.e. not 'microphone')
5. Run macPPM. For the first tries you may want to use './macPPM -t' to get audible feedback. -c swaps the used input channel.
There is a binary included that was compiled on OS X 10.11. If it doesn't work - please recompile. For testing YsJoystickReader can be useful.
6. Play your favorite sim/game. I tested it with x-plane, cgm-next and heli-x. The latter didn't work for me but I think that's is their fault.
7. If you don't have a NineEagles J6 Pro like me, you may have to adjust the code in main.c (the usb descriptor and how the ppm channels are mapped to the virtual joystick in the while loop at the bottom). In principle up to 20 buttons and/or proportional channels should be possible.

# Credits
This was made possible by combining https://github.com/nicholasrobinson/BuddyBox-PPM
with the code from http://github.com/unbit/foohid. I wrote the glue to stick them together.
