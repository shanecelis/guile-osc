include $(top_srcdir)/support/automake/noweb.am
include $(top_srcdir)/support/automake/guile.am

.SECONDARY:

NOWEAVE_FLAGS = -n -delay
BUILT_SOURCES = $(NOWEB_BUILT_FILES) osc.c.x 
CLEANFILES = $(NOWEB_CLEANFILES) osc.c.x 

WARN_NOTANGLE = $(top_builddir)/bin/warn-notangle

dist-hook:
	cp $(distdir)/*.pdf $(top_distdir)

NOWEB_DOCS = osc.pdf
NOWEB_FILES = osc.nw
NOWEB_PRODUCTS = osc.c osc.h osc.scm osc-test.scm
EXTRA_DIST = $(NOWEB_DOCS) $(NOWEB_EXTRA_DIST)

osc.o : osc.c.x

check_PROGRAMS = 

TESTS = osc-test.scm
TEST_EXTENSIONS = .scm 
SCM_LOG_COMPILER = $(ENV) guile 

lib_LTLIBRARIES = libguile-osc.la

guilemoduledir = $(prefix)/share/guile/site/
dist_guilemodule_DATA = osc.scm

AM_CFLAGS  = $(GUILE_CFLAGS) $(LO_CFLAGS)
# hello_world_test_c_LDADD   = $(GUILE_LIBS) libguile-osc.la
# hello_world_test_c_LDFLAGS = $(GUILE_LDFLAGS)
# hello_world_test_c_SOURCES = osc-test.c

libguile_osc_la_LIBADD  = $(GUILE_LIBS) $(LO_LIBS)
libguile_osc_la_SOURCES = osc.c
include_HEADERS = osc.h 

MAINTAINERCLEANFILES = Makefile.in config.h.in osc-test
