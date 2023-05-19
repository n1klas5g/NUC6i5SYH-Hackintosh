# NUC6i5SYH-Hackintosh
This is my EFI (OpenCore 0.9.2) built with help of Dortania's OpenCore Guide. I'm not a pro at hackintoshes, I just wanted to share my EFI with you all to make it easier for somebody else to use macOS on their NUC.

I'm using Ventura 13.3.1 at the moment - I cant't say something about the compatibility for other versions. For Monterey and older you should add `-igfxsklaskbl` to the boot args to get it working.

Specs of my NUC:
- CPU: Intel Core i5 6260U
- iGPU: Intel Iris Graphics 540 (spoofed as Iris Plus 640 to get Ventura working)
- RAM: single 8GB Stick of DDR4 2133
- SSD: Samsung 850 EVO 250GB
- Audio: Realtek ALC283 (got it working with layout id 1)
- Ethernet: Intel I219-V
- WiFi+BT: Intel AC-8260 (soldered on the NUC's mainboard)

# What's working and what isn't?
### Working:
- Audio Jack
- HDMI Video (can't test HDMI Audio)
- Bluetooth
- iServices
- Ethernet

### Not working:
- WiFi (due to the alpha state of the Airportitlwm Kext for Ventura) -> I could it get WiFi (just Internet, not everything else) working with adding a WiFi to the known WiFis via "Other" in the WiFi-Settings and then rebooting
- Continuity features (again due to the alpha state of the Airportitlwm Kext for Ventura)
- AirDrop (...)
- you could fix these issues by inserting a natively compatible WiFi-Card -> https://dortania.github.io/Wireless-Buyers-Guide/types-of-wireless-card/m2.html
- SD Card Reader

### Couldn't test:
- mDP output

# Installation:
1. Create the USB Installer (https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) and drag my EFI folder onto it
2. Generate SMBIOS for your Hackintosh (Model: iMac18,1): https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#platforminfo
3. Change your BIOS settings as explained in the Dortania guide (you can leave VT-d on): https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#intel-bios-settings
4. Boot via F10 from the USB and hit space when you see the OpenCore boot menu. You can select the macOS Installer with the arrow keys.

# Post-install:
When you installed and setted up macOS, you maybe want your Hackintosh to boot without the USB: https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html#grabbing-opencore-off-the-usb

# Credits:
- https://dortania.github.io/OpenCore-Install-Guide/
- dev's of OpenCore, Lilu, VirtualSMC, WhateverGreen, IntelMausi, AppleALC and itlwm
