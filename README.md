# SamsungS8-Root-Kali-Nethunter-Install-Guide
A guide to help root and install kalinethunter on Samsung s8 Plus

## Intro 
My goal for the project was to install Kali Linux NetHunter on a Samsung S8 Plus. However, I found a lack of resources on this topic, so here's a guide to help.

**Please note before continuing:** The Samsung S8 is **not** a supported device by Kali. Proceed at your own risk. USB support will not work unless you can write a custom kernel. I am doing this on Windows 11. Read the guide fully before attempting any modifications to the device. Perform a backup for the phone as we will be wiping it later. Nmap will not have full functionality and needs to be run with `--unprivileged`.`
## Samsung Phone Specifications
**Model:** Galaxy S8+ 
**Model Number:** SM-G955F 
**Android Version:** 9 
**Processor Type:** Exynos
## Developer Tools
### Enable Developer Tools
Start by navigating to Settings -> About Phone -> Software Info. Tap the build number 5-10 times to enable developer tools. A pop-up bubble will appear, indicating that developer tools are now enabled.
### Turn Off Bootlocking
While still in the settings, open the Developer Options and enable OEM unlocking. Scroll down to Debugging and choose USB debugging.
## Files to download
Now, let's move on to the computer side of things by downloading some files. I recommend using HighOnAndroid for the rooting files and drivers. You can find them at [highonandroid.com](https://highonandroid.com/).

1. Go to the "ROOTING" dropdown box and select "ODIN & Drivers."
2. Open both "Download Odin" and "Download Samsung USB Drivers."
3. Next, open the "MAGISK & SUPERSU" section.
    - Download the following files:
        - `Magisk v18.1 ZIP installer`
        - `Magisk Manager APK`
        - `No Verify Opt Encrypt ZIP`
        - `RMM State bypass ZIP`
4. Finally, open the TWRP recovery page.
    - Select the TWRP image suitable for your device; for me, it will be Galaxy S8+ SM-G955F/FD Exynos.
## Odin
Connect your Samsung phone to the computer. Now, extract Odin from the zip file and run the executable. A blue box at the top of the page will appear. If this doesn't happen, run the Samsung USB driver installer and restart Odin.
## Putting the Samsung in download mode
To put the device in download mode, simultaneously press the `Volume Down`, `Bixby`, and `Power Button` until the phone vibrates and a blue screen with an exclamation point in a triangle appears. When this occurs, press the `Volume Up` button to confirm putting the device in download mode.
## Rooting the phone
### Odin Part 2 
Returning to Odin, select the AP button. Locate and choose the `twrp.tar` file we downloaded earlier, then press start on Odin. After initiating the process, ensure that when the screen goes black (device powers off), press the `Volume Up`, `Bixby`, and `Power Button`
### TWRP 
Once the device reboots, you will find yourself on the TWRP menu. Start by selecting "Keep Read Only." You are now on the main TWRP menu. Navigate to the "Wipe" option, select it, and then choose "Wipe Data." Type "yes" when prompted.

*Note: This action will erase all data from the phone, so ensure you have a backup if needed.*

After the wipe is complete, press the home button to return to the original screen. Proceed to press the "Reboot" option and then select "Recovery." Press "Do Not Install" when prompted. The phone will reboot, bringing you back to the TWRP screen.

Now, copy the following files onto the Samsung phone:

- Magisk v18.1
- No Verify Opt Encrypt
- RMM State Bypass

Back on the phone, on the TWRP home screen, select "Install" and choose "No Verify Opt Encrypt." Swipe the bar at the bottom of the screen. After this, press back and repeat the process for "RMM State Bypass" and finally "Magisk," in that order.

Once all packages are installed, perform one last reboot.
## Install Magisk Manager
After the reboot is complete, set up the phone as normal. Next, reconnect the phone to your Windows 11 environment and move the Magisk Manager APK to the Samsung device. Open "My Files" on the Samsung and run the APK.

Once this is done, open the Magisk app. On the home screen, you'll find two options: Magisk and App. First, install the app and allow any permissions it requests.
## Magisk 
Restart the Magisk app and open it again. Select "Install" next to Magisk, and proceed to select "Next" for the options, as there's no need to make any changes.
### Method
In the "Method" section, the process may vary depending on the device. There could be up to two options. If you see both, choose "Patch a File" and proceed to direct install. However, if you see only one option, continue to the step below.
### Add or patch a file 
To manually patch in the file for Magisk, we need to download an additional tool and firmware. Bifrost has been found to work the best, and you can choose from the following tools:

- SamFirm.NET, samfirm.js
- Frija
- Bifrost
- Samloader (Archived)
## Setting up adb
For ADB, which is why we enabled USB debugging, follow the guide from here on how to install ADB: [Nexus Tools Guide](https://github.com/corbindavenport/nexus-tools).
## Downloading the firmware
_Note: I am using Bifrost for this._

1. Extract Bifrost from the zip file and run the executable. It may take some time to initially start. When it does, you will see four text boxes to input data.
2. Start with the Model Number, which can be found in the Settings under "About Phone." For example, my model number is SM-G955F. Write this into the Model box on Bifrost.
3. For Region, select the region and carrier if applicable that best suits your location.
4. Finally, input the IMEI/Serial number. These can be found in the Settings under "About Phone." We only need one, so it can be either.
5. Press the "Check for Updates" button, and the firmware box will fill itself in.
6. Next, press the "Download" button and wait for it to download. Unzip the firmware and copy the AP tar file to your device. It is normally named as AP_[device_model_sw_ver].tar.md5.
7. Open Magisk, go back to the Method, select "Add or Patch a File," and choose the md5 file we extracted.
8. Start the installation. After it's completed, reboot the phone. Now, you should have the direct install option. Click this and run through its process.
## Kali Setup
To start the Kali NetHunter setup, download the KaliStore APK file. This can be done from either the phone or Windows 11. I used Windows 11 to download the APK file, moved it onto the phone, and installed it from "My Files."

1. Open Kali Store and install the following:
    - NetHunter
    - NetHunter Terminal
2. Once these are installed, open the NetHunter app.
3. Select the three lines and open Kali Chroot Manager.
4. Choose "Install."
After this process is finished, you now have Kali NetHunter installed on your rooted Samsung S8+.
## References
### Reference format
Author, dd/mm/yyyy. Name of resource. link.

  Dr.E (Max Lee), 15/3/2019. "How to Root Galaxy S8/S8+ on Android 9.0 Pie!" Retrieved from
https://www.youtube.com/watch?v=ZD-5twDm6XI&t=431s

N/A, N/A. "Highonandroid". Retrieved from
https://highonandroid.com/

N/A, N/A. "installation | Magisk". Retrieved from
https://topjohnwu.github.io/Magisk/install.html#samsung-devices

jesec, 12/11/2023. "SamFirm.NET". Retrieved from
https://github.com/jesec/SamFirm.NET

jesec, 11/1/2021. "samfirm.js". Retrieved from
https://github.com/jesec/samfirm.js

SlackingVeteran, 28/3/2018. "frija". Retrieved from
https://github.com/SlackingVeteran/frija/releases/tag/v2.0.23364.3

samloader, 19/6/2023. "samloader". Retrieved from
https://github.com/samloader/samloader

zacharee 1/3/2021. "SamloaderKotlin". Retrieved from
https://github.com/zacharee/SamloaderKotlin/releases/tag/1.16.10
