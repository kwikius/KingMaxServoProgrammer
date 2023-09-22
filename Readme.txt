
The following files should accompany this readme in the same folder

DSConfig_v2.1.exe
SiUSBXp.dll
SW22HV_6_turn_default.svo

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

Connect the servo programmer to the usb port and start the DSConfig_v1.2.exe application. Select Reflash USB and check that v1.2 is seen in the txt box to the left of the reflash usb button. ( Note the exact version number of the appp may change of course)

Next do a Read Config. This step is important since the default values that the DS Config app starts with are invalid for the SW22HV. If you write them the servo will probably (temporarily) stop moving, so always remember to do a Read Config first.

Next use the turns values table in the programmer instructions to find the correct ( non intuitive) values that will select your required number of turns into the Left range and Right range text boxes and press Write Config.  
Note that the provided turns values are only a guide and not exact. If the turns you want are between the values written, then you can try interpolating values between those written in the manual. For simplicity, just change ( say) the Left range value by +-1 or 2 and then test if it provides the travel you want, rinse and repeat.

Once happy with the range, use the Save button to save your config somewhere.
 
You can use the invert tick box if you want to change the direction the servo travels on a particular tx stick direction which is nice!.  Using the invert button appears also to change the range somewhat as well unfortunately.

If for some reason your servo stops working, then use the Load button and load the SW22HV_6_turn_default.svo file and press Write Config and your winch servo should now start working again.



