include $(top_srcdir)/support/automake/noweb.am
include $(top_srcdir)/support/automake/guile.am

.SECONDARY:

BUILT_SOURCES = $(NOWEB_BUILT_FILES)
CLEANFILES = $(NOWEB_CLEANFILES) hello-world.c.x 

WARN_NOTANGLE = $(top_builddir)/bin/warn-notangle

dist-hook:
	cp $(distdir)/*.pdf $(top_distdir)

NOWEB_DOCS = hello-world-paper.pdf
NOWEB_FILES = hello-world.nw
NOWEB_PRODUCTS = hello-world.c hello-world.h hello-world.scm
EXTRA_DIST = $(NOWEB_DOCS) $(NOWEB_EXTRA_DIST)

doc-local : 	hello-world-paper.pdf

hello-world-paper.pdf : hello-world.tex

hello-world.o : hello-world.c.x

bin_PROGRAMS = hello-world

lib_LTLIBRARIES = libguile-hello-world.la

AM_CFLAGS  = $(GUILE_CFLAGS)
hello_world_LDADD   = $(GUILE_LIBS)
hello_world_LDFLAGS = $(GUILE_LDFLAGS)
hello_world_SOURCES = hello-world.c

libguile_hello_world_la_LIBADD  = $(GUILE_LIBS)
libguile_hello_world_la_SOURCES = hello-world.c
include_HEADERS = hello-world.h 

MAINTAINERCLEANFILES = Makefile.in config.h.in 
