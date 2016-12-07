#
# Copyright (C) 2016 John Oliver Troxler
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=Twisted
PKG_VERSION:=16.4.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://pypi.python.org/packages/6b/23/8dbe86fc83215015e221fbd861a545c6ec5c9e9cd7514af114d1f64084ab
PKG_MD5SUM:=c6d09bdd681f538369659111f079c29d

PKG_BUILD_DEPENDS:=python3 python3-setuptools

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=John Oliver Troxler <john.troxler@gmail.com>

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-twisted
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Python 3 Event-based framework for internet applications
  URL:=http://twistedmatrix.com/
  DEPENDS:=+python3 +python3-zope.interface
endef

define Package/python3-twisted/description
  Twisted is a networking engine written in Python, supporting numerous
  protocols. It contains a web server, numerous chat clients, chat servers,
  mail servers, and more.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,, \
		install --prefix="/opt" --root="$(PKG_INSTALL_DIR)" --no-compile, \
	)
	$(SED) 's,#!.*,#!/opt/bin/python3,' $(PKG_INSTALL_DIR)/opt/bin/*
endef

$(eval $(call Py3Package,python3-twisted))
$(eval $(call BuildPackage,python3-twisted))
