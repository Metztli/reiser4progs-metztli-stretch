SUBDIRS         = libaux plugin libreiser4 librepair libmisc progs include doc demos

EXTRA_DIST	= AUTHORS COPYING TODO NEWS BUGS README CREDITS THANKS \
		  reiser4progs.spec.in reiser4progs.spec libreiser4.m4 \
		  one_touch_install INSTALL_README CUSTOM_INSTALL_README \
		  depcomp run-ldconfig

aclocaldir 	= $(datadir)/aclocal
aclocal_DATA	= libreiser4.m4

define all_sources
	( find ./ -name '*.[ch]' | grep -v SCCS | grep -v "Attic" | grep -v "reiser4progs" )
endef

TAGS:
	$(all_sources) | etags -

tags:
	$(all_sources) | xargs -- ctags -w -o TAGS

install-exec-hook:
	./run-ldconfig $(libdir)

uninstall-hook:
	./run-ldconfig $(libdir)
