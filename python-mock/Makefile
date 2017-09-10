#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mock
PKG_VERSION:=2.0.0
PKG_RELEASE:=1

PKG_SOURCE:=mock-2.0.0.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/0c/53/014354fc93c591ccc4abff12c473ad565a2eb24dcd82490fae33dbf2539f
PKG_MD5SUM:=0febfafd14330c9dcaa40de2d82d40ad
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-mock
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-mock
	URL:=https://pypi.python.org/pypi/mock
	DEPENDS+=+python +python-funcsigs +python-pbr +python-six
endef

define Package/python-mock/description
	Upstream mock package from pypi.python.org
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

define Package/python-mock/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-mock))
