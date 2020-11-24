# Lenovo Thinkpad T440S

[![macOS](https://img.shields.io/badge/macOS-Big_Sur_11.0.1-green)](https://www.apple.com/macos/big-sur/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.6.3-green)](https://github.com/acidanthera/OpenCorePkg)

Lenovo Thinkpad T440S using OpenCore Bootloader

### What works:
- Intel HD Graphics 4400 QE/CI
- Brightness Control
- TouchScreen with Gestures
- Keyboard & Backlit
- TouchPad with Gestures
- Dual Battery Support
- Secure Boot
- FileVault
- Sleep and Wake
- Audio and DisplayPort Audio
- Power Management
- USB Ports
- LAN
- DisplayPort
- VGA
- Wireless and Bluetooth
- Docking Station USB Ports
- Docking Station LAN
- Docking Station DisplayPort
- Docking Station VGA Port
- Docking Station DVI Port
- Everything else that i missed

### What doesn't work:
- DRM content
- SD Card Reader (no reliable kext)
- FingerPrint Reader
- Docking Station kernel panic if a display is connected in any of the Dock Ports `VGA DVI DisplayPort` and you attempt to `Sleep, Reboot or Shutdown`

### Secure Boot
Users with `1366x768` or `1600x900` displays can go ahead and enable secure boot and enjoy it.
Users with upgraded displays to `1080p` or native `1080p` displays will have garbled screen if CSM is disabled in BIOS (which can't be left enabled if Secure Boot enabled)
In order to fix this problem we need to patch `Display-EDID`.

Procedures to be added soon...

### Non TouchScreen Displays
If your Lenovo Thinkpad T440S doesn't have a TouchScreen display, it is required for you to disable the kext responsible for TouchScreen.
Go to `EFI/OC/Config.plist > Kernel > Add >` and disable the 4 following kexts:
- `VoodooI2CServices.kext - Enabled = No`
- `VoodooGPIO.kext - Enabled = No`
- `VoodooI2C.kext - Enabled = No`
- `VoodooI2CHID.kext - Enabled = No`

### TouchPad
Most of the users have probably already upgraded to a T450S Touchpad (the one with Physical Buttons) and this one does work natively, no need to touch anything.
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
- `EFI/OC/Config.plist > Kernel > Add > BrcmBluetoothInjector > Enabled = Yes`
- `EFI/OC/Config.plist > Kernel > Add > BrcmFirmwareData > Enabled = Yes`
- `EFI/OC/Config.plist > Kernel > Add > BrcmPatchRAM3 > Enabled = Yes`

#### DW1820A
This card uses the same kexts as DW1560, DW1830 but needs to disable ASPM to avoid freezes.
Into `EFI/OC/Config.plist > DeviceProperties >` and add the following entry: `PciRoot(0x0)/Pci(0x1C,0x1)/Pci(0x0,0x0)`
and into the `PciRoot(0x0)/Pci(0x1C,0x1)/Pci(0x0,0x0)` entry add the device property `pci-aspm-default` (number) `0`

#### BCM4360NG
This card is the best one you can find for the moment, it is the same as the Apple BCM94360CS2 which works natively but it does have a standard NGFF form factor.

#### BCM94360CS2
This is the native Apple Wireless and Bluetooth card that can be found on MacBookPro(s).
In order to fit this one you will have to buy the NGFF adapter and the extending cable module.
There is not enough room to fit the full height so you will be required to place it somewhere else.

### Credits
- [zhen-zen](https://github.com/zhen-zen) for **YogaSMC** and **BrightnessKeys**
- [benbender](https://github.com/benbender) for **SSDT-BATX**, **Touchscreen Gestures** and **ACPI refinements**

### Work in Progress...
