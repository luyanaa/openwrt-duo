# SPDX-License-Identifier: GPL-2.0-only

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/image.mk

define Image/BuildKernel
 	cp $(KDIR)/Image $(BIN_DIR)/$(IMG_PREFIX)-Image
# 	cp $(DTS_DIR)/$(DTSDIR)/$(DTSNAME).dtb $(BIN_DIR)/$(DTSNAME).dtb
endef

define Image/Build/Initramfs
	cp $(KDIR)/Image-initramfs $(BIN_DIR)/$(IMG_PREFIX)-Image-initramfs
endef

define Image/Build/gzip
	gzip -f9n $(BIN_DIR)/$(IMG_ROOTFS)-$(1).img
endef

$(eval $(call Image/gzip-ext4-padded-squashfs))

define Image/Build
	$(call Image/Build/$(1))
	genimage --rootpath $(call mkfs_target_dir,$(1)) --inputpath ${PWD}/image/input --outputpath $(BIN_DIR)
#	$(call Image/Build/gzip/$(1))
endef

$(eval $(call BuildImage))

