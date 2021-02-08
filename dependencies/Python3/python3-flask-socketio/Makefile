include $(TOPDIR)/rules.mk

PKG_NAME:=python3-flask-socketio
PKG_VERSION:=5.0.1
PKG_RELEASE:=1
PKG_SOURCE:=Flask-SocketIO-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/06/7f/7496b6684e2b8eadb150555fa979497303459a31cb7dc592a5da51900090/
PKG_HASH=5c4319f5214ada20807857dc8fdf3dc7d2afe8d6dd38f5c516c72e2be47d2227

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)
PKG_BUILD_DEPENDS:=python python3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk
#$(call include_mk, python3-package.mk)

define Package/python3-flask-socketio
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-flask-socketio
  URL:=https://pypi.org/project/python-socketio
  DEPENDS:=+python3 +python3-flask +python3-socketio
  VARIANT:=python3
endef

define Package/python3-flask-socketio/description
  Socket.IO integration for Flask applications. (flask-socketio)
endef

$(eval $(call Py3Package,python3-flask-socketio))
$(eval $(call BuildPackage,python3-flask-socketio))
