################################################################
### AtlantsEmbedded:
### Intelligent & Machine Learning Systems

### Created by:Alex Joseph
### email: josephvalex@gmail.com

### Description: OpenWRT Makefile for signal processing library 
### for adding it to the build as a shared object
################################################################


include $(TOPDIR)/rules.mk

PKG_NAME:=signal_proc_lib
PKG_VERSION:=2015-28-05
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/AtlantsEmbedded/atlants-signal_proc_lib.git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/signal_proc_lib
	SECTION:=Libraries
	CATEGORY:=Atlants
	SUBMENU:=Libraries
	TITLE:=signal_proc_lib
	DEPENDS:=+librt
endef

define Package/signal_proc_lib/description
	Signal processing shared library
endef


define Package/signal_proc_lib/install
	$(INSTALL_DIR) $(1)/usr
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include
	cp $(PKG_BUILD_DIR)/*.so* $(1)/usr/lib/
	cp $(PKG_BUILD_DIR)/include/*.h $(1)/usr/include/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR)/usr
	$(INSTALL_DIR) $(STAGING_DIR)/usr/include/
	$(INSTALL_DIR) $(STAGING_DIR)/usr/lib
	cp $(PKG_BUILD_DIR)/*.so* $(STAGING_DIR)/usr/lib/
	cp $(PKG_BUILD_DIR)/include/*.h $(STAGING_DIR)/usr/include/

endef

$(eval $(call BuildPackage,signal_proc_lib))

