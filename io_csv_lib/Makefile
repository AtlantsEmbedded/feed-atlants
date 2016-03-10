include $(TOPDIR)/rules.mk

PKG_NAME:=io_csv_lib
PKG_VERSION:=2016-03-10
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/AtlantsEmbedded/atlants-io_csv_lib.git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/io_csv_lib
	SECTION:=Libraries
	CATEGORY:=Atlants
	SUBMENU:=Libraries
	TITLE:=io_csv_lib
	DEPENDS:=+librt
endef

define Package/io_csv_lib/description
	CSV output library
endef

define Package/io_csv_lib/install
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

$(eval $(call BuildPackage,io_csv_lib))
