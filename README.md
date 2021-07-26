# Topre Realforce Wake-up issue on the MacOS


## Issue
If you use the Topre Realforce Keyboard (versions prior to R2) to wake up your Mac, it will no longer operate.
As a result, you won't be able to use your keyboard until you re-plug your USB cable. 


## Cause
I'm not sure what's causing this problem. 
However, I believe it is caused by something on the Realforce H/W. 
The Realforce R2 family has no problems.
Perhaps Topre will not fix this issue for the old version of Realforce.


## Solution
I made a simple solution for this issue.
Using a third-party program, forcibly re-plug USB port (only Realforce attached) after Wake-up.


## Prepare
- Keyboard Maestro (Any application, such as Keyboard Maestro, is acceptable)
- USB Prober (made by Apple, according to Apple Developer page, from IOUSBFamily package)
![f04638be315b3b0163f6b039044d111b](https://user-images.githubusercontent.com/35429874/126942487-9ff6657e-1b7e-48c9-9ac8-94160fd9edf1.jpg)


## How to
1. Install the USB Prober app to an Applications folder
2. Install Keyboard Maestro
3. Create a User Macro and add a Execute a Shell script
4. Set the Macro as shown below or Import attached kmmacros file (change VID, PID for your device)
```
/Applications/USB\ Prober.app/Contents/Resources/reenumerate -v 0x0853,0x0117
```
![c324a142b9e178e80237c64e9a6f6614](https://user-images.githubusercontent.com/35429874/126942532-83e3e71b-d721-4203-8a7e-56b1a275caaf.jpg)

5. Use programs like IORegistry Explorer or any other apps to check the macro works properly
![3aea0f85444b876f75df2610315b9e05](https://user-images.githubusercontent.com/35429874/126942551-08538661-8255-4593-abed-efb016b3cf24.jpg)
6. Done


