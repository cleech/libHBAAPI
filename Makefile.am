lib_LTLIBRARIES = libHBAAPI.la
libHBAAPI_la_SOURCES = HBAAPILIB.c hbaapi.h vendorhbaapi.h
libHBAAPI_la_LDFLAGS = -version-info 2:2:0

nobase_include_HEADERS = hbaapi.h vendorhbaapi.h

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = HBAAPI.pc

dist_sysconf_DATA = hba.conf
dist_noinst_DATA = HBAAPI.pc.in libHBAAPI.spec

