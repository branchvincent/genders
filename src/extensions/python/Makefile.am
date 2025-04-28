##*****************************************************************************
## $Id: Makefile.am,v 1.25 2009-08-12 23:35:19 chu11 Exp $
##*****************************************************************************
## Process this file with automake to produce Makefile.in.
##*****************************************************************************

# Use Python's distutils to make/install everything into the right place.

# DESTDIR is usually set during make install time, not configure or
# make time, so we work around it with the --with-extension-destdir
# autoconf option.

PYTHON_DESTDIR = @EXTENSION_DESTDIR@

if WITH_PYTHON_EXTENSIONS
all: pyproject.toml libgendersmodule.c genders.py
	$(PYTHON) -m pip wheel .

install pure_install install-data-local:
	$(PYTHON) -m pip install --prefix=$(PYTHON_DESTDIR)$(prefix) .

clean:
	rm -rf build

endif

EXTRA_DIST = pyproject.toml libgendersmodule.c genders.py
