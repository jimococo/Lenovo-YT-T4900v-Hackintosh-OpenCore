# 联想 扬天 T4900v-00 台式机黑苹果OpenCore EFI 文件



[English](https://github.com/jimococo/Lenovo-YT-T4900v-Hackintosh-OpenCore) | 中文

### 最新的Release：[OpenCore 0.8.4](https://github.com/jimococo/Lenovo-YT-T4900v-Hackintosh-OpenCore/releases/tag/v0.8.4)

**macOS版本：macOS Monterey 12.6**

**OpenCore版本：[0.8.4 Official](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.8.4)**

本 OpenCore 黑苹果项目适配 联想品牌机 Lenovo T4900v-00 i5 9400 的配置

> 感谢 [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) 这个教程文档，让我学会了配置黑苹果的EFI文件；
>
> 感谢国内最优秀的黑苹果论坛之一——[黑果小兵部落阁](https://blog.daliansky.net/) 提供中文教程和打包的镜像文件，感谢兵哥的付出。



# 本EFI文件中不包含mac的序列号和主板ID等，请自行用[GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)软件生成序列号填入！！！



## 更新
- 2022-10-20
  
  基于OpenCore Official 0.8.4 
  
## 电脑配置

|   配件   |             规格              | 工作状态 |
| :------: | :---------------------------: | :------: |
|   模组   |         联想品牌机 T4900v-00         |    ✅     |
|   主板   | 联想 3176（300 Series 芯片组 Family (B365)） |    ✅     |
|  处理器  |   Intel Core i5-9400 @ 2.9GHz up to 4.1GHz   |    ✅     |
|   内存   |          8GB 记忆科技 DDR4 2666Mhz           |    ✅     |
| 固态硬盘 |           联想 X800 SATA 128GB SSD           |    ✅     |
| 机械硬盘 |               WD10EZEX 1TB HDD               |    ✅     |
| 核芯显卡 |            Intel UHD Graphics 630            |    ✅     |
| 独立显卡 |                      无                      |    🚫     |
|   声卡   |  Realtek 瑞昱@英特尔 High Definition Audio   |    ✅     |
| 有线网卡 |               Realtek RTL8111                |    ✅     |
| 无线网卡 | 无 | ✅ |
| 蓝牙 | 绿联 蓝牙 4.0 USB蓝牙模块 CSR 8150芯片 | ✅ |
| 显示器 | 联想LEN65CB LS2224A 21.5寸 ★使用VGA接口★ | ✅ |



## BIOS设置选项列表

### 禁用清单

- `Fast Boot` - 快速启动
- `VT-d` (can be enabled if you set DisableIoMapper to YES) - VT-d（如果DisableIOMapper Quicks设置为YES，则可以启用）
- `CSM` - CSM 兼容性支持模块
- `Thunderbolt` - 雷雳
- `Intel SGX` - 英特尔SGX
- `Intel Platform Trust`- 英特尔平台信任
- `CFG Lock` (MSR 0xE2 write protection) - CFG锁（MSR 0xE2写保护）（必须关闭，如果找不到该选项，则在OpenCore的config-内核-> Quirks下启用与CFG Lock相关选项）
- `Secure Boot` - 安全启动
- `Parallel Port` - 并口
- `Serial/COM Port` - 串行/COM端口

### 启用

- `VT-x` - VT-x
- `UEFI Boot Mode` UEFI启动模式。请不要使用Legacy
- 硬盘模式：改为`AHCI`。不能用IDE和RST RAID。
- `Above 4G decoding` - 大于4G地址空间解码
- `Hyper-Threading` - 超线程
- `Execute Disable Bit` - 执行禁用位
- `EHCI/XHCI Hand-off` - EHCI / XHCI接手控制
- `OS type`: `Windows 8.1/10 UEFI Mode` - 操作系统类型：Windows 8.1 / 10 UEFI模式
- `DVMT Pre-Allocated`(iGPU Memory): DVMT预分配（iGPU内存）：`64MB`（如果能设Max就设）
- `Legacy RTC Device` - 传统RTC设备



选项设置摘自[黑果小兵部落阁](https://blog.daliansky.net/) ，

如果你的BIOS中找不到这些选项，可以不用管，只调整你的BIOS中能找到以上的选项。

**请去联想官网更新 BIOS 至最新版本！**

**其他保持默认设置。**



## 工作的部分

- macOS 12.6（可以更新macOS 12的小版本，请不要更新macOS 13）
- CPU（睿频4.1Ghz，支持自动变频）
- 核芯显卡（完美驱动，支持硬解）
- 有线网卡（千兆网络）
- 音频（Layout=21 支持耳机麦克风二合一的耳机。请将耳麦接入标有耳机图标的那个接口上）
- USB（以完美定制USBPorts.kext，USB蓝牙已内建）
- 蓝牙（绿联蓝牙4.0 USB蓝牙模块 支持Apple的AirPods和Magic Trackpad 2等苹果原装设备）
- Wi-Fi（无。所以不支持隔空投送和接力，个人感觉这个品牌机没必要自己去加装无线网卡了）

## 不工作的部分

- HDMI（因为品牌机嘛，原配的显示器就是VGA接口的，而且300系列芯片组的VGA接口是DP转出来的，免驱，简单不需要定制，如果你需要HDMI输出，请自行完成核显接口输出定制）
