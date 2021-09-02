include $(TOPDIR)/rules.mk

PKG_NAME:=python3-bidict
PKG_VERSION:=0.20.0
PKG_RELEASE:=1
PKG_SOURCE:=bidict-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/cb/fa/8d7be0a97276d9c0ea704e8c7a9f426850bbaad94671615970eda3d8d290/
PKG_HASH=c1b1ce1c0f1e3457489672bc3a4db375a06f61ae7797a9eedf71ea788cea3870

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
