include $(TOPDIR)/rules.mk

PKG_NAME:=python3-engineio
PKG_VERSION:=3.14.2
PKG_RELEASE:=1
PKG_SOURCE:=python-engineio-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/7d/a3/9491c16fae684011c51cc94513e17153bacfb5509c71c68dde6c5abd51fc/
PKG_HASH=eab4553f2804c1ce97054c8b22cf0d5a9ab23128075248b97e1a5b2f29553085

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)
PKG_BUILD_DEPENDS:=python python3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk
#$(call include_mk, python3-package.mk)

define Package/python3-engineio
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-engineio
  URL:=https://pypi.org/project/engineio/
  DEPENDS:=+python3 +python3-bidict
  VARIANT:=python3
endef

define Package/python3-engineio/description
  Python implementation of the Engine.IO realtime client and server. (python-engineio)
endef

$(eval $(call Py3Package,python3-engineio))
$(eval $(call BuildPackage,python3-engineio))
