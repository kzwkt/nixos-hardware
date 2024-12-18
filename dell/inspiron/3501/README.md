# Dell Inspiron 15 ICL 3000,3501

### Hardware
- CPU: Intel® Core™ i3-1005G1  Processor
- GPU: Intel® Iris Plus Graphics G1 (Ice Lake) pci (8086:8a56 1028:0a2b )
- Network: Realtek Semiconductor Co., Ltd. RTL8101E/RTL8102E PCI Express Fast Ethernet controller pci (10ec:8136 )
- Wifi: QCA9377 , ath10k_pci driver 

```
 lspci -nn
00:00.0 Host bridge [0600]: Intel Corporation Device [8086:8a02] (rev 03)
00:02.0 VGA compatible controller [0300]: Intel Corporation Iris Plus Graphics G1 (Ice Lake) [8086:8a56] (rev 07)
00:04.0 Signal processing controller [1180]: Intel Corporation Processor Power and Thermal Controller [8086:8a03] (rev 03)
00:14.0 USB controller [0c03]: Intel Corporation Ice Lake-LP USB 3.1 xHCI Host Controller [8086:34ed] (rev 30)
00:14.2 RAM memory [0500]: Intel Corporation Ice Lake-LP DRAM Controller [8086:34ef] (rev 30)
00:15.0 Serial bus controller [0c80]: Intel Corporation Ice Lake-LP Serial IO I2C Controller #0 [8086:34e8] (rev 30)
00:15.1 Serial bus controller [0c80]: Intel Corporation Ice Lake-LP Serial IO I2C Controller #1 [8086:34e9] (rev 30)
00:16.0 Communication controller [0780]: Intel Corporation Ice Lake-LP Management Engine [8086:34e0] (rev 30)
00:17.0 SATA controller [0106]: Intel Corporation Ice Lake-LP SATA Controller [AHCI mode] [8086:34d3] (rev 30)
00:19.0 Serial bus controller [0c80]: Intel Corporation Ice Lake-LP Serial IO I2c Controller #4 [8086:34c5] (rev 30)
00:1d.0 PCI bridge [0604]: Intel Corporation Ice Lake-LP PCIe Port [8086:34b1] (rev 30)
00:1f.0 ISA bridge [0601]: Intel Corporation Ice Lake-LP LPC Controller [8086:3482] (rev 30)
00:1f.3 Audio device [0403]: Intel Corporation Ice Lake-LP Smart Sound Technology Audio Controller [8086:34c8] (rev 30)
00:1f.4 SMBus [0c05]: Intel Corporation Ice Lake-LP SMBus Controller [8086:34a3] (rev 30)
00:1f.5 Serial bus controller [0c80]: Intel Corporation Ice Lake-LP SPI Controller [8086:34a4] (rev 30)
01:00.0 Network controller [0280]: Qualcomm Atheros QCA9377 802.11ac Wireless Network Adapter [168c:0042] (rev 31)
```


### Before Installation

These settings are needed both for booting the final install, and
installer itself. Therefore, they must be done first:

+ Disable *Secure* Boot (but keep **UEFI** Boot)
+ Disable *RAID* and use **AHCI**

### Firmware Upgrades

Note that this device is supported by [fwupd](https://fwupd.org).
To perform firmware upgrades just activate the service:

```
services.fwupd.enable = true;
```

Then use `fwupdmgr` to perform updates



# excat blob needed 

needed extra firmware from linux-firmware 
-    https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/i915 : icl_dmc_ver1_09.bin  icl_guc_70.1.1.bin  icl_huc_9.0.0.bin : for graphics
-    https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/qca : nvm_usb_00000302.bin  nvm_usb_00000302_eu.bin  rampatch_usb_00000302.bin : for bluetooth 
-    https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/ath10k/QCA9377/hw1.0 : board-2.bin  board.bin	firmware-5.bin	firmware-6.bin	firmware-sdio-5.bin : for wifi
-    https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/rtl_nic/rtl8106e-1.fw : for ethernet


