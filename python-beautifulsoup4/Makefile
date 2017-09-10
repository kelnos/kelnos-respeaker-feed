#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=beautifulsoup4
PKG_VERSION:=4.6.0
PKG_RELEASE:=1

PKG_SOURCE:=beautifulsoup4-4.6.0.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/fa/8d/1d14391fdaed5abada4e0f63543fef49b8331a34ca60c88bd521bcf7f782
PKG_MD5SUM:=c17714d0f91a23b708a592cb3c697728
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-beautifulsoup4
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-beautifulsoup4
	URL:=https://pypi.python.org/pypi/beautifulsoup4
	DEPENDS+=+python
endef

define Package/python-beautifulsoup4/description
	Upstream beautifulsoup4 package from pypi.python.org
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

define Package/python-beautifulsoup4/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-beautifulsoup4))
