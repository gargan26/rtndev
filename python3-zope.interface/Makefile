#
# Copyright (C) 2016 John Oliver Troxler
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=zope.interface
PKG_VERSION:=4.3.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/38/1b/d55c39f2cf442bd9fb2c59760ed058c84b57d25c680819c25f3aff741e1f
PKG_MD5SUM:=5f7e15a5bcdfa3c6c0e93ffe45caf87c

PKG_BUILD_DEPENDS:=python3 python3-setuptools

PKG_LICENSE:=ZPL-2.1
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=John Oliver Troxler <john.troxler@gmail.com>

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-zope.interface
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Python 3 Zope interface
  URL:=http://pypi.python.org/pypi/zope.interface
  DEPENDS:=+python3-light
endef

define Package/python3-zope.interface/description
  This package provides an implementation of "object interfaces" for Python.
  Interfaces are a mechanism for labeling objects as conforming to a given API
  or contract. So, this package can be considered as implementation of the
  Design By Contract methodology support in Python.

  This is the Python 3 version.
endef

define Py3Package/python3-zope.interface/filespec
+|$(PYTHON3_PKG_DIR)
-|$(PYTHON3_PKG_DIR)/zope/interface/common/tests
-|$(PYTHON3_PKG_DIR)/zope/interface/tests
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,, \
		install --prefix="/opt" --root="$(PKG_INSTALL_DIR)" --no-compile, \
	)
endef

$(eval $(call Py3Package,python3-zope.interface))
$(eval $(call BuildPackage,python3-zope.interface))
