include $(TOPDIR)/rules.mk

PKG_NAME:=python3-bidict
PKG_VERSION:=0.21.2
PKG_RELEASE:=1
PKG_SOURCE:=bidict-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/bd/7c/83fbbc8568be511bc48704b97ef58f67ff2ab85ec4fcd1dad12cd2323c32/
PKG_HASH=4fa46f7ff96dc244abfc437383d987404ae861df797e2fd5b190e233c302be09

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)
PKG_BUILD_DEPENDS:=python python3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk
#$(call include_mk, python3-package.mk)

define Package/python3-bidict
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-bidict
  URL:=https://pypi.org/project/python3-bidict/
  DEPENDS:=+python3
  VARIANT:=python3
endef

define Package/python3-bidict/description
  The bidirectional mapping library for Python. (python3-bidict)
endef

$(eval $(call Py3Package,python3-bidict))
$(eval $(call BuildPackage,python3-bidict))
