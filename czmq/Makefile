# Copyright (C) [2013]
#
# Author: Victor Perron <victor@iso3103.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=czmq
PKG_VERSION:=c1b1284
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/hintjens/czmq.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=c1b1284166aac47ce9ebcfb257760b044a0f1245
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/czmq
    MAINTAINER:=zoobab@gmail.com
    TITLE:=czmq
    SECTION:=libs
    DEPENDS:=+zeromq
    CATEGORY:=Libraries
endef

define Package/czmq/description
	Handy C Wrapper for zeromq.
endef

define Build/Configure
	( cd $(PKG_BUILD_DIR); ./autogen.sh );
	$(call Build/Configure/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) \
		$(1)/usr/lib 	\
		$(1)/usr/include \
		$(1)/usr/lib/pkgconfig
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* \
		$(1)/usr/lib/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/include/* \
		$(1)/usr/include/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig \
		$(1)/usr/lib/

endef

define Package/czmq/install
	$(INSTALL_DIR) $(1)/usr/lib 
	$(CP) $(PKG_BUILD_DIR)/src/.libs/libczmq.so* $(1)/usr/lib/

endef

$(eval $(call BuildPackage,czmq))
