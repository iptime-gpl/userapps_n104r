#
# Makefile for the kernel miscellaneous SPARC device drivers.
#
# Dave Redman Frame Buffer tuning support.
#
# 7 October 2000, Bartlomiej Zolnierkiewicz <bkz@linux-ide.org>
# Rewritten to use lists instead of if-statements.
#

O_TARGET := sunchar.o

export-objs := su.o bbc_i2c.o
obj-y := sunkbd.o sunkbdmap.o sunmouse.o sunserial.o zs.o

list-multi := vfc.o bbc.o
vfc-objs := vfc_dev.o vfc_i2c.o
bbc-objs := bbc_i2c.o bbc_envctrl.o

obj-$(CONFIG_PCI) += su.o pcikbd.o

obj-$(CONFIG_SAB82532)			+= sab82532.o
obj-$(CONFIG_ENVCTRL)			+= envctrl.o
obj-$(CONFIG_DISPLAY7SEG)		+= display7seg.o
obj-$(CONFIG_WATCHDOG_CP1XXX)		+= cpwatchdog.o
obj-$(CONFIG_WATCHDOG_RIO)		+= riowatchdog.o
obj-$(CONFIG_OBP_FLASH)			+= flash.o
obj-$(CONFIG_SUN_OPENPROMIO)		+= openprom.o
obj-$(CONFIG_SUN_MOSTEK_RTC)		+= rtc.o
obj-$(CONFIG_SUN_BPP)			+= bpp.o
obj-$(CONFIG_SUN_VIDEOPIX)		+= vfc.o
obj-$(CONFIG_SUN_AURORA)		+= aurora.o
obj-$(CONFIG_TADPOLE_TS102_UCTRL)	+= uctrl.o
obj-$(CONFIG_SUN_JSFLASH)		+= jsflash.o
obj-$(CONFIG_BBC_I2C)			+= bbc.o

include $(TOPDIR)/Rules.make

sunkbdmap.o: sunkeymap.c

vfc.o: $(vfc-objs)
	$(LD) -r -o $@ $(vfc-objs)

bbc.o: $(bbc-objs)
	$(LD) -r -o $@ $(bbc-objs)
