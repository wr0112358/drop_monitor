#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([drop_monitor], [0.1], [wr0112358@gmail.com])
AM_INIT_AUTOMAKE([foreign])

AC_CONFIG_SRCDIR([src/dwarf_lookup.cc])
#AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_TYPE_SIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T

AC_CONFIG_MACRO_DIR(m4)

AX_CXX_COMPILE_STDCXX([14], [noext], [optional])
AC_LANG([C++])
#AX_CXX_COMPILE_STDCXX([14], [noext], [optional])
#AX_CXX_COMPILE_STDCXX([11], [noext], [mandatory])

m4_pattern_forbid([PKG_CHECK_MODULES])
PKG_CHECK_MODULES([libnl3], [libnl-3.0 >= 3.2.3])
PKG_CHECK_MODULES([libnl_genl3], [libnl-genl-3.0 >= 3.2.3])


AC_CHECK_LIB(nl-3, nl_socket_alloc,, [AC_MSG_ERROR([libnl-3.0 required but not found])])
AC_CHECK_LIB(dw, dwfl_begin,, [AC_MSG_ERROR([libdw(elfutils) required but not found])])
#AC_CHECK_LIB(asan, __sanitizer_cov_init)

# Checks for library functions.
AC_CHECK_FUNCS([memchr memset strdup strerror strtoul])

#AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES(Makefile src/Makefile man/Makefile)
#AC_OUTPUT(Makefile src/Makefile man/Makefile)
AC_OUTPUT
