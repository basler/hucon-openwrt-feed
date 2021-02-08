include $(TOPDIR)/rules.mk
PKG_NAME:=hackerschool-server
PKG_VERSION:=1.6.0-a13
PKG_RELEASE:=0

REPOSITORY_PATH:=JonasTrampe/hucon

PKG_SOURCE:=hucon-$(PKG_VERSION).run
PKG_SOURCE_URL:=http://github.com/$(REPOSITORY_PATH)/releases/download/$(PKG_VERSION)/
PKG_HASH:=0760c9cd80b495dacf8c0cc928ae87f374b59547559f058d3a061584c22b602b
#PKG_SOURCE_SUBDIR:=$(PKG_NAME)
#PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

# base hackerschool package
define Package/hackerschool-server
  SECTION:=hackerschool
  CATEGORY:=Hackerschool
  SUBMENU:=hackerschool
  TITLE:=Hucon-Robot Webserver
  DEPENDS:=+curl +python3-light +python3-pip +python3-flask +python3-flask-socketio +python3-omega-expansion +python3-onion-i2c +python3-pwm-exp
endef


define Package/hackerschool-server/description
Hucon-Robot Webserver
endef

UNPACK_CMD:=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)

define Package/hackerschool-server/prepare
	(cd $(PKG_BUILD_DIR))
endef

define Build/Compile
	chmod +x $(PKG_BUILD_DIR)/$(PKG_SOURCE)
	mkdir -p $(PKG_BUILD_DIR)/opt/hucon
	mkdir -p $(PKG_BUILD_DIR)/etc/init.d
	mkdir -p $(PKG_BUILD_DIR)/usr/lib/python3.6/site-packages/
	$(PKG_BUILD_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/opt/ unpack
endef

define Package/hackerschool-server/install
	$(INSTALL_DIR) $(1)/opt/hucon
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/usr/lib/python3.6/site-packages/
	
	chmod +x $(PKG_BUILD_DIR)/opt/hucon/init.d/*
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/opt/hucon/init.d/* $(1)/etc/init.d/

	$(CP) -r \
		$(PKG_BUILD_DIR)/opt/hucon/__version__ \
		$(PKG_BUILD_DIR)/opt/hucon/README.md \
 		$(PKG_BUILD_DIR)/opt/hucon/LICENSE \
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

define Package/hackerschool-server/postinst
	#!/bin/sh
	# check if we are on real system
	if [ -z "$${IPKG_INSTROOT}" ]; then
		true
	fi
	exit 0
endef

# calls to build each package
$(eval $(call BuildPackage,hackerschool-server))
