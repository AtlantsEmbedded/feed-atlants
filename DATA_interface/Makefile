include $(TOPDIR)/rules.mk

PKG_NAME:=DATA_interface
PKG_VERSION:=2015-08-12
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/AtlantsEmbedded/atlants-DATA_interface.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/DATA_interface
	SECTION:=Interfaces
	CATEGORY:=Atlants
	TITLE:=DATA_interface
	SUBMENU:=Interfaces
	DEPENDS:=+wiringPi +libpthread +libezxml +glib2 +bluez-libs +bluez-utils +io_csv_lib
endef

define Package/DATA_interface/description
	Application which will act as the interface for gathering \
 data to be used for analysis - this includes Bluetooth EEGs
endef

define Package/DATA_interface/install
	$(INSTALL_DIR) $(1)/intelli
	$(INSTALL_DIR) $(1)/intelli/data
	$(INSTALL_DIR) $(1)/intelli/data/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/data-daemon/config/* $(1)/intelli/data/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/data-daemon/data_interface $(1)/intelli/data
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DIR) $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,DATA_interface))
