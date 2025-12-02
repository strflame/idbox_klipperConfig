# KlipperConfig for idbox!

If it's exactly the same, you can use it as is, but I think it's better to make some fine adjustments.
Below is my equipment

mainsailOS : v2.14.0

Printer : idbox(Marlin v2.1.2.5.)

Extruder : 1 ※Bowden style

HeatBed : no



# How to connect the printer and control board (mainsail)
1.SSH connection to mainsaliOS

2.Execute the following to configure the microcontroller.

 cd ~/klipper/
 
 make menuconfig
 

3.Select the following on the settings screen.

 Architecture:ATMega
 
 Processor model:2560
 

4.After saving, run the make command to compile.
5.Check the USB device with the following command:
(The printer and control board must be connected via USB.)

 ls /dev/serial/by-id/*
 

 for exp: /dev/serial/by-id/usb-ID_BOX_ID_BOX_854303630393517162C1-if00

6.Finally, use the previous results to run the following command and write it:

 make flash FLASH_DEVICE=[previous result]
 
end.
