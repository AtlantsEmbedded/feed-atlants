include $(TOPDIR)/rules.mk

PKG_NAME:=GPIO_interface
PKG_VERSION:=2014-26-14
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/AtlantsEmbedded/atlants-GPIO_interface.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=+wiringPi

include $(INCLUDE_DIR)/package.mk

define Package/GPIO_interface
	SECTION:=Interfaces
	CATEGORY:=Atlants
	TITLE:=GPIO_interface
	SUBMENU:=Interfaces
	DEPENDS:=+librt +libpthread +libezxml +glib2 wiringPi
endef

define Package/GPIO_interface/description
	Application which will act as both a server for the LCD \
	and for button presses.
endef

define Package/GPIO_interface/install
	$(INSTALL_DIR) $(1)/atlants
	$(INSTALL_DIR) $(1)/atlants/gpio
	$(INSTALL_DIR) $(1)/atlants/gpio/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/gpio-daemon/config/gpio_config.xml $(1)/atlants/gpio/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/gpio-daemon/gpio_interface $(1)/atlants/gpio
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/gpio-ipc-client/gpio_ipc_client $(1)/atlants/gpio
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DIR) $(1)/etc/init.d/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/scripts/gpio $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,GPIO_interface,+wiringPi))
