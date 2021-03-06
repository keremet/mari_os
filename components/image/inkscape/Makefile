#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"). You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Aurelien Larcher
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		inkscape
COMPONENT_VERSION=	0.91
COMPONENT_FMRI=		image/editor/inkscape
COMPONENT_CLASSIFICATION=	Applications/Graphics and Imaging
COMPONENT_SUMMARY=	Opensource professional vector graphics editor
COMPONENT_PROJECT_URL=	http://www.inkscape.org/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH=	\
    sha256:4d901f8a9e1924404e797ad23b8b0c495a9d155448816d95a55974314e1f141b
COMPONENT_ARCHIVE_URL=	http://inkscape.org/en/gallery/item/3860/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE = GPLv2

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

COMPONENT_PREP_ACTION =	( cd $(@D)  && \
				libtoolize --force &&\
				intltoolize --force --copy --automake &&\
				aclocal -I. &&\
				automake -a -c -f &&\
				autoconf)

CONFIGURE_OPTIONS+=  --enable-lcms
CONFIGURE_OPTIONS+=  --enable-poppler-cairo
CONFIGURE_OPTIONS+=  --disable-binreloc
CONFIGURE_OPTIONS+=  --with-gnome-vfs


build:		$(BUILD_32)

install:	$(INSTALL_32)

test:		$(TEST_32)

REQUIRED_PACKAGES += developer/gsl
REQUIRED_PACKAGES += image/imagemagick
REQUIRED_PACKAGES += image/library/libjpeg6
REQUIRED_PACKAGES += image/library/libjpeg6-ijg
REQUIRED_PACKAGES += image/library/libpng16
REQUIRED_PACKAGES += library/c++/glibmm
REQUIRED_PACKAGES += library/c++/libcdr
REQUIRED_PACKAGES += library/c++/librevenge
REQUIRED_PACKAGES += library/c++/libwpg
REQUIRED_PACKAGES += library/c++/sigcpp
REQUIRED_PACKAGES += library/desktop/c++/atkmm
REQUIRED_PACKAGES += library/desktop/c++/cairomm
REQUIRED_PACKAGES += library/desktop/c++/gtkmm
REQUIRED_PACKAGES += library/desktop/c++/pangomm
REQUIRED_PACKAGES += library/desktop/cairo
REQUIRED_PACKAGES += library/desktop/gdk-pixbuf
REQUIRED_PACKAGES += library/desktop/gtk2
REQUIRED_PACKAGES += library/desktop/gtkspell
REQUIRED_PACKAGES += library/desktop/pango
REQUIRED_PACKAGES += library/gc
REQUIRED_PACKAGES += library/glib2
REQUIRED_PACKAGES += library/gnome/gnome-vfs
REQUIRED_PACKAGES += library/lcms2
REQUIRED_PACKAGES += library/libpoppler
REQUIRED_PACKAGES += library/libxml2
REQUIRED_PACKAGES += library/libxslt
REQUIRED_PACKAGES += library/popt
REQUIRED_PACKAGES += library/zlib
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/fontconfig
REQUIRED_PACKAGES += system/library/freetype-2
REQUIRED_PACKAGES += system/library/g++-4-runtime
REQUIRED_PACKAGES += system/library/gcc-4-runtime
REQUIRED_PACKAGES += system/library/math
REQUIRED_PACKAGES += x11/library/libx11
