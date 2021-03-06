#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2013, Oracle and/or its affiliates. All rights reserved.
#

include ../../make-rules/shared-macros.mk

COMPONENT_NAME=         mlocate
COMPONENT_VERSION=      0.25
COMPONENT_PROJECT_URL=  https://fedorahosted.org/mlocate
COMPONENT_SRC=          $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=      $(COMPONENT_SRC).tar.xz
COMPONENT_ARCHIVE_HASH= \
    sha256:ab95c111f9dba35b5690896180dd0a7639dbf07d70b862fcb0731264d9273951
COMPONENT_ARCHIVE_URL=  https://fedorahosted.org/releases/m/l/$(COMPONENT_NAME)/$(COMPONENT_ARCHIVE)

COMPONENT_BUGDB = utility/mlocate

include ../../make-rules/prep.mk
include ../../make-rules/configure.mk
include ../../make-rules/ips.mk

CONFIGURE_OPTIONS.64 +=    CC="$(CC) -m64"
CONFIGURE_OPTIONS += --localstatedir="/var/cache"
CONFIGURE_OPTIONS += --sysconfdir="/etc"

COMPONENT_PREP_ACTION = (cd $(@D) ; autoreconf -f && automake)
COMPONENT_POST_INSTALL_ACTION= \
    @$(MKDIR) -p $(PROTO_DIR)/etc/; \
    $(CP) files/updatedb.conf $(PROTO_DIR)/etc/ 

# Enable aslr for this component
ASLR_MODE = $(ASLR_ENABLE)

# common targets
build:		$(BUILD_32_and_64)

install:	$(INSTALL_32_and_64)
		
test:		$(NO_TESTS)

BUILD_PKG_DEPENDENCIES =	$(BUILD_TOOLS)

include ../../make-rules/depend.mk
