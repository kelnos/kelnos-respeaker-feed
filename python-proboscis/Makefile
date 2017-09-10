#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=proboscis
PKG_VERSION:=1.2.6.0
PKG_RELEASE:=1

PKG_SOURCE:=proboscis-1.2.6.0.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/3c/c8/c187818ab8d0faecdc3c16c1e0b2e522f3b38570f0fb91dcae21662019d0
PKG_MD5SUM:=e4b36449ef7c18f70b8243f4c8bddbca
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-proboscis
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-proboscis
	URL:=https://pypi.python.org/pypi/proboscis
	DEPENDS+=+python
endef

define Package/python-proboscis/description
	Upstream proboscis package from pypi.python.org
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

define Package/python-proboscis/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-proboscis))
