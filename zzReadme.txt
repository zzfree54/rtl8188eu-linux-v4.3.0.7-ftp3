RTL8188EUS_linux_v4.3.0.7_12758.20141114.zip
	driver/rtl8188EUS_linux_v4.3.0.7_12758.20141114.tar.gz

zz @ dell-ubuntu12.04
	@2015-0210

//zz//######################################
1.
download the source form here

ftp3.realtek.com.tw
RTL8188E : M6b3Er

//zz//######################################
2.
make
=> 8188eu.ko

need to modified Makefile

1)
#zz# @dell @2015-0204 begin
#zz# CONFIG_PLATFORM_I386_PC = y
CONFIG_PLATFORM_ARM_AM335X = y
#zz# @dell @2015-0204 end

2)
#zz###################################
# @home @2015-0204 begin
ifeq ($(CONFIG_PLATFORM_ARM_AM335X), y)
EXTRA_CFLAGS += -DCONFIG_LITTLE_ENDIAN
ARCH := arm
CROSS_COMPILE := arm-linux-
KVER  := 3.2.0
KSRC := /home/am335x-tisdk6.0/linux-3.2.0-psp04.06ti-zz
endif

# @home @2015-0204 end
#zz###################################




