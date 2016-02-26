include $(TOPDIR)/rules.mk

PKG_NAME:=stats_lib
PKG_VERSION:=2015-28-05
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/AtlantsEmbedded/atlants-stats_lib.git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/stats_lib
	SECTION:=Libraries
	CATEGORY:=Atlants
	SUBMENU:=Libraries
	TITLE:=stats_lib
	DEPENDS:=+librt
endef

define Package/stats_lib/description
	Basic stats library
endef

define Package/stats_lib/install
	$(INSTALL_DIR) $(1)/usr
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include
	cp $(PKG_BUILD_DIR)/*.so* $(1)/usr/lib/
	cp $(PKG_BUILD_DIR)/*.h $(1)/usr/include/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR)/usr
	$(INSTALL_DIR) $(STAGING_DIR)/usr/include/
	$(INSTALL_DIR) $(STAGING_DIR)/usr/lib
	cp $(PKG_BUILD_DIR)/*.so* $(STAGING_DIR)/usr/lib/
	cp $(PKG_BUILD_DIR)/*.h $(STAGING_DIR)/usr/include/

endef

$(eval $(call BuildPackage,stats_lib))
