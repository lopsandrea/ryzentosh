# OpenCore EFI for AMD Ryzen Hackintosh

## Specification

| **Component**  | **Model**                           |
| -------------- | ----------------------------------- |
| CPU            | AMD Ryzen 5 3500x @ 3.6GHz          |
| Motherboard    | ASUS B450M Steel Legend             |
| RAM            | 64GB (4 x 16GB) Corsair @ 3200MHz   |
| Audio Chipset  | Realtek ALC892                      |
| GPU x 2        | XFX Rx 570 4gb                      |
| OS Disk (NVMe) | Samsung 512GB                       |
| WiFi           | AX3000 WiFi 6                       |

**macOS version**: 11.2.3 (20D91)
<br>
**OpenCore version**: 0.6.6

## Drivers 

- [[Bootloader] OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [[Patch] AMD_Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- [[Driver] OpenRuntime](https://github.com/acidanthera/OpenCorePkg)
- [[Driver] OpenCanopy](https://github.com/acidanthera/OpenCorePkg)
- [[Driver] HFSPlus](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)

## Kexts
- [[Kext] NVMeFix @1.0.5](https://github.com/acidanthera/NVMeFix)
- [[Kext] Lilu @1.5.1](https://github.com/acidanthera/Lilu)
- [[Kext] VirtualSMC @1.2.1](https://github.com/acidanthera/VirtualSMC)
- [[Kext] WhateverGreen @1.4.8](https://github.com/acidanthera/WhateverGreen)
- [[Kext] AppleALC @1.5.8](https://github.com/acidanthera/AppleALC)
- [[Kext] RealtekRTL8111 @2.4.0](https://github.com/Mieze/RTL8111_driver_for_OS_X/releases)
- [[Kext] AirportItlwm @1.2.0](https://github.com/OpenIntelWireless/itlwm)


## Not working

- Hypervisor.framework (VirtualBox and XCode iOS emulator works)
- Microphone 
- Bluetooth (fix asap)

## How to use

1. Create directory "EFI" in your EFI partition (e.g. pendrive or hard drive)
2. Clone this repo and paste directiories "BOOT" and "OC" onto created directory
3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select **Generate SMBIOS**, as model select **iMacPro1,1**.
4. Open config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree) and go to PlatformInfo > Generic. Set MLB (Board Serial), SystemSerialNumber (Serial) and SystemUUID (SmUUID) to generated values.
5. Make USB installer with [**this guide**](https://dortania.github.io/OpenCore-Desktop-Guide/installer-guide/)
6. Boot it!

**You CAN NOT use SMBIOS from this repository, it MUST be unique for every macOS installation**

## References

- OpenCore Desktop Guide: [**here**](https://dortania.github.io/OpenCore-Install-Guide/)
