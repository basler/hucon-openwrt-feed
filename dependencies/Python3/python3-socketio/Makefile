include $(TOPDIR)/rules.mk

PKG_NAME:=python3-socketio
PKG_VERSION:=5.0.4
PKG_RELEASE:=1
PKG_SOURCE:=python-socketio-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/37/91/7713854e0741f807c38ef084169b489ff6e87b24d1d9ba1e943bb9e10b8b/
PKG_HASH=f53fd0d5bd9f75a70492062f4ae6195ab5d34d67a29024d740f25e468392893e

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)
PKG_BUILD_DEPENDS:=python python3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk
#$(call include_mk, python3-package.mk)

define Package/python3-socketio
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-socketio
  URL:=https://pypi.org/project/python-engineio/
  DEPENDS:=+python3 +python3-engineio +python3-bidict
  VARIANT:=python3
endef

define Package/python3-socketio/description
  Python implementation of the Socket.IO realtime client and server. (socketio)
endef

$(eval $(call Py3Package,python3-socketio))
$(eval $(call BuildPackage,python3-socketio))
