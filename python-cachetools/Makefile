#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=cachetools
PKG_VERSION:=2.0.1
PKG_RELEASE:=1

PKG_SOURCE:=cachetools-2.0.1.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/54/e4/ddaa319bf53f04cda4ef99201de1c402871151b6edefe631bd426dc621a3
PKG_MD5SUM:=d9ffa584355aa9b69a664bf8a82c4890
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-cachetools
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-cachetools
	URL:=https://pypi.python.org/pypi/cachetools
	DEPENDS+=+python
endef

define Package/python-cachetools/description
	Upstream cachetools package from pypi.python.org
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

define Package/python-cachetools/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-cachetools))
