#-# Added locally. First created: 2013-03-24T07:22:48 UTC
#-# Last modified: 2013-03-24T07:23:00Z

SWPKG = bsd-pkgconfig
MODFN = PkgConfig.pm
MODNS = OpenBSD

BINDIR :=
LIBDIR :=

INSTALL ?= /usr/bin/install

realinstall : probeinstall
	@ECHO We have LIBDIR as $(LIBDIR) and BINDIR as $(BINDIR)
	${INSTALL} -vm 0664 -D OpenBSD/PkgConfig.pm ${DESTDIR}${LIBDIR}/PkgConfig.pm
	${INSTALL} -vm 0755 pkg-config ${DESTDIR}${BINDIR}/$(SWPKG)
	@ECHO Done.

.PHONY : probeinstall realinstall

probeinstall :
	@/bin/printf 1>&2 'Going to try running perl on ourself: %s\n' $(firstword ${MAKEFILE_LIST})
	@${if $(LIBDIR),, /bin/true \
   $(eval LIBDIR = $(shell /bin/perl -x $(firstword ${MAKEFILE_LIST}) ${MODNS})) \
   $(eval BINDIR = $(shell /bin/perl -x $(firstword ${MAKEFILE_LIST})))}

ifeq (1,2)

#!/usr/bin/env perl
use strict;
use warnings;
use Config;
my $sdspec = shift @ARGV;
my $destin;
  if ($sdspec) {
      $destin = File::Spec::Unix->catdir($Config{installsitelib}, $sdspec);
      printf STDERR "Likely module install directory is %s\n" => $destin;
  } else {
     $destin = $Config{installsitebin};
      printf STDERR "Likely script install directory is %s\n" => $destin;
  }
printf STDOUT $destin;
__END__
endif
