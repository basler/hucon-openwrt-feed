include $(TOPDIR)/rules.mk

PKG_NAME:=python3-engineio
PKG_VERSION:=4.0.0
PKG_RELEASE:=1
PKG_SOURCE:=python-engineio-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/92/e8/2dd4bd782b593adcc0bdce0675fe92016c3ffca061202142fcf1e55cbf6a/
PKG_HASH=9f34afa4170f5ba6e3d9ff158752ccf8fbb2145f16554b2f0fc84646675be99a

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
