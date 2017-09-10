#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=validictory
PKG_VERSION:=1.1.1
PKG_RELEASE:=1

PKG_SOURCE:=validictory-1.1.1.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/18/af/6f633257c16f66e3d7029db3706f2802dc822b45acfdb5b9bad19fa65594
PKG_MD5SUM:=7e6e7045d822465b92c76c1176f9018f
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-validictory
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-validictory
	URL:=https://pypi.python.org/pypi/validictory
	DEPENDS+=+python
endef

define Package/python-validictory/description
	Upstream validictory package from pypi.python.org
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

define Package/python-validictory/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-validictory))
