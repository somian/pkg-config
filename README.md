### OpenBSD pkg-config implemented in Perl

The software in this repository started as a simple fork-clone of [the code repository at
](https://github.com/jasperla "Github jasperla") apparently a non-canonical GitHub space.
The code appears to be brought from OpenBSD cvs management directly into that repo with
no changes. The latest commit there was
[@dde2548](https://github.com/jasperla/pkg-config/commit/dde2548e24b569836ffc4dfaca70e28f1d232c63).

#### Usage
```text
Usage:/usr/local/bin/bsd-pkg-config [options]
    --help - this message
    --usage - this message
    --debug	- turn on debugging output
    --list-all - show all packages that D:/UserSW/root/bin/../usr/local/bin/bsd-pkgconfig can find
    --version - print version of pkgconfig
    --errors-to-stdout - direct error messages to stdout rather than stderr
    --print-errors - print error messages in case of error
    --print-provides - print all the modules the given package provides
    --print-requires - print all the modules the given package requires
    --print-requires-private - print all the private modules the given package requires
    --silence-errors - don't print error messages in case of error
    --atleast-pkgconfig-version [version] - require a certain version of pkgconfig
    --cflags package [versionspec] [package [versionspec]]
    --cflags-only-I - only output -Iincludepath flags
    --cflags-only-other - only output flags that are not -I
    --define-variable=NAME=VALUE - define variables
    --libs package [versionspec] [package [versionspec]]
    --libs-only-l - only output -llib flags
    --libs-only-L - only output -Llibpath flags
    --libs-only-other - only output flags that are not -l or -L
    --exists package [versionspec] [package [versionspec]]
    --uninstalled - allow for uninstalled versions to be used
    --static - adjust output for static linking
    --atleast-version [version] - require a certain version of a package
    --modversion [package] - query the version of a package
    --variable var package - return the definition of <var> in <package>
```

#### Installation

The runtime library for this implementation of _pkgconfig_ in Perl, is **OpenBSD/PkgConfig.pm**. 

Any installer utility's task is to place a executable script (_pkg-config_) in the right place
and to put *OpenBSD/PkgConfig.pm* in the right place. A simple Makefile was provided upstream.
We've added a GNUmakefile that is able to query the Perl in PATH and install file to the more
often predictably correct places (but likely not always). This is very simple GNU make code.

No attempt is made to adjust the hashbang first line of the script file.

#### Licensing

A comment block in the head seems to state the licensing terms for this software. This is
the precise wording:

> Permission to use, copy, modify, and distribute this software for any
> purpose with or without fee is hereby granted, provided that the above
> copyright notice and this permission notice appear in all copies.

> THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
> WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
> MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
> ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
> WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
> ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
> OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.

#### Copyright

The _copyright notice_ refered to in the __Licensing__ section currently comprises
this:

    Copyright (c) 2006 Chris Kuethe <--------->
    Copyright (c) 2011 Jasper Lievisse Adriaanse <--------->
    Copyright (c) 2013 Sören Andersen <somian OH-EIGHT @ gmail.com>
 
Email addresses of previous authors elided in this README in order to cut the exposure
their addresses must suffer to the workings of spam-bots.

### See Also

 * The GPL-2 licensed __pkgconfig__
[published by FreeDesktop.org](http://www.freedesktop.org/wiki/Software/pkg-config)

 * The [Guide to pkg-config](http://people.freedesktop.org/~dbn/pkg-config-guide.html "published by Dan Nicholson")

Last modified: 2013-03-26T19:30:12 UTC-04:00
