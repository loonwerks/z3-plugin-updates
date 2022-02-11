# Z3-Plugin

Packages the Microsoft Z3 solver binaries into an Eclipse Plugin for convenient
use in Eclipse-based analysis tools.

## Packaging

Presently all supported OS/architecture binaries are packaged into one plug in.
In future, we hope to have the time to separate these into individual bundles,
requiring installation only of the the binary to support the local machine
OS/Architecture.

The presently supported versions are:

- Microsoft Windows WIN32, 64-bit
- Linux GTK, 64-bit
- Apple Macintosh OSX, 64-bit

## Updating

All of the steps necessary to fetch updated versions of Z3 Prover,
package into Eclipse plugins, and deploy these as an Eclipse P2 update
site are codified in the Python script `z3_release_fetcher.py` in the
root directory of this repository.

Further, a Travis CI configuration `.travis.yml` is used to
periodically query for new versions of Z3 Prover and package these.
Note that any Travis CI build jobs should be set up as periodic rather
than responding to checkins.  This is because the script itself checks
in newly packaged plugins.  Responding to checkins would then fork
bomb Travis CI until no new versions of Z3 are found (which should be
pretty quickly, so this isn't quite as bad as it sounds).

## Installing in Eclipse

This repository is laid out such that access via the GitHub raw
interface maps to a valid Eclipse P2 repository.  Use the following
URL in the Eclipse "Install New Software..." dialog:

[https://raw.githubusercontent.com/loonwerks/z3-plugin-updates/master](https://raw.githubusercontent.com/loonwerks/z3-plugin-updates/master)
