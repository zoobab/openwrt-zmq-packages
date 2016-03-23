# Copyright (C) [2011-2016] [TheClashingRocks.org, zoobab.com]
#
# Authors:	Victor Perron <victor@iso3103.net>
#		Benjamin Henrion <zoobab@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=gsl
PKG_VERSION:=b337394
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/imatix/gsl.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=b3373947711e840021b4147318cf91a5cf09b0ed
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)/src

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/gsl
    MAINTAINER:=zoobab@gmail.com
    TITLE:=gsl
    SECTION:=lang
    SUBMENU:=Javascript
    CATEGORY:=Languages
endef

define Package/gsl/description
	GSL is a universal code generator
endef

define Build/Compile
	$(call Build/Compile/Default, -C $(PKG_BUILD_DIR) )
endef

define Package/gsl/install
	$(INSTALL_DIR) $(1)/usr/bin 
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/src/gsl $(1)/usr/bin/
endef

$(eval $(call BuildPackage,gsl))
