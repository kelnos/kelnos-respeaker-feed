#
# Copyright (c) 2017 Brian Tarricone <brian@tarricone.org>
#
# Licenced under the 2-clause BSD licence.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=Mopidy-GMusic
PKG_VERSION:=2.0.0
PKG_RELEASE:=1

PKG_SOURCE:=Mopidy-GMusic-2.0.0.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/02/af/a313c837c63b10deadee22dcf453b0ec15a7e33c4e35a604f532559a68b6
PKG_MD5SUM:=aab1981070f399b548ea8eaac4b49294
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/mopidy-gmusic
	SECTION:=Python
	CATEGORY:=ReSpeaker
	TITLE:=mopidy-gmusic
	URL:=https://pypi.python.org/pypi/Mopidy-GMusic
	DEPENDS+=+python +mopidy +pykka +python-cachetools +python-gmusicapi +python-requests +python-setuptools +glib-networking
endef

define Package/mopidy-gmusic/description
	Upstream Mopidy-GMusic package from pypi.python.org
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

define Package/mopidy-gmusic/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,mopidy-gmusic))
