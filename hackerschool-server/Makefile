include $(TOPDIR)/rules.mk
PKG_NAME:=hackerschool-server
PKG_VERSION:=1.5.0
PKG_RELEASE:=0

REPOSITORY_PATH:=basler/hucon

PKG_SOURCE:=hucon-$(PKG_VERSION).run
PKG_SOURCE_URL:=http://github.com/$(REPOSITORY_PATH)/releases/download/$(PKG_VERSION)/
PKG_HASH:=b08b2d7864f009d277356aa2556a4b9979538060ba8ee00d203e7157c5b36d70
#PKG_SOURCE_SUBDIR:=$(PKG_NAME)
#PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

# base hackerschool package
define Package/$(PKG_NAME)
	SECTION:=hackerschool
	CATEGORY:=Hackerschool
	SUBMENU:=hackerschool
	TITLE:=Hucon-Robot Webserver
	DEPENDS:=+python-flask
endef


define Package/$(PKG_NAME)/description
Hucon-Robot Webserver
endef

UNPACK_CMD:=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)

define Package/$(PKG_NAME)/prepare
        (cd $(PKG_BUILD_DIR))
endef

define Build/Compile
	chmod +x $(PKG_BUILD_DIR)/$(PKG_SOURCE)
	mkdir -p $(PKG_BUILD_DIR)/opt/hucon
	mkdir -p $(PKG_BUILD_DIR)/etc/init.d
	mkdir -p $(PKG_BUILD_DIR)/usr/lib/python2.7/site-packages/
	$(PKG_BUILD_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/opt/ unpack
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/opt/hucon
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/usr/lib/python2.7/site-packages/

	chmod +x $(PKG_BUILD_DIR)/opt/hucon/init.d/*
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/opt/hucon/init.d/* $(1)/etc/init.d/

	$(CP) -r $(PKG_BUILD_DIR)/opt/hucon/__version__ \
		 $(PKG_BUILD_DIR)/opt/hucon/README.md \
		 $(PKG_BUILD_DIR)/opt/hucon/code/ \
		 $(PKG_BUILD_DIR)/opt/hucon/python_lib/ \
		 $(PKG_BUILD_DIR)/opt/hucon/webserver/ \
		 $(PKG_BUILD_DIR)/opt/hucon/i2c_led.sh \
		 $(PKG_BUILD_DIR)/opt/hucon/start_server.sh \
		 $(PKG_BUILD_DIR)/opt/hucon/uninstall.sh \
		 $(PKG_BUILD_DIR)/opt/hucon/update.sh \
		 $(1)/opt/hucon

	$(PKG_BUILD_DIR)/opt/hucon/img_install.sh $(1)
endef

define Package/$(PKG_NAME)/postinst
#!/bin/sh
# check if we are on real system
if [ -z "$${IPKG_INSTROOT}" ]; then
	true
fi
exit 0
endef

# calls to build each package
$(eval $(call BuildPackage,$(PKG_NAME)))
