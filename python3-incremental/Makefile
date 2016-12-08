#
# Copyright (C) 2016 John Oliver Troxler
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=incremental
PKG_VERSION:=16.10.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/da/b0/32233c9e84b0d44b39015fba8fec03e88053723c1b455925081dc6ccd9e7
PKG_MD5SUM:=3fe6b3b1da1d26a48187fb27e969f072

PKG_BUILD_DEPENDS:=python3-setuptools

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=John Oliver Troxler <john.troxler@gmail.com>

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-incremental
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Library for versioning Python projects
  URL:=https://github.com/hawkowl/incremental
  DEPENDS:=+python3
endef

define Package/python3-incremental/description
  Incremental is a small library that versions your Python projects.

  This package provides the Python 3.x module.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,install \
		--prefix="/opt" \
		--root="$(PKG_INSTALL_DIR)", \
	)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(PYTHON3_LIB_DIR)
	$(CP) $(PKG_INSTALL_DIR)$(PYTHON3_PKG_DIR)/* $(PYTHON3_LIB_DIR)
endef

$(eval $(call Py3Package,python3-incremental))
$(eval $(call BuildPackage,python3-incremental))
