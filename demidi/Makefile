# Copyright (C) [2011-2016] [TheClashingRocks.org, zoobab.com]
#
# Authors:	Victor Perron <victor@iso3103.net>
#		Benjamin Henrion <zoobab@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=demidi
PKG_VERSION:=master
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/ZyreApps/DeMidi.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/demidi
    MAINTAINER:=zoobab@gmail.com
    TITLE:=demidi
    SECTION:=sound
    DEPENDS:=+zyre +alsa-lib
    CATEGORY:=Sound
endef

define Package/demidi/description
	DeMidi brings MIDI devices, sequencers, and synths together over WiFi without any cables and without any configuration.
endef

define Build/Configure
	( cd "$(PKG_BUILD_DIR)"; ./autogen.sh )
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default, -C $(PKG_BUILD_DIR) )
endef

define Package/demidi/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/src/{midicast,midigrab} $(1)/usr/bin/
endef

$(eval $(call BuildPackage,demidi))
