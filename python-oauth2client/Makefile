#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=oauth2client
PKG_VERSION:=4.1.2
PKG_RELEASE:=1

PKG_SOURCE:=oauth2client-4.1.2.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/50/30/f89a4fc014a03e180840d432e73ffb96da422f2a8094ff3539f0f0c46661
PKG_MD5SUM:=bc30976cd1e859cd6199264a50c5ba72
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-oauth2client
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-oauth2client
	URL:=https://pypi.python.org/pypi/oauth2client
	DEPENDS+=+python +python-httplib2 +pyasn1-modules +pyasn1 +python-rsa +python-six
endef

define Package/python-oauth2client/description
	Upstream oauth2client package from pypi.python.org
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

define Package/python-oauth2client/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-oauth2client))
