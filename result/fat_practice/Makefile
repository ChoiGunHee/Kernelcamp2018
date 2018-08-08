#
# Makefile for the Linux fat filesystem support.
#
NAME=vfat_lecture
obj-m += fat_kernel_camp.o
obj-m += $(NAME).o

fat_kernel_camp-y := cache.o dir.o fatent.o file.o inode.o misc.o nfs.o
$(NAME)-objs := namei_vfat.o

KDIR:=/lib/modules/$(shell uname -r)/build
PWD:=$(shell pwd)

CFLAGS_fatent.o = -I$(src)

default:$(TARGETS)
	$(MAKE) -C $(KDIR) SUBDIRS=$(PWD) modules

clean :
	rm -rf *.ko
	rm -rf *.mod.*
	rm -rf .*.cmd
	rm -rf *.o
	rm -rf .tmp_versions
