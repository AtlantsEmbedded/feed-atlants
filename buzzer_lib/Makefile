include $(TOPDIR)/rules.mk

PKG_NAME:=buzzer_lib
PKG_VERSION:=2016-02-02
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/AtlantsEmbedded/atlants-buzzer_lib.git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/buzzer_lib
	SECTION:=Libraries
	CATEGORY:=Atlants
	SUBMENU:=Libraries
	TITLE:=buzzer_lib
	DEPENDS:=+librt +wiringPi
endef

define Package/buzzer_lib/description
	Buzzer library
endef

define Package/buzzer_lib/install
	$(INSTALL_DIR) $(1)/usr
	$(INSTALL_DIR) $(1)/usr/lib
	cp $(PKG_BUILD_DIR)/*.so* $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR)/usr
	$(INSTALL_DIR) $(STAGING_DIR)/usr/include/
	$(INSTALL_DIR) $(STAGING_DIR)/usr/lib
	cp $(PKG_BUILD_DIR)/*.so* $(STAGING_DIR)/usr/lib/
	cp $(PKG_BUILD_DIR)/include/*.h $(STAGING_DIR)/usr/include/
endef

$(eval $(call BuildPackage,buzzer_lib))
