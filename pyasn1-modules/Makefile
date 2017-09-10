#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyasn1-modules
PKG_VERSION:=0.1.4
PKG_RELEASE:=1

PKG_SOURCE:=pyasn1-modules-0.1.4.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/66/6b/f5582cbf3b920896ce1b97bde3894599b3dec31301ef79ae7ea0022f5577
PKG_MD5SUM:=c90b071d0dfe23dc25669c71e9b91c46
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/pyasn1-modules
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=pyasn1-modules
	URL:=https://pypi.python.org/pypi/pyasn1-modules
	DEPENDS+=+python +pyasn1
endef

define Package/pyasn1-modules/description
	Upstream pyasn1-modules package from pypi.python.org
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

define Package/pyasn1-modules/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,pyasn1-modules))
