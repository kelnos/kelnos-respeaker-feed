#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=MechanicalSoup
PKG_VERSION:=0.7.0
PKG_RELEASE:=1

PKG_SOURCE:=MechanicalSoup-0.7.0.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/f4/f5/359baf84062bfe3df1ac89456cbfc4f674941964f875caae4e316a8c59ef
PKG_MD5SUM:=7cb538573e7bfc1afd55262373fc6b58
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-mechanicalsoup
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-mechanicalsoup
	URL:=https://pypi.python.org/pypi/MechanicalSoup
	DEPENDS+=+python +python-beautifulsoup4 +python-requests +python-six
endef

define Package/python-mechanicalsoup/description
	Upstream MechanicalSoup package from pypi.python.org
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

define Package/python-mechanicalsoup/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-mechanicalsoup))
