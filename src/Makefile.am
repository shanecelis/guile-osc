include $(top_srcdir)/support/automake/noweb.am
include $(top_srcdir)/support/automake/guile.am

.SECONDARY:

NOWEAVE_FLAGS = -n -delay
BUILT_SOURCES = $(NOWEB_BUILT_FILES) hello-world.c.x 
CLEANFILES = $(NOWEB_CLEANFILES) hello-world.c.x 

WARN_NOTANGLE = $(top_builddir)/bin/warn-notangle

dist-hook:
	cp $(distdir)/*.pdf $(top_distdir)

NOWEB_DOCS = hello-world.pdf
NOWEB_FILES = hello-world.nw
NOWEB_PRODUCTS = hello-world.c hello-world.h hello-world.scm hello-world-test.c hello-world-test.scm
EXTRA_DIST = $(NOWEB_DOCS) $(NOWEB_EXTRA_DIST)

doc-local : 	hello-world.pdf

hello-world.o : hello-world.c.x

check_PROGRAMS = hello-world-test-c

TESTS = hello-world-test-c hello-world-test.scm
TEST_EXTENSIONS = .scm 
SCM_LOG_COMPILER = $(ENV) guile 

lib_LTLIBRARIES = libguile-hello-world.la

AM_CFLAGS  = $(GUILE_CFLAGS)
hello_world_test_c_LDADD   = $(GUILE_LIBS) libguile-hello-world.la
hello_world_test_c_LDFLAGS = $(GUILE_LDFLAGS)
hello_world_test_c_SOURCES = hello-world-test.c

libguile_hello_world_la_LIBADD  = $(GUILE_LIBS)
libguile_hello_world_la_SOURCES = hello-world.c
include_HEADERS = hello-world.h 

MAINTAINERCLEANFILES = Makefile.in config.h.in hello-world-test
