#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.63])
AC_INIT([guile-noweb-autotools], [0.1.0], [you@somewhere.com])
AC_CONFIG_AUX_DIR([support/build-aux])

# We're going to use GNUMake and we're going to like it.
AM_INIT_AUTOMAKE([-Wall foreign -Wno-portability])
AM_EXTRA_RECURSIVE_TARGETS([run show-doc])
AC_CONFIG_MACRO_DIR([support/m4])
# Checks for programs.
AC_PROG_CC_C_O
# CXX required for OpenGL, GL, and GLUT libraries.
AC_PROG_LIBTOOL
AX_CHECK_NOWEB
AC_PATH_PROG([PERL], [perl])
AC_SUBST([PERL])

AC_PATH_PROG([BASH], [bash])
AC_SUBST([BASH])

AC_PATH_PROG([guile_snarf], guile-snarf)
AC_SUBST(guile_snarf)

# Checks for libraries.
PKG_CHECK_MODULES([GUILE], [guile-2.0])

# Checks for header files.
AC_HEADER_STDC
AC_CHECK_HEADERS([stdio.h])

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.
AC_CHECK_FUNCS([puts])

AC_SUBST(ENV, ['${top_builddir}/bin/env'])
AC_SUBST(imagedir, ['${top_srcdir}/support/image'])
AC_SUBST(automakedir, ['${top_srcdir}/support/automake'])
pdflatex="TEXINPUTS=${imagesdir}: $pdflatex";

# Output files.
AC_CONFIG_HEADERS([src/config.h])
AC_CONFIG_FILES([ Makefile
                  bin/Makefile 
                  src/Makefile 
                  tests/Makefile 
                  ], [])
AC_CONFIG_FILES([ tests/works-without-noweb.sh ], [chmod +x tests/works-without-noweb.sh])
AC_CONFIG_FILES([bin/env], [chmod a+x bin/env])
AC_CONFIG_FILES([bin/warn-notangle], [chmod a+x bin/warn-notangle])

AC_OUTPUT
