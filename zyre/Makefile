# Copyright (C) [2011-2016] [TheClashingRocks.org, zoobab.com]
#
# Authors:	Victor Perron <victor@iso3103.net>
#		Benjamin Henrion <zoobab@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=zyre
PKG_VERSION:=master
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/zeromq/zyre.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/zyre
    MAINTAINER:=zoobab@gmail.com
    TITLE:=zyre
    SECTION:=libs
    DEPENDS:=+libuuid +czmq
    CATEGORY:=Libraries
endef

define Package/zyre/description
	ZyRE discovery library implementing ZRE protocol.
endef

define Build/Configure
	( cd "$(PKG_BUILD_DIR)"; ./autogen.sh )
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default, -C $(PKG_BUILD_DIR) )
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib $(1)/usr/include $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig $(1)/usr/lib/
endef

define Package/zyre/install
	$(INSTALL_DIR) $(1)/usr/lib 
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,zyre))
