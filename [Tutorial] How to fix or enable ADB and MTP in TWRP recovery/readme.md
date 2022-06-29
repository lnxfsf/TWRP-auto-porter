Requirements
TWRP recovery, you can port TWRP for your device
Notepad++ ; download @ https://notepad-plus-plus.org/downloads/
Android image kitchen (AIK) ; download @ https://forum.xda-developers.com/showthr...?t=2073775


Steps on how to fix or enable ADB and MTP in TWRP recovery


Follow the steps below to fix or enable ADB and MTP in TWRP recovery

1. Extract your twrp recovery.img using AIK tool (drag and drop onto the unpackimg.bat)

2. If successful, open the \ramdisk folder and edit the file below using a text editor e.g Notepad++
For android 7 and below, edit default.prop
For android 8 and above, edit prop.default


3. Search for the following items below one after the other and if they exist then modify their values (see the next step for the right values to use)
Code:
ro.secure
ro.adb.secure
ro.debuggable
persist.sys.usb.config
sys.usb.config



4. If they don't exist then add each item in a new line as seen below
Code:
ro.secure=0
ro.adb.secure=0
ro.debuggable=1
persist.sys.usb.config=adb,mtp
sys.usb.config=adb,mtp



5. Repack the TWRP by running the repackimg.bat script

6. Finally, flash and boot into TWRP then confirm if both ADB and MTP work

Important Notice
This might also work for other custom recoveries such as CWM / Philz. You can try to find out yourself
