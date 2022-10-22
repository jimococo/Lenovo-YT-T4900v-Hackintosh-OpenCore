# OpenCore Hackintosh for Lenovo YangTian T4900v-00 Desktop

English | [中文](https://github.com/jimococo/Lenovo-YT-T4900v-Hackintosh-OpenCore/blob/main/README_CN.md)

### Latest Release:[OpenCore 0.8.4](https://github.com/jimococo/Lenovo-YT-T4900v-Hackintosh-OpenCore/releases/tag/v0.8.4)

**macOS Version: macOS Monterey 12.6**

**OpenCore Version: [0.8.4 Official](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.8.4)**

This OpenCore Hackintosh repo is made for i5-9400 version of Lenovo YangTian T4900v-00 desktop.

> Thank for  [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) . This document taught me how to configure the Hackintosh EFI.
>
> Thanks for one of the best Hackintosh forums in China——[黑果小兵部落阁](https://blog.daliansky.net/) . This forum provides Chinese Hackintosh tutorials and packaged image files. Thanks!



### This EFI file does not contain the serial number and the motherboard ID, etc., please use the  [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) software to generate the serial number ！！！



## Updates
- 2022-10-20

  ​	Based on OpenCore Official 0.8.4 
## Configuration

| Specifications |                     Detail                      | Working |
| :------------: | :---------------------------------------------: | :-----: |
|     Model      |            Lenovo YangTian T4900v-00            |    ✅    |
|       MB       |  Lenovo 3176（300 Series Chips Family (B365)）  |    ✅    |
|   Processor    |    Intel Core i5-9400 @ 2.9GHz up to 4.1GHz     |    ✅    |
|     Memory     |            8GB RAMAXEL DDR4 2666Mhz             |    ✅    |
|      SSD       |           Lenovo X800 SATA 128GB SSD            |    ✅    |
|      HDD       |                WD10EZEX 1TB HDD                 |    ✅    |
|      iGPU      |             Intel UHD Graphics 630              |    ✅    |
|      dGPU      |                      none                       |    🚫    |
|   Sound Card   |      Realtek @ Intel High Definition Audio      |    ✅    |
| Ethernet Card  |                 Realtek RTL8111                 |    ✅    |
| Wireless Card  |                      none                       |    ✅    |
|   Bluetooth    |   UGREEN Bluetooth 4.0 USB with CSR 8150 Chip   |    ✅    |
|    display     | Lenovo LEN65CB LS2224A 21.5 ★ Connect VGA port★ |    ✅    |

## BIOS Configuration

### Disable

- `Fast Boot` 
- `VT-d` (can be enabled if you set DisableIoMapper to YES) - VT-d
- `CSM` 
- `Thunderbolt`
- `Intel SGX` 
- `Intel Platform Trust`
- `CFG Lock` (MSR 0xE2 write protection)
- `Secure Boot` 
- `Parallel Port` 
- `Serial/COM Port` 

### Enable

- `VT-x` 
- `UEFI Boot Mode` 
- SATA/Disk Mode：`AHCI`
- `Above 4G decoding` 
- `Hyper-Threading` 
- `Execute Disable Bit` 
- `EHCI/XHCI Hand-off` 
- `OS type`: `Windows 8.1/10 UEFI Mode` 
- `DVMT Pre-Allocated`(iGPU Memory)：`64MB`
- `Legacy RTC Device` 

Option settings excerpted from[黑果小兵部落阁](https://blog.daliansky.net/) ，

You just have to adjust the options you can find in the BIOS.

Please update BIOS to the newest version on Lenovo official website.

Everything else is set default.

## Working

- macOS 12.6
- CPU (Boost to 4.1Ghz)
- iGP (with hardware decoding)
- Ethernet (1Gbps)
- Audio (Layout=21, Support 2-in-1 headset)
- USB (Customed by USBPorts.kext)
- Bluetooth (With UGREEN Bluetooth 4.0 USB version , it can support Apple Magic Trackpad 2 ,etc.)

## Not Working

- HDMI (Only VGA monitors can be used. If you want to use HDMI, please customize the iGPU output by yourself. )
