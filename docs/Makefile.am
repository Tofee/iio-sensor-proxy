NULL =

AUTOMAKE_OPTIONS = 1.7

# The name of the module.
DOC_MODULE=iio-sensor-proxy

# The top-level SGML file.
DOC_MAIN_SGML_FILE=iio-sensor-proxy-docs.xml

# Extra options to supply to gtkdoc-scan
SCAN_OPTIONS=--ignore-headers=config.h --rebuild-sections --rebuild-types

# The directory containing the source code. Relative to $(srcdir)
DOC_SOURCE_DIR=

# Used for dependencies
HFILE_GLOB=
CFILE_GLOB=

# Headers to ignore
IGNORE_HFILES= \
	$(NULL)

GTKDOC_LIBS =

# Extra options to supply to gtkdoc-mkdb
MKDB_OPTIONS=--sgml-mode --output-format=xml

# Extra options to supply to gtkdoc-mktmpl
MKTMPL_OPTIONS=

docs-net.hadess.SensorProxy.xml: $(top_srcdir)/src/net.hadess.SensorProxy.xml
	$(AM_V_GEN)$(GDBUS_CODEGEN) --generate-docbook=docs $<

# Non-autogenerated SGML files to be included in $(DOC_MAIN_SGML_FILE)
content_files =				\
	version.xml			\
	docs-net.hadess.SensorProxy.xml	\
	$(NULL)

# FIXME
MAINTAINERCLEANFILES =		\
	*~			\
	Makefile.in		\
	iio-sensor-proxy.types	\
	iio-sensor-proxy-*.txt	\
	$(NULL)

if ENABLE_GTK_DOC
include $(top_srcdir)/gtk-doc.make
else
CLEANFILES = $(NULL)
EXTRA_DIST = iio-sensor-proxy-docs.xml
endif

CLEANFILES +=					\
	docs-net.hadess.SensorProxy.xml		\
	docs-net.hadess.SensorProxy.Compass.xml	\
	$(NULL)

# Version information for marking the documentation
EXTRA_DIST += version.xml.in

-include $(top_srcdir)/git.mk
