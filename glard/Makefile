# Copyright (C) [2016] [zoobab.com]
# Authors: Benjamin Henrion <zoobab@gmail.com>
include $(TOPDIR)/rules.mk

PKG_NAME:=glard
PKG_VERSION:=101

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/CodeJockey/glar150.git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=ac3887b897d4d041696cb1548cc2ca384f380f16

PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/glard
    TITLE:=glard
    MAINTAINER:=zoobab@gmail.com
    SECTION:=net
    CATEGORY:=Network
    DEPENDS:=+zyre +screen
endef

define Package/glard/description
	GL-AR150 demo application
endef

define Build/Configure
	( cd "$(PKG_BUILD_DIR)"; ./autogen.sh )
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default, -C $(PKG_BUILD_DIR) )
endef

define Package/glard/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/src/.libs/libglar* $(1)/usr/lib

	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/.libs/glard $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/commands/blink $(1)/usr/bin

	$(INSTALL_DIR) $(1)/root
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/glard_init.sh $(1)/root

	$(INSTALL_DIR) $(1)/etc
	$(CP) $(PKG_BUILD_DIR)/src/rc.local $(1)/etc
endef

$(eval $(call BuildPackage,glard))
