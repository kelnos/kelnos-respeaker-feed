#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=funcsigs
PKG_VERSION:=1.0.2
PKG_RELEASE:=1

PKG_SOURCE:=funcsigs-1.0.2.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/94/4a/db842e7a0545de1cdb0439bb80e6e42dfe82aaeaadd4072f2263a4fbed23
PKG_MD5SUM:=7e583285b1fb8a76305d6d68f4ccc14e
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-funcsigs
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-funcsigs
	URL:=https://pypi.python.org/pypi/funcsigs
	DEPENDS+=+python
endef

define Package/python-funcsigs/description
	Upstream funcsigs package from pypi.python.org
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

define Package/python-funcsigs/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-funcsigs))
