#
# Copyright (C) 2016 John Oliver Troxler
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=constantly
PKG_VERSION:=15.1.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/95/f1/207a0a478c4bb34b1b49d5915e2db574cadc415c9ac3a7ef17e29b2e8951
PKG_MD5SUM:=f0762f083d83039758e53f8cf0086eef

PKG_BUILD_DEPENDS:=python3-setuptools

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=John Oliver Troxler <john.troxler@gmail.com>

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-constantly
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Symbolic constants in Python
  URL:=https://github.com/twisted/constantly
  DEPENDS:=+python3
endef

define Package/python3-constantly/description
  A library that provides symbolic constant support. It includes collections
  and constants with text, numeric, and bit flag values.

  Originally twisted.python.constants from the Twisted project.

  This package provides the Python 3.x module.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,install \
		--prefix="/opt" \
		--root="$(PKG_INSTALL_DIR)", \
	)
endef

$(eval $(call Py3Package,python3-constantly))
$(eval $(call BuildPackage,python3-constantly))
