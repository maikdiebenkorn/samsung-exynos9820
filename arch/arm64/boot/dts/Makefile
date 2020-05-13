# SPDX-License-Identifier: GPL-2.0
dts-dirs += actions
dts-dirs += al
dts-dirs += allwinner
dts-dirs += altera
dts-dirs += amd
dts-dirs += amlogic
dts-dirs += apm
dts-dirs += arm
dts-dirs += broadcom
dts-dirs += cavium
dts-dirs += exynos
dts-dirs += freescale
dts-dirs += hisilicon
dts-dirs += marvell
dts-dirs += mediatek
dts-dirs += nvidia
dts-dirs += qcom
dts-dirs += realtek
dts-dirs += renesas
dts-dirs += rockchip
dts-dirs += socionext
dts-dirs += sprd
dts-dirs += xilinx
dts-dirs += lg
dts-dirs += zte

subdir-y	:= $(dts-dirs)

dtstree		:= $(srctree)/$(src)

dtb-$(CONFIG_OF_ALL_DTBS) := $(patsubst $(dtstree)/%.dts,%.dtb, $(foreach d,$(dts-dirs), $(wildcard $(dtstree)/$(d)/*.dts)))

always		:= $(dtb-y)

targets += dtbs

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif
targets += $(DTB_LIST)

dtbs: $(addprefix $(obj)/, $(DTB_LIST))

clean-files := dts/*.dtb *.dtb

ifdef CONFIG_MODEL_G970F
include arch/arm64/boot/dts/G970F.mk
endif

ifdef CONFIG_MODEL_G970N
include arch/arm64/boot/dts/G970N.mk
endif

ifdef CONFIG_MODEL_G973F
include arch/arm64/boot/dts/G973F.mk
endif

ifdef CONFIG_MODEL_G975F
include arch/arm64/boot/dts/G975F.mk
endif

ifdef CONFIG_MODEL_G977B
include arch/arm64/boot/dts/G977B.mk
endif

ifdef CONFIG_MODEL_N970F
include arch/arm64/boot/dts/N970F.mk
endif

ifdef CONFIG_MODEL_N971N
include arch/arm64/boot/dts/N971N.mk
endif

ifdef CONFIG_MODEL_N975F
include arch/arm64/boot/dts/N975F.mk
endif

ifdef CONFIG_MODEL_N976B
include arch/arm64/boot/dts/N976B.mk
endif

ifdef CONFIG_MODEL_N976N
include arch/arm64/boot/dts/N976N.mk
endif
