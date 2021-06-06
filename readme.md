2021.6.6 目前更新到macOS 11.4

WiFi和蓝牙驱动有问题，连接不稳定，引导时一直循环Interfirmware:................，需要等很久



# MSI GS65 9SD 黑苹果EFI




# 硬件配置
* I7-9750H
* Intel集显 HD 630 & Nvidia GeForce GTX 1660Ti （只能驱动集显）
* 主板HM370
* 16G 内存 (8GBx2)
* 512GB NVMe
* KILLER E2500 (RJ45)  （已驱动）
* Killer(R) Wireless-AC 9560 WiFi  （已驱动）
* 15.6" FHD (1920x1080), 144Hz, IPS-Level
* 雷电 3.0 Type C

### BIOS菜单设置

* Advanced
  *   Sata mode = AHCI 
  *   VT-d = 关闭
  *   VT-x/即intel虚拟化技术 = 开启
* Boot 
  *   Fastboot = disabled
  *   Boot mode = UEFI
* Security
  
  *   Secure boot = disabled
* 其它   按L-ALT + R-CTRL + R-SHIFT + F2或（fn + F2）查看BIOS隐藏功能
  
  * 关闭cfg lock  
  
    Advanced->Power & Performance->CPU - Power Management Control->CPU lock Configuration->CFG lock = Disabled
  
  * 开启cpu speed shift technology
  
  * 开启usb XHCI hand off
  
  * dvmt allocated设置为64m,最大值设置为max

##  驱动说明

* VirtualSMC、Lilu、Whatevergreen、这几个基本的就不说了
* [VoodooPS2](https://github.com/acidanthera/VoodooPS2/releases "VoodooPS2") (keyboard and mouse)
* XHCI-unsupported、USBPorts164 (借用别人做好的usb端口，机型需设置SMBIOS是16,4)
* [AtherosE2200Ethernet](https://github.com/Mieze/AtherosE2200Ethernet/releases) (以太网)
* [AirportItlwm](https://github.com/OpenIntelWireless/itlwm/releases) WiFi驱动，注意每个系统对应不同的文件
* IntelBluetoothFirmware、IntelBluetoothInjector （蓝牙）
* NVMeFix （固态硬盘）
* AppleALC （声卡，仿冒ID我用的是34）
* SMCBatteryManager、SMCLightSensor、SMCProcessor、SMCSuperIO、（电池，光传感器等，貌似还有问题）

##  ACPI

* SSDT-AWAC.aml
* SSDT-EC-USBX-LAPTOP.aml
* SSDT-PLUG-DRTNIA.aml
* SSDT-PMC.aml  用于模拟NVRAM，断电重启等保留信息，如蓝牙、屏幕亮度、音量、iMessage、、、没有的话会导致无法正常关机重启，关机卡住
* SSDT-PNLF-CFL.aml
* SSDT-XOSI.aml

##  CONFIG

待补充

##  整体体验

* 显卡、声卡、网卡、等都没有问题
* App Store、iMessage、iCloud、FaceTime、等都没问题
* 能实现正常的睡眠唤醒
##  一些注意的问题

* 有时BIOS的设置被重置了，导致无法引导，要注意检查  例如：电量耗尽关机
* 无法引导，可能NVRAM出了问题。重置后再添加引导项