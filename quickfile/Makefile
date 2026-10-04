#
# Copyright (C) 2015-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v3.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=quickfile
PKG_VERSION:=2.0.5
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/quickfile
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Web Servers/Proxies
  TITLE:=Quick File Manager
  DEPENDS:=+liblzma
  URL:=https://git.cooluc.com/sbwml/quickfile
endef

define Package/quickfile/description
  A high-performance, lightweight web file manager built with Rust (Axum) and Vue 3, featuring an integrated terminal and multimedia preview, tailored for embedded systems and the OpenWrt ecosystem.
endef

# 清空准备与编译阶段（跳过 OpenWrt SDK 内部耗时的 Rust/LLVM 重编）
define Build/Prepare
endef

define Build/Compile
endef

define Package/quickfile/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) ./quickfile $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/init.d $(1)/etc/nginx/conf.d
	$(INSTALL_BIN) $(CURDIR)/files/quickfile.init $(1)/etc/init.d/quickfile
	$(INSTALL_CONF) $(CURDIR)/files/quickfile.locations $(1)/etc/nginx/conf.d/quickfile.locations
endef

$(eval $(call BuildPackage,quickfile))
