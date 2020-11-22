# Lenovo-Thinkpad-T440S

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
- Docking Station causes kernel panic if you have a display connected in any of the Docking Station Ports `VGA DVI DisplayPort` and you attempt to `Sleep, Reboot or Shutdown`

### Secure Boot
Users with `1366x768` or `1600x900` displays can go ahead and enable secure boot and enjoy it.
Users with upgraded displays to `1080p` or native `1080p` displays will have garbled screen if CSM is disabled in BIOS (which can't be left enabled if Secure Boot enabled)
In order to fix this problem we need to patch `Display-EDID`.

Procedures to be added soon...

### Wireless and Bluetooth

#### Intel AC7260
Users with Intel AC7260 cards can enjoy out of the box support for both Wireless and Bluetooth.
Keep in mind that Airportitlwm/itlwm is still in early development and only `N` speeds are supported.

#### DW1560, DW1830
Users with one of these two cards first need to disable the intel kexts:
`EFI/OC/Config.plist > Kernel > Add > Airportitlwm > Enabled = No`

`EFI/OC/Config.plist > Kernel > Add > IntelBluetoothInjector > Enabled = No`

`EFI/OC/Config.plist > Kernel > Add > IntelBluetoothFirmware > Enabled = No`

Then enable the corresponding kexts for those two cards:

`EFI/OC/Config.plist > Kernel > Add > AirportBrcmFixup > Enabled = Yes`

`EFI/OC/Config.plist > Kernel > Add > BrcmBluetoothInjector > Enabled = Yes`

`EFI/OC/Config.plist > Kernel > Add > BrcmFirmwareData > Enabled = Yes`

`EFI/OC/Config.plist > Kernel > Add > BrcmPatchRAM3 > Enabled = Yes`

#### DW1820A
This card uses the same kexts as DW1560, DW1830 but needs to disable ASPM to avoid freezes.

#### BRCM4360NG
This card is the best one you can find for the moment, it is the same as the Apple BCM94360CS2 which works natively but it does have a standard NGFF form factor.

#### BRCM94360CS2
This is the native Apple Wireless and Bluetooth card that can be found on MacBookPro(s).
In order to fit this one you will have to buy the NGFF adapter and the extending cable module.
There is not enough room to fit the full height so you will be required to place it somewhere else.


## Work in Progress...
