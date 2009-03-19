lib_LTLIBRARIES = libHBAAPI.la
libHBAAPI_la_SOURCES = hbaapi.h vendorhbaapi.h
nodist_libHBAAPI_la_SOURCES = hbaapilib.c
libHBAAPI_la_LDFLAGS = -version-info 2:2:0

nobase_include_HEADERS = hbaapi.h vendorhbaapi.h

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = HBAAPI.pc

dist_sysconf_DATA = hba.conf
dist_noinst_DATA = HBAAPILIB.c HBAAPI.pc.in libHBAAPI.spec hbaapi2.2.patch

hbaapilib.c: ${srcdir}/HBAAPILIB.c ${srcdir}/hbaapi2.2.patch
	cp ${srcdir}/HBAAPILIB.c $@
	patch $@ < ${srcdir}/hbaapi2.2.patch

clean-local:
	-rm -f hbaapilib.c
	-if [ ${abs_srcdir} != ${abs_builddir} ]; then \
		rm -f hba.conf; \
	fi

# re-write hba.conf to edit out everything except for comments and blank lines
FORCE:
hba.conf: FORCE
	grep "^#\|^[[:space:]]*$$" ${srcdir}/$@ > $@.tmp
	mv $@.tmp $@

