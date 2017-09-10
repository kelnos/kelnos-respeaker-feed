#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=gpsoauth
PKG_VERSION:=0.4.1
PKG_RELEASE:=1

PKG_SOURCE:=gpsoauth-0.4.1.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/96/a1/2b366c602ee081def4dd80624581dfa8eb23d20c5a51f8a2591c40fa8d41
PKG_MD5SUM:=bdbdcb78b8f14670eac5c47d073e6a05
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-gpsoauth
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-gpsoauth
	URL:=https://pypi.python.org/pypi/gpsoauth
	DEPENDS+=+python +pycryptodomex +python-requests
endef

define Package/python-gpsoauth/description
	Upstream gpsoauth package from pypi.python.org
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

define Package/python-gpsoauth/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-gpsoauth))
