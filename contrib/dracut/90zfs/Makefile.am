pkgdracutdir = $(dracutdir)/modules.d/90zfs
pkgdracut_SCRIPTS = \
	export-zfs.sh \
	module-setup.sh \
	mount-zfs.sh \
	parse-zfs.sh \
	zfs-generator.sh \
	zfs-needshutdown.sh \
	zfs-lib.sh

EXTRA_DIST = \
	$(top_srcdir)/contrib/dracut/90zfs/export-zfs.sh.in \
	$(top_srcdir)/contrib/dracut/90zfs/module-setup.sh.in \
	$(top_srcdir)/contrib/dracut/90zfs/mount-zfs.sh.in \
	$(top_srcdir)/contrib/dracut/90zfs/parse-zfs.sh.in \
	$(top_srcdir)/contrib/dracut/90zfs/zfs-generator.sh.in \
	$(top_srcdir)/contrib/dracut/90zfs/zfs-needshutdown.sh.in \
	$(top_srcdir)/contrib/dracut/90zfs/zfs-lib.sh.in

$(pkgdracut_SCRIPTS):%:%.in
	-$(SED) -e 's,@bindir\@,$(bindir),g' \
		-e 's,@sbindir\@,$(sbindir),g' \
		-e 's,@udevdir\@,$(udevdir),g' \
		-e 's,@udevruledir\@,$(udevruledir),g' \
		-e 's,@sysconfdir\@,$(sysconfdir),g' \
		-e 's,@systemdunitdir\@,$(systemdunitdir),g' \
		$< >'$@'

distclean-local::
	-$(RM) $(pkgdracut_SCRIPTS)
