dnl Process this file with autoconf to produce a configure script.
AC_REVISION($Revision: 1.7 $)dnl



m4_define([m4_REDBLACK_MAJOR_VERSION],[1])
m4_define([m4_REDBLACK_MINOR_VERSION],[4])
m4_define([m4_REDBLACK_VERSION],[m4_REDBLACK_MAJOR_VERSION.m4_REDBLACK_MINOR_VERSION])



dnl Library version info
dnl This should be one more than REDBLACK_MAJOR_VERSION
dnl incremented each time there is a major change to the interface
m4_define([m4_REDBLACK_LIB_CURRENT],[2])

dnl This should be set to zero everytime we DELETE from the interface
dnl It should be incremented every time we ADD to the interface
m4_define([m4_REDBLACK_LIB_AGE],[2])

dnl This should be incremented with every source code change
m4_define([m4_REDBLACK_LIB_REVISION],[m4_REDBLACK_MINOR_VERSION])

# For automake.
m4_define([m4_VERSION],[m4_REDBLACK_VERSION])
m4_define(m4_PACKAGE,[libredblack])



# cf https://www.gnu.org/software/automake/manual/html_node/Public-Macros.html

AC_INIT(m4_PACKAGE,m4_VERSION)
AC_PREREQ(2.61)
AC_CONFIG_AUX_DIR(tools)
AC_CONFIG_SRCDIR([redblack.c])
dnl Initialize the automake stuff
AM_INIT_AUTOMAKE([foreign])

AM_CONFIG_HEADER(config.h)

output_files="Makefile libredblack.spec"

dnl Checks for programs.
AC_PROG_CC
AC_PROG_INSTALL


AC_SUBST(REDBLACK_LIB_CURRENT,[m4_REDBLACK_LIB_CURRENT])
AC_SUBST(REDBLACK_LIB_REVISION,[m4_REDBLACK_LIB_REVISION])
AC_SUBST(REDBLACK_LIB_AGE, [m4_REDBLACK_LIB_AGE])
AC_SUBST(REDBLACK_MAJOR_VERSION, m4_REDBLACK_MAJOR_VERSION)
AC_SUBST(REDBLACK_MINOR_VERSION, m4_REDBLACK_MINOR_VERSION)


AC_SUBST(REDBLACK_VERSION, m4_REDBLACK_VERSION)


# --with-rbgen
AC_ARG_WITH(rbgen,
        AC_HELP_STRING([--with-rbgen], [Enable RB Code Generator (needs python)]),
	[], [with_rbgen=yes]
)

if test "$with_rbgen" = "yes"; then
  # --with-python=PATH
  AC_ARG_WITH(python,
	AC_HELP_STRING([--with-python=PATH],[Specify path to Python interpreter]),
	[PATH_PYTHON_PROG="$withval"],
	[AC_PATH_PROGS(PATH_PYTHON_PROG, python python2.4 python2.3 python2.2 \
		python2.1 python2.0 python1.6 python1.5 python1.4, false)]
  )
  if test "$PATH_PYTHON_PROG" = false
  then
	with_rbgen=no
  fi
fi

dnl Initialize libtool
AM_PROG_LIBTOOL

dnl Checks for libraries.

dnl Checks for header files.
AC_HEADER_STDC

dnl Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST

dnl Checks for library functions.
AC_CHECK_FUNCS(strdup)

AM_CONDITIONAL(USE_RBGEN, test "$with_rbgen" = "yes")

AC_OUTPUT(Makefile libredblack.spec rbgen, [chmod a+x rbgen])
