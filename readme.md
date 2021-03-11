2021.3.11 目前更新到macOS 10.15.7，换OpenCore引导了，应该可以使用在BigSur上



# MSI GS65 9SD 黑苹果EFI




# 硬件配置
* I7-9750H
* Intel集显 HD 630 & Nvidia GeForce GTX 1660Ti
* 16G 内存 (8GBx2)
* 512GB NVMe
* KILLER E2500 (RJ45)
* Killer(R) Wireless-AC 9560 WiFi
* 15.6" FHD (1920x1080), 144Hz, IPS-Level
* 雷电 3.0 Type C

### BIOS菜单设置

* Advanced
  *   Sata mode = AHCI 
  *   VT-d = 关闭
  *   VT-x/即intel虚拟化技术 = 关闭
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
* [AtherosE2200Ethernet](https://github.com/Mieze/AtherosE2200Ethernet/releases "AtherosE2200Ethernet") (以太网)
* AirportItlwm、IntelBluetoothFirmware、IntelBluetoothInjector （WIFI和蓝牙）
* NVMeFix （固态硬盘）
* AppleALC （声卡，仿冒ID我用的是34）
* SMCBatteryManager、SMCLightSensor、SMCProcessor、SMCSuperIO、（电池，光传感器等，貌似还有问题）

##  整体体验

* 显卡、声卡、网卡、等都没有问题
* App Store、iMessage、iCloud、FaceTime、等都没问题
* 能实现正常的睡眠唤醒
##  存在的问题

* 开机选了OC引导之后，黑屏等一会才跑代码，暂时不知道为什么