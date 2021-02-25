2020.4.17 目前更新到macOS 10.15.7



# MSI GS65 9SD 黑苹果EFI



原版的配置是参考了[ErrorErrorError](https://github.com/ErrorErrorError)/**[msi-gs65-gs75-hackintosh](https://github.com/ErrorErrorError/msi-gs65-gs75-hackintosh)**

但感觉不对，修改很多东西，目前10.15上基本都驱动了




# 硬件配置
* I7-9750H
* Intel集显 HD 630 & Nvidia GeForce GTX 1660Ti
* 16G 内存 (8GBx2)
* 512GB NVMe
* KILLER E2500 (RJ45)
* Killer(R) Wireless-AC WiFi
* 15.6" FHD (1920x1080), 144Hz, IPS-Level
* 雷电 3.0 Type C

### BIOS菜单设置

* Advanced
  *   Sata mode = AHCI 
  *   VT-d = Disabled

* Boot 
  *   Fastboot = disabled
  *   Boot mode = UEFI with CSM

* Security
  *   Secure boot = disabled

##  驱动说明

* VirtualSMC、Lilu、Whatevergreen、这几个基本的就不说了

* [VoodooPS2](https://github.com/acidanthera/VoodooPS2/releases "VoodooPS2") (keyboard and mouse)
* [USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/ "USBInjectAll") (usb injection)
* [AtherosE2200Ethernet](https://github.com/Mieze/AtherosE2200Ethernet/releases "AtherosE2200Ethernet") (ethernet connection)
