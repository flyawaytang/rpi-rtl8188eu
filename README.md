rpi-rtl8188eu
=============

Linux driver for tplink-wn725n nano wireless adapter.

Compile and install
===================
1. get linux source code from github
	git clone git://github.com/raspberrypi/linux.git rpi-linux
2. get fireware from github
	git clone git://github.com/raspberrypi/firmware.git rpi-firmware
3. cd rpi-linux
	make mrproper
	zcat /proc/config.gz > .config
	make modules_prepare
	cp /path/to/rpi-firmware/extra/Module.symvers .
	cd /path/to/rtl-8188eu
	CONFIG_RLT8188EU=m make -C /path/to/rpi-linux M=`pwd`
4. copy 8188eu.ko to /lib/modules/`uname -r`/kernel/driver/net/wireless
5. modprobe 8188eu
6. ifconfig and you can see the wlan interface :-)
