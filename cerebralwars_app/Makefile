include $(TOPDIR)/rules.mk

PKG_NAME:=cerebralwars_app
PKG_VERSION:=2015-11-06
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/AtlantsEmbedded/atlants-cerebral_wars.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/cerebralwars_app
	SECTION:=Applications
	CATEGORY:=Atlants
	TITLE:=cerebralwars_app
	SUBMENU:=Applications
	DEPENDS:=wiringPi +librt +libpthread +libezxml +glib2
endef

define Package/cerebralwars_app/description
	Two players competitive game running on the IntelliPi
endef

define Package/cerebralwars_app/install
	$(INSTALL_DIR) $(1)/intelli
	$(INSTALL_DIR) $(1)/intelli/app
	$(INSTALL_DIR) $(1)/intelli/app/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/cerebralwars_app $(1)/intelli/app
endef

$(eval $(call BuildPackage,cerebralwars_app))
