# OpenBCI_PulseSensor
Connecting [Pulse Sensor](www.pulsesensor.com) to [OpenBCI](www.openbci.com)

The output data stream from the OpenBCI 32bit board will contain auxiliary data that includes data derived from Pulse Sensor. OpenBCI library contains the auxData array and is composed of 3 16-bit variables.

  * auxData[0] = raw Pulse Sensor signal data (10 bit ADC result)
  * auxData[1] = BPM data, updated when OpenBCI finds a pulse (Beats Per Minute)
  * auxData[2] = IBI data, updated when OpenBCI finds a pulse (Inter-Beat Interval 4mS resolution)

This is still in BETA mode. The OpenBCI GUI is currently set up to convert the auxiliary data points into Gs, because it expects to find accelerometer data there. An update of the GUI is in the works...

_____________
There is a tutorial for getting started from scratch uploading code to OpenBCI 32bit Boards [here](http://docs.openbci.com/tutorials/02-Upload_Code_to_OpenBCI_Board#upload-code-to-openbci-board-32bit-upload-how-to)

Note that to USE the OpenBCI system, you will generally use the OpenBCI USB Dongle. The dongle requries that you install the FTDI drivers for your particular operating system: http://www.ftdichip.com/FTDrivers.htm

Download the latest Arduino IDE software from the Arduino site www.arduino.cc

Follow the instructions to download and install the latest chipKIT-core hardware files from the chipKIT-core wiki http://chipkit.net/wiki/index.php?title=ChipKIT_core

Before you can get started with programming or re-programming the OpenBCI 32bit Board, you will need to insall the libraries specific to it. These can be found here https://github.com/OpenBCI/OpenBCI_32bit_Libraries
Put the OpenBCI_32_Daisy and OBCI_SD folders into your Documents/Arduino folder and restart Arduino to be able to select the sketch.

When you upload the firmware, select the 'OpenBCI 32' from the Tools -> Board menu, 
select the serial port of the dongle in the Tools -> Port menu. On a Mac, it should be something like /dev/cu/OpenBCI-XXXXXX. On a Windows, it will be an enumerated COM port. 

The next step is to put the OpenBCI 32bit board into Bootloader mode, so that it can receive the code. To do this, press the RST and PROG buttons on the OpenBCI 32bit Board, then hold the PROG button while you release the RST button. If you do this right, the blue LED on the board will blink like crazy. Now you're ready to upload!

We are uploading the sketch over air! There is a chance that the process will fail!
If you ever unplug the Dongle, you MUST turn on the OpenBCI Board AFTER you plug the Dongle back in. This is to be nice to the radios as it is best that the Board radio comes on line after the dongle radio.

If you have any questions, or need other help, go to the forum http://openbci.com/index.php/forum/
