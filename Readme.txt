


-----------------------------------------------------------------------

The Kingmax servo programmer is designed to work on a PC running Windows.

The instructions here are for programming the KingMax SW22HV on a Windows 7 PC, so may be different if you have a newer PC. You will need an intenet connection for this to work.

First, especially if you have an older version of Windows, you need to update your system, because the servo programmer requires its own custom drivers and updates to Windows 7 also updates the way it finds and installs drivers. Please be aware that the Windows Update process may take several hours and may require waiting, rebooting, waiting and restarting the PC a couple of times, so be prepared, but don't be tempted to skip it.

To start Windows Update, go to Start and type "Windows Update" in the Search box. This should bring up Windows Update as a result.  Click on that to run it and follow the instructions.

Once the update process has completed,( and without plugging in the winch servo to the programmer yet) connect the KingMax servo programmer to a usb port.

Now search for "Device Manager" in the start search box. Click on the resulting program Device Manager to run it.

In Device Manager, look down the list for Other Devices -> DS Programer.

Now make sure you are connected to the internet since Windows will search online for drivers, and right click Other Devices -> DS Programer and select "Update Driver".

In the next window,, where it says "How do you want to search for driver software?", select "Search automatically for update driver software" .

 The search may take several minutes, so please be patient. After some time you should see "Downloading driver software..." and finally after a few more minutes "Windows has successfully updated your driver software. Windows has finished installing the software for this device"

Note that the programmer device has been renamed to USBXpress Device.

At this point, congratulations, you should have successfully installed the drivers for the programmer.

-----------------

Using the Programmer.

First The following files ( which should accompany this readme) should be placed in the same folder.  

DSConfig_v2.1.exe
SiUSBXp.dll
SW22HV_6_turn_default.svo
Readme.txt
DSConfig_v2.1.exe is the application
SiUSBXp.dll is a dynamic link library, used to talk to the usb driver
SW22HV_6_turn_default.svo is a winch servo configuration file which holds the default configuration for the SW22HV and can be used to recover the winch servo back to  a default working configuration.
Readme.txt  This readme

---------

Connect the servo programmer to the usb port and start the DSConfig_v1.2.exe application. Hit [Reflash USB] and check that v1.2 is seen in the text box to the left of the [Reflash USB] button. ( Note the exact version number of the app may change of course)

Next connect the winch servo to the programmer, taking especial care to get the connector the correct way around with black to the pin marked GND, and do a [Read Config]. This step is important since the default values that the DS Config app starts with are invalid for the SW22HV. If you write them the servo will probably (temporarily) stop moving, so always remember to do a [Read Config] first.

Next use the following values to find the correct ( non intuitive) values that will select your required number of turns into the Left range and Right range text boxes.

Turns 		Left Range[ 	Right Range
1 		-55 		-54
1.5 		-51 	        -49
2 		-46 		-45
2.5 		-42 		-41
3 		-39 		-37
3.5 		-34 		-33
4 		-30 		-30
4.5 		-26 		-25
5 		-22 		-22
5.5 		-19 		-18
6 		-14 		-14
6.5 		-11 		-10


Once happy press [Write Config]. You should hear a beep from the programmer. Your winch servo should now be updated to the new turns value.

Note that the provided turns values are only a guide and not exact. If the turns you want are between the values written, then you can try interpolating values between those written in the manual. For simplicity, just change (say) the Left range value by +-1 or 2 and then test if it provides the travel you want, rinse and repeat.

Once happy with the range, use the [Save] button to save your config somewhere on your PC.
 
You can use the Invert tick box if you want to change the direction the servo travels on a particular tx stick direction.  Using the invert button appears also to change the range somewhat as well unfortunately.

If for some reason your servo stops working, then use the [Load] button and load the SW22HV_6_turn_default.svo file and press [Write Config] and your winch servo should now start working again.



