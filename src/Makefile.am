lib_LTLIBRARIES = liblbxutil.la

AM_CFLAGS = $(CWARNFLAGS) $(LBXUTIL_CFLAGS)
AM_CPPFLAGS = -I$(top_srcdir)/include

noinst_PROGRAMS = mkg3states

mkg3states_SOURCES =				\
	$(srcdir)/image/mkg3states.c

liblbxutil_la_SOURCES =				\
	$(srcdir)/lbx_zlib/reqstats.h		\
	$(srcdir)/lbx_zlib/lbx_zlib_io.c	\
	$(srcdir)/lbx_zlib/lbx_zlib.h		\
	$(srcdir)/lbx_zlib/lbx_zlib.c		\
	$(srcdir)/lbx_zlib/reqstats.c		\
	$(srcdir)/image/misc.c			\
	$(srcdir)/image/dpackbits.c		\
	$(srcdir)/image/epackbits.c		\
	$(srcdir)/image/dfaxg42d.c		\
	$(srcdir)/image/lbxfax.h		\
	$(srcdir)/image/efaxg42d.c		\
	$(srcdir)/image/lbxbwcodes.h		\
	$(srcdir)/delta/lbxdelta.c

extensiondir=${includedir}/X11/extensions
extension_HEADERS =						\
	$(top_srcdir)/include/X11/extensions/lbxbuf.h		\
	$(top_srcdir)/include/X11/extensions/lbxbufstr.h	\
	$(top_srcdir)/include/X11/extensions/lbxdeltastr.h	\
	$(top_srcdir)/include/X11/extensions/lbximage.h		\
	$(top_srcdir)/include/X11/extensions/lbxopts.h		\
	$(top_srcdir)/include/X11/extensions/lbxzlib.h

nodist_liblbxutil_la_SOURCES = g3states.h

liblbxutil_la_LIBADD = $(LBXUTIL_LIBS)

$(srcdir)/image/dfaxg42d.c: g3states.h

g3states.h: mkg3states
	-rm -f g3states.h
	$(AM_V_GEN) ./mkg3states -c > g3states.h_ && mv g3states.h_ g3states.h

liblbxutil_la_LDFLAGS = -version-number 1:0:0 -no-undefined

CLEANFILES = g3states.h
