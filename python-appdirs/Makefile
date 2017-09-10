#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=appdirs
PKG_VERSION:=1.4.3
PKG_RELEASE:=1

PKG_SOURCE:=appdirs-1.4.3.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/48/69/d87c60746b393309ca30761f8e2b49473d43450b150cb08f3c6df5c11be5
PKG_MD5SUM:=44c679904082a2133f5566c8a0d3ab42
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-appdirs
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-appdirs
	URL:=https://pypi.python.org/pypi/appdirs
	DEPENDS+=+python
endef

define Package/python-appdirs/description
	Upstream appdirs package from pypi.python.org
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

define Package/python-appdirs/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-appdirs))
