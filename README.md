# Lenovo ThinkPad T440s OpenCore Configuration


![repository-open-graph-template new](https://user-images.githubusercontent.com/72415505/192321519-9ccf8bf8-a79a-401c-991a-5af1d3d19d50.png)



[![macOS](https://img.shields.io/badge/macOS-Big_Sur_11.7-red)](https://www.apple.com/macos/big-sur/)
[![macOS](https://img.shields.io/badge/macOS-Monterey_12.6-green)](https://www.apple.com/macos/monterey/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.8.5-blue)](https://github.com/acidanthera/OpenCorePkg)


<p align="center">
   <strong>Status: Maintained</strong>
   <br />
   <strong>OpenCore Version: </strong>0.8.5
   <br />
   <a href="https://github.com/MultimediaLucario/Lenovo-ThinkPad-T440s/releases"><strong>Download now »</strong></a>
   <br />
   <a href="https://github.com/MultimediaLucario/Lenovo-ThinkPad-T440s/discussions">Report Bug</a>
   ·
   <a href="https://github.com/MultimediaLucario/Lenovo-ThinkPad-T440s/blob/main/CHANGELOG.md">Recent Changes</a>
   ·
   <a href=https://www.youtube.com/watch?v=6cAxwXj5Zy4">YouTube Review</a>
   ·
   <a href="https://github.com/Sniki/Lenovo-Thinkpad-T440S">Original Repo</a>
  </p>
</p>
</br>

#
<details>  
<summary><strong>Recent Changes ⌚️ </strong></summary>
</br>

**10/12/2022** : Updated from OpenCore 0.8.3 to OpenCore 0.8.5                                                          
                                                           
**09/29/2022** : Added TrackPoint support and fixed the Instant Wake Issue when in sleep mode.

**09/26/2022** : Added Bluetooth support for macOS Monterey & fixed the slow startup issue.

**09/18/2022** : Changed the SMBIOS from ```MacBookPro11,1``` to  ```MacBookPro11,5``` for macOS Monterey.

</details>

</details>


<details>  
<summary><strong>My ThinkPad T440s Hardware Specs 💻</strong></summary>
</br>

| Model              | Lenovo ThinkPad T440s                                                                               |
|:-------------------|:----------------------------------------------------------------------------------------------------------|
| Processor          | Intel Core i5-4300U (2C, 4T,  1.9GHz / 2.5GHz) vPro (The best compatibility with macOS)                                                              
| Graphics           | Integrated Intel HD Graphics 4400                                                                         |
| Memory             | 12 GB DDR3 (4GB Soldered + 8GB SODIMM DDR3, dual-channel)                                                       |
| Display            | 14" HD (1600x900) TN, non-touch                                                                       |
| Storage            | 1 TB Pioneer SATA SSD + 16 GB mSATA SSD                                                                             |
| Ethernet           | Intel Ethernet                                                         |
| WLAN + Bluetooth   | Intel Wifi 7260ngw + Bluetooth 4.0                                        |
| Camera             | 720p resolution, low light sensitive, fixed focus                                                       |
| Audio support      | HD Audio, Realtek ALC3245 codec, stereo speakers 1Wx2, dual array microphone, combo audio/microphone jack |
| Keyboard           | 6-row, spill-resistant, multimedia Fn keys, LED backlight                                                 |
| Battery            | Internal Li-Polymer 3-cell (68) and External Li-Ion 6-cell (68+)                       |


</details>

</details>

<details>  
<summary><strong>Hardware Compatibility 🧰</strong></summary>
</br>
 
## What works:
- Intel HD Graphics 4400 QE/CI
- Brightness Control
- TouchScreen with Gestures
- Keyboard & Backlit
- TrackPoint (TrackPoint / Nipple Mouse Warriors, rejoice!)
- TouchPad with Gestures
- Dual Battery Support
- Secure Boot
- FileVault
- Sleep and Wake
- Audio and DisplayPort Audio
- Power Management
- USB Ports
- LAN
- DisplayPort (Currently not working under macOS Monterey)
- VGA
- Wireless and Bluetooth
- SD Card Reader
- Docking Station USB Ports
- Docking Station LAN
- Docking Station DisplayPort (Currently not working under macOS Monterey)
- Docking Station VGA Port (Currently not working under macOS Monterey)
- Docking Station DVI Port (Currently not working under macOS Monterey)
- Docking Station DisplayPort Audio (Currently not working under macOS Monterey)
- [DRM content](https://github.com/acidanthera/OpenCorePkg/releases) 

## What doesn't work:
- FingerPrint Reader



</details>

</details>

<details>  
<summary><strong>Photos 📷 </strong></summary>
</br>


![IMG_0864 copy](https://user-images.githubusercontent.com/72415505/193050341-594325eb-5070-439d-adf6-0675eb9205e4.jpg)

![CA22B0F4-5E65-4EFC-A22C-982CBE542B40](https://user-images.githubusercontent.com/72415505/193050942-1d1e1d86-31f6-4d40-943b-6965ea132d00.jpeg)

![659834E9-136E-4368-8D4A-E66CF6E17244](https://user-images.githubusercontent.com/72415505/193051479-9ba92d2e-3369-4abb-ad70-7467b20a9b89.jpeg)

</details>



#
## Lenovo ThinkPad T440s Hackintosh Guide

<details>  
<summary><strong>Getting Started</strong></summary>
</br>

To start you'll need the following:

You must have the following items:
- Lenovo ThinkPad T440s (Obviously 😁).
- Access to a working Windows machine with Python installed.
- A pendrive with more than 4 GB (Keep in mind, during the preperation we will format the disk to create the install media).
- an Internet connection via Ethernet.
- 1-2 hours of your time.

</details>

<details>  
<summary><strong>Creating the USB Installer </strong></summary>
</br>

1. To grab legacy installers is super easy, first grab a copy of [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg/releases) and head to /Utilities/macrecovery/. Next copy the folder path for the macrecovery folder. 

<img width="974" alt="file-path 0aea4278" src="https://user-images.githubusercontent.com/72415505/156628158-190cba5d-6114-4972-aa83-f1b14749e34d.png">


#
2. From here, you'll want to open up a Command Prompt and cd into the macrecovery folder that we copied earlier:

```cd Paste_Folder_Path```

<img width="917" alt="command-prompt 53392eba" src="https://user-images.githubusercontent.com/72415505/156628358-c2692037-80ac-40f9-bb3b-9a424442dafe.png">

#
3. Now run one of the following depending on what version of macOS you want(Note these scripts rely on [Python](https://www.microsoft.com/en-us/p/python-39/9p7qfqmjrfp7?activetab=pivot:overviewtab) support, please install if you haven't already):

 ```
# Mojave (10.14)
python macrecovery.py -b Mac-7BA5B2DFE22DDD8C -m 00000000000KXPG00 download

# Catalina (10.15)
python macrecovery.py -b Mac-00BE6ED71E35EB86 -m 00000000000000000 download

# Big Sur (11)
python macrecovery.py -b Mac-42FD25EABCABB274 -m 00000000000000000 download

# Monterey (12)
python macrecovery.py -b Mac-E43C1C25D4880AD6 -m 00000000000000000 download

# Ventura (13) (Coming Soon)
```

This will take some time, however once you're finished you should get either BaseSystem or RecoveryImage files:

![macrecovery-after 4c24ba88](https://user-images.githubusercontent.com/72415505/156629881-3d0e18a5-79cf-465e-a054-44b39a77b47f.jpg) <img width="973" alt="basesystem-example 93778929" src="https://user-images.githubusercontent.com/72415505/156629925-77869c1f-19ee-463f-bcc7-cafb2be09866.png">

#
4. Download [Rufus](https://rufus.ie/en/), set the BOOT selection as not bootable, set File System as Large FAT32, click Start, and delete all file autorun in USB Drive partition.

![format-usb-rufus 43feba9e](https://user-images.githubusercontent.com/72415505/156631083-73e33087-d51e-42e4-a804-e93afad7c2ca.png)

#
5. Next, go to the root of this USB drive and create a folder called com.apple.recovery.boot. Then move the downloaded BaseSystem or RecoveryImage files. Please ensure you copy over both the .dmg and .chunklist files to this folder:

<img width="824" alt="com-recovery 805dc41f" src="https://user-images.githubusercontent.com/72415505/156631343-529ca3ee-9e79-4e21-bab1-7305b4ed3df9.png">

#

6. Open up and extract the EFI folder archive you downloaded earlier.


7. Copy the folder named, "EFI," to the root of your USB Drive.

8. Restart your computer.


</details>

<details>  
<summary><strong>Installing macOS</strong></summary>
</br>

1. Open the BIOS and disable all the security options. (Security Chip, Intel (R) AT Module Activation, and Computrace Module)

2. Boot via your Flash Drive.

11. Boot the macOS installer.

12. Now open Disk Utility and format your internal or external Hard Drive or SSD as APFS.

13. Follow the on-screen prompts and install macOS.

14. Your system might reboot during the installation.

15. Now after install again boot into your usb drive and then select the drive that you installed macOS on.

16. Download and install [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/).

17. Open [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/) and Mount the EFI partition of the drive you want to boot off of.

18. Now copy the EFI Folder to the EFI Partition and overwrite it with the one system created.

19. Now try booting macOS without the USB drive.

20. Congratulations, you've successfully hackintoshed your Lenovo ThinkPad T440s.


#


</details>

<details>  
<summary><strong>Updating OpenCore </strong></summary>
</br>

1. Download and install the [OpenCore Updater](https://github.com/mswgen/oc-updater/releases).
2. When the app opens, press Get Started. A dialog will appear asking you to select the EFI directory.
3. Mount the EFI Partition on your drive using [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/).
4. Select your EFI directory. It's usually /Volumes/EFI/EFI. It should have BOOT and OC directories inside.
5. If your OpenCore version is detected, your OpenCore version and list of kexts you are using will be displayed. If your OpenCore version is not detected, you will be asked to select the OpenCore version you are using. Select the version you are using and press Select this version.
6. If you are not using the latest version of OpenCore, the app will ask you to update. Press Update to update OpenCore.
7. The app will start to download OpenCore, kexts, and Binary Data. this might take some time and you might see the spinning beach ball. DO NOT CLOSE THE APP.
8. When the app finishes downloading, it will create a backup of your old EFI and will swap files with the new ones.
9. Then, it will update config.plist. When it's done, it will display that it's done. It will also display the list of not updated kexts, the backup directory, and that OpenCore Vault is disabled(if it was enabled). You need to reboot your computer to see the changes.

</details>

<details>  
<summary><strong>Post-Install Tweaks </strong></summary>
</br>

### Bios
These are the recommended settings to have everything working properly:

**Security Tab**:
- `Security Chip > Security Chip [Disabled]`
- `Anti-Theft > Intel (R) AT Module Activation > Current Setting [Disabled]`
- `Anti-Theft > Computrace > Computrace Module Activation > Current Setting [Disabled]`

**Note**: These laptops do have whitelist which doesn't allow you to use other Card than the Intel AC7260.
In order to use a different / supported card, you need to mod your bios (remove whitelist) or downgrade to Bios v2.36
- Bios v2.36 doesn't have whitelist so downgrading allows you to use any wireless card that you want.


### Secure Boot
Users with `1366x768` or `1600x900` displays can go ahead and enable secure boot and enjoy it.
Users with upgraded displays to `1080p` or native `1080p` displays will have garbled screen if CSM is disabled in BIOS (which can't be left enabled if Secure Boot enabled)
In order to fix this problem we need to patch `Display-EDID`.

### Patching Display EDID [WIP]

First we need to download these three Applications: [Hackintool](https://github.com/headkaze/Hackintool/releases), [AWEDIDEditor](https://www.analogway.com/files/uploads/produit/download/en/aw_edideditor_setup_2_00_13_macos.zip) and [HexFiend](https://github.com/HexFiend/HexFiend/releases)

- Open Hackintool and go to the `Displays` tab and click the Export icon/button on the bottom-right side.
- On desktop, you will see some new files appeared, now open the `EDID-***-****-orig.bin` file with AWEDIDEditor
- Go to `Detailed Data` tab and change `H. Sync Width:` value to `100`.
- Save the EDID as `Patched-EDID` or whatever name you like just to know which one is the patched one
- Open the `Patched-EDID` with HexFiend and make sure you expand it so it contains 8 columns of code bytes.
- Copy the 128 bytes code and paste it into: `EFI>OC>Config.plist>DeviceProperties>PciRoot(0x0)/Pci(0x2,0x0)>AAPL00,override-no-connect`
- Save the config.plist file and reboot, Enjoy Secure Boot without garbled screen.


### Non TouchScreen Displays
If your Lenovo ThinkPad T440s doesn't have a TouchScreen display, it is required for you to disable the kext responsible for TouchScreen.
Go to `EFI/OC/Config.plist > Kernel > Add >` and disable the 4 following kexts:
- `VoodooI2CServices.kext - Enabled = No`
- `VoodooGPIO.kext - Enabled = No`
- `VoodooI2C.kext - Enabled = No`
- `VoodooI2CHID.kext - Enabled = No`

### TouchPad
Most of the users have probably already upgraded to a Lenovo ThinkPad T450s Touchpad (the one with Physical Buttons) and this one does work natively, no need to touch anything.
For you users that have the standard Touchpad that came with this laptop, you have to do some changes as VoodooRMI doesn't seem to work very well with them.

Go to `EFI/OC/Config.plist > Kernel > Add` and disable the VoodooRMI kexts:
- `VoodooRMI.kext - Enabled = No`
- `VoodooRMI.kext/Contents/PlugIns/RMISMBus.kext - Enabled = No`
- `VoodooRMI.kext/Contents/PlugIns/VoodooTrackpoint.kext - Enabled = No`
- `VoodooRMI.kext/Contents/PlugIns/VoodooInput.kext - Enabled = No`

Once done, enable the VoodooPS2Controller kexts for Touchpad:

- `VoodooPS2Controller.kext/Contents/PlugIns/VoodooInput.kext - Enabled = Yes`
- `VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Trackpad.kext - Enabled = Yes`
- `VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Mouse.kext - Enabled = Yes`

Now enable the `SSDT-TPD.aml` for Touchpad to work with VoodooPS2:  
- `EFI/OC/Config.plist > ACPI > Add > SSDT-TPD.aml > Enabled = Yes`

### YogaSMC
To have working Keyboard Function Keys (Fn) and Fan reading etc, you need to install the YogaSMCPane and the YogaSMC App.
YogaSMC.kext is already included in the EFI so when yo go to releases tab, you download the **YogaSMC-App-release.dmg**
- https://github.com/zhen-zen/YogaSMC


### Audio
ALCPlugFIx is required to fix static noise on headphones, however Black-Dragon74 released a Swift version that doesn't require `hda-verb`, `alc-verb` or `CodecCommander` kext. the `ALCPlugFix.zip` is included in the Tools folder.

**Installation**:
- Extract ALCPlugFix zip into desktop
- Open terminal and type following commands one by one on the listed order:
- `sudo spctl --master-disable`
- `sudo mkdir /usr/local/bin/`
- `cd desktop/ALCPlugFix`
- `sudo cp -R ALC3232.plist /usr/local/bin/`
- `./install.sh`
- Now the installer will ask you to drop the `ALC3232.plist` into the terminal window.
- Open a new finder window and press `Shift + Cmd(Alt) + G` to open a new `go to folder:` window
- Now type: `/usr/local/bin/`
- Drag the `ALC3232.plist` from the `/usr/local/bin` folder into the terminal window and press enter.
- Done


### Wireless and Bluetooth

#### Intel AC7260
Users with Intel AC7260 cards can enjoy out of the box support for both Wireless and Bluetooth.
Keep in mind that Airportitlwm/itlwm is still in early development and only `N` speeds are supported.

#### DW1560 & DW1830
Users with one of these two cards first need to disable the intel kexts:

- `EFI/OC/Config.plist > Kernel > Add > Airportitlwm > Enabled = No`
- `EFI/OC/Config.plist > Kernel > Add > IntelBluetoothInjector > Enabled = No`
- `EFI/OC/Config.plist > Kernel > Add > IntelBluetoothFirmware > Enabled = No`

Then enable the corresponding kexts for those two cards:

- `EFI/OC/Config.plist > Kernel > Add > AirportBrcmFixup > Enabled = Yes`
- `EFI/OC/Config.plist > Kernel > Add > AirPortBrcm4360_Injector > Enabled = Yes`
- `EFI/OC/Config.plist > Kernel > Add > BrcmBluetoothInjector > Enabled = Yes`
- `EFI/OC/Config.plist > Kernel > Add > BrcmFirmwareData > Enabled = Yes`
- `EFI/OC/Config.plist > Kernel > Add > BrcmPatchRAM3 > Enabled = Yes`

#### DW1820A
This card uses the same kexts as DW1560, DW1830 but needs this additional injector:
- `EFI/OC/Config.plist > Kernel > Add > AirPortBrcmNIC_Injector > Enabled = Yes`

We also need to disable `pci-aspm-default` to fix system freezes caused from this card:
Go into `EFI/OC/Config.plist > DeviceProperties >` and rename / uncomment:
- `#PciRoot(0x0)/Pci(0x1C,0x1)/Pci(0x0,0x0)` to `PciRoot(0x0)/Pci(0x1C,0x1)/Pci(0x0,0x0)` and the device property:
- `#pci-aspm-default` to `pci-aspm-default`

#### BCM4360NG
This card is the best one you can find for the moment, it is the same as the Apple BCM94360CS2 which works natively but it does have a standard NGFF form factor.

#### BCM94360CS2
This is the native Apple Wireless and Bluetooth card that can be found on MacBookPro(s).
In order to fit this one you will have to buy the NGFF adapter and the extending cable module.
There is not enough room to fit the full height so you will be required to place it somewhere else.

#### Country Code for Wireless Cards
Some countries have different 5GHz bands and may not be supported for some, the default one is set as US.
You can specify other country codes like: **US**, **CN**, **#a**, etc by going into:
- `EFI/OC/Config.plist > DeviceProperties > Add > PciRoot(0x0)/Pci(0x1C,0x1)/Pci(0x0,0x0)` and rename/uncomment:
- `#country-code` to `country-code` and set the desired value (**#a** is the preset value, replace with the country code that you need)

</details>

## Credits

<details>  
<summary><strong>Special Thanks to...</strong></summary>
</br>

- [zhen-zen](https://github.com/zhen-zen) for **YogaSMC** and **BrightnessKeys**
- [benbender](https://github.com/benbender) for **SSDT-BATX**, **Touchscreen Gestures** and **ACPI refinements**
- [Sniki](https://github.com/Sniki) for creating the original OC EFI files to make this hackintosh project possible.
- [ShiftHackZ](https://github.com/ShiftHackZ) and [valnoxy](https://github.com/valnoxy) for making macOS Monterey on a ThinkPad T440s possible.
- [mswgen](https://github.com/mswgen) for the OpenCore Updater application for macOS.
