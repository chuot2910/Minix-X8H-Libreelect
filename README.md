# MINIX Neo X8-X8H (S802)
```
Cau hinh:
Processor: Quad Core Cortex A9r4 Processor (Amlogic S802)
GPU: Octo Core Mali-450 GPU
Memory: 2GB DDR3
Internal Storage: 16GB eMMC
Wireless Connectivity: 802.11n Dual Band Wi-Fi (2.4GHz/5.8GHz), Bluetooth 4.0
OS: AndroidTM KitKat 4.4
Video Output: HDMI 1.4b, up to 4K @ 30fps
Audio Output: Via HDMITMM 1.4b, 3.5mm stereo jack, optical SPDIF
Peripheral Interface: RJ-45 Ethernet jack (10/100Mbps) - Supports hotspot sharing via Wi-Fi SD/MMC card reader (SD 3.0, MMC V4.41), Support HDMI-CEC USB 2.0 port x 3, OTG port x 1, Microphone Jack, Headphone Jack, IR receiver (remote included) 
Power: DC 5V, 3A adapter included (CE, FCC, CCC Certified)
Supported Video Format:DAT/MPEG/MPE/MPG/TS/TP/VOB/ISO/AVI/MP4/MOV/3GP/FLV/
MKV/M2TS/MTS/M4V/WMV/ASF/RM/RMVB
Supported Audio Format: DD/DD+/DTS/MP2/MP3/WMA/WAV/OGG/OGA/FLAC/ALAC/APE/AAC
```
Install LIBREELEC Just enough OS for KODI
https://forum.libreelec.tv/thread/23456-legacy-v9-2-lts-builds-for-amlogic-s805-s8x2-s905-s912-and-all-wetek-boxes/
https://github.com/dtechsrv/LibreELEC-AML
https://libreelec.dtech.hu/
https://libreelec.dtech.hu/images/3rdParty/

[ LibreELEC v9.2 (LTS) community builds for Amlogic S8xx, S905 and S912 devices ]

How to create bootable media, boot, install to eMMC/NAND and update

## Create bootable media (SD card or USB flash drive*):
To create bootable media you need to download the LibreELEC-AML USB-SD Creator
tool. Select the file you want to download and click the 'Download' button, or
click the 'Select file' button and browse the previously downloaded "img.gz" disk
image.

* Meson8* devices (S805/S8X2) only support USB boot since version v9.2.8.16.
However, this option is not enabled by default, because scanning USB ports in
some cases increases the boot time with additional delay. To enable it needs to
set a variable in the uboot environment: 'fw_setenv enableusbboot 1'.

It is important to note that some devices cannot boot from USB at all, or only
certain USB ports can be used for this purpose.

## Boot LibreELEC from your previously prepared bootable media:
If you want to boot the device from your bootable media, you need to perform the
toothpick method first: Disconnect the power plug, insert the prepared boot
media, and then press and hold the reset button*. Reconnect the power jack while
holding down the reset button, then release it after about 3-5 seconds**.

* The reset button on MXQ and M8S+ is located behind the A/V connector, but on
the Mecool and WeTek devices, the reset button is located behind the hole on the
bottom of the device.
** If the Android recovery menu appeared, you pressed the button for too long.

## Install image from bootable media to internal NAND/eMMC (non-WeTek devices only):
If you want to install the image into the internal memory, you need to log in to
the device via SSH* and run the 'installtointernal' command.

* The default password for the root user is 'libreelec'.

IMPORTANT NOTICE: It will completely overwrite the installed OS (e.g. Android),
so it will no longer be possible to boot that system!

## WeTek NAND Installation Guide:
Download the NAND installation zip file, extract it, and copy the contents of the
file to the root folder of an FAT32-formatted SD card. Disconnect the power cord
from the WeTek device, insert the prepared SD card, and plug in the power jack
while pressing the reset button through the toothpick-sized hole in the bottom
panel. You need to hold the button about 8-10 seconds until the LibreELEC
installation begins.

## Install an update package:
To install the update, you need to download, and then copy the update file (tar)
to the Update folder via SMB, and then restart the device. The update process will
start automatically after the restart.

