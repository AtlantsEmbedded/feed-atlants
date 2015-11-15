include $(TOPDIR)/rules.mk

PKG_NAME:=braintone_app
PKG_VERSION:=2015-11-06
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=svn
PKG_SOURCE_URL:=http://svn.code.sf.net/p/atomproducts/svn/trunk/src/braintone_app
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/braintone_app
	SECTION:=Applications
	CATEGORY:=Atom
	TITLE:=braintone_app
	SUBMENU:=Interfaces
	DEPENDS:=wiringPi +librt +libpthread +libezxml +glib2
endef

define Package/braintone_app/description
	Piezobuzzer-based Neurofeedback application for the Pi
endef

define Package/braintone_app/install
	$(INSTALL_DIR) $(1)/atom
	$(INSTALL_DIR) $(1)/atom/app
	$(INSTALL_DIR) $(1)/atom/app/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/braintone_app $(1)/atom/app
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/config/braintone_app_config.xml $(1)/atom/app/config
endef

$(eval $(call BuildPackage,braintone_app))