#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=gmusicapi
PKG_VERSION:=10.1.2
PKG_RELEASE:=1

PKG_SOURCE:=gmusicapi-10.1.2.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/44/44/fe21b95528cabcb7fbbe79860d650b00b615b12ae4e54c2ed3c2cc86e9cd
PKG_MD5SUM:=f9cf1c1c92940073c89abaac5c9da612
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-gmusicapi
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=python-gmusicapi
	URL:=https://pypi.python.org/pypi/gmusicapi
	DEPENDS+=+python +python-mechanicalsoup +python-appdirs +python-decorator +python-future +python-gpsoauth +python-mock +python-mutagen +python-oauth2client +python-proboscis +python-protobuf +python-dateutil +python-requests +python-six +python-validictory
endef

define Package/python-gmusicapi/description
	Upstream gmusicapi package from pypi.python.org
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

define Package/python-gmusicapi/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-gmusicapi))
