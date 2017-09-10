#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mutagen
PKG_VERSION:=1.38
PKG_RELEASE:=1

PKG_SOURCE:=mutagen-1.38.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/57/ec/d7534cdb2766f1fee534a3aabdbdfbf05d6cf77cde617d77b526336a1a72
PKG_MD5SUM:=c54443dfb8d4ac088eb2a0c4fd569772
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-mutagen
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-mutagen
	URL:=https://pypi.python.org/pypi/mutagen
	DEPENDS+=+python
endef

define Package/python-mutagen/description
	Upstream mutagen package from pypi.python.org
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

define Package/python-mutagen/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-mutagen))
