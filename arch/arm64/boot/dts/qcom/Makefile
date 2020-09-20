# SPDX-License-Identifier: GPL-2.0
ifeq ($(CONFIG_ARM64),y)
dtbo-y += sm8150-sdx50m-mtp-overlay.dtbo

sm8150-sdx50m-mtp-overlay.dtbo-base := sm8150.dtb sm8150-v2.dtb sm8150p.dtb sm8150p-v2.dtb

always		:= sm8150-v2.dtb
subdir-y	:= $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(dtb-y))
endif
clean-files	:= *.dtb *.dtbo

