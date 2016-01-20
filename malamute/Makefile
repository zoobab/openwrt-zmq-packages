# Copyright (C) [2016] [zoobab.com]
#
# Authors: Benjamin Henrion <zoobab@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=malamute
PKG_VERSION:=a8879c3
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/zeromq/malamute.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
#PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_VERSION:=a8879c364c76ff14747d9ecd71a98057934d62e9
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/malamute
    MAINTAINER:=zoobab@gmail.com
    TITLE:=ZeroMQ enterprise messaging broker
    SECTION:=net
    DEPENDS:=+zyre +libmlm
    CATEGORY:=Network
endef

define Package/malamute/description
	The ZeroMQ Enterprise Messaging Broker
endef

define Build/Configure
	( cd "$(PKG_BUILD_DIR)"; ./autogen.sh )
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default, -C $(PKG_BUILD_DIR) )
endef

define Package/malamute/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/src/.libs/{malamute,mshell} $(1)/usr/bin/
endef

$(eval $(call BuildPackage,malamute))
