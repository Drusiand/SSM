## Process this file with automake to produce Makefile.in
## Created by Anjuta

SUBDIRS = po

dist_doc_DATA = \
	README \
	COPYING \
	AUTHORS \
	ChangeLog \
	INSTALL \
	NEWS


INTLTOOL_FILES = intltool-extract.in \
	intltool-merge.in \
	intltool-update.in

AM_CPPFLAGS = \
        -DPACKAGE_LOCALE_DIR=\""$(localedir)"\" \
        -DPACKAGE_SRC_DIR=\""$(srcdir)"\" \
        -DPACKAGE_DATA_DIR=\""$(pkgdatadir)"\" \
	-IABCDE_SSM \
	-I/usr/include/boost \
        $(ABCDE_CFLAGS)

AM_CFLAGS =\
         -Wall\
         -g

bin_PROGRAMS = abcde

abcde_SOURCES = \
        ABCDE_SSM/abcde.cpp \
	ABCDE_SSM/deep.cpp \
	ABCDE_SSM/distr.cpp \
	ABCDE_SSM/main.cpp \
	ABCDE_SSM/solution.cpp

abcde_HEADERS = \
	ABCDE_SSM/abcde.h \
	ABCDE_SSM/config.h \
	ABCDE_SSM/deep.h \
	ABCDE_SSM/distr.h \
	ABCDE_SSM/model.h \
	ABCDE_SSM/pch.h \
	ABCDE_SSM/solution.h

abcdedir = \
        $(includedir)/abcde

abcde_CXXFLAGS = -fPIC \
                -fopenmp

abcde_CFLAGS = -fPIC

abcde_LDFLAGS = -fPIC

abcde_LDADD = $(ABCDE_LIBS) \
	-lboost_filesystem 

if NATIVE_WIN32
abcde_LDFLAGS += -mwindows
endif


EXTRA_DIST = \
	$(INTLTOOL_FILES)

DISTCLEANFILES = intltool-extract \
	intltool-merge \
	intltool-update \
	po/.intltool-merge-cache


# Remove doc directory on uninstall
uninstall-local:
	-rm -r $(docdir)
