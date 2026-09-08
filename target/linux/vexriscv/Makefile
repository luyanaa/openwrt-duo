# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2024 Toco Technologies <info@toco.ae>
#
include $(TOPDIR)/rules.mk

ARCH:=riscv32
BOARD:=vexriscv
BOARDNAME:=VexRISCV
FEATURES:=ext4
KERNELNAME:=Image dtbs
SUBTARGETS:=litex

KERNEL_PATCHVER:=6.1
KERNEL_TESTING_PATCHVER:=6.6

include $(INCLUDE_DIR)/target.mk

define Target/Description
	Build firmware images for the VexRISCV-based boards
endef

$(eval $(call BuildTarget))
