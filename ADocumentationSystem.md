# A Documentation System

Currently `sip2rst.py` uses undocumented and unstable calls into the `sipbuild`
module.  It has always been the intention for SIP to implement some sort of
general purpose documentation system.  With recent changes to SIP (specifically
the provision of the plugin API) it has become clearer how this might work.

In the most general terms the documentation system should be implemented as
part of PyQt-builder making use of the public SIP APIs (extended as required).
More specifically the `sip2rst.py` script should be replaced by a call to
`sip-build` that is passed appropriate PyQt-builder options to configure its
plugin(s) to generate reST rather than C++.


## Requirements

The documentation should be able to be built from a normal PyQt installation,
ie. the `.sip` files should be obtained from the installed `bindings`
directory.  This will require SIP to expose an `Installation` class with which
the project meta-data (ie. the `bindings` directory) can be introspected in a
way that allows future layour changes.


## Issues

Currently the `bindings` directory only contains data for the modules that are
actually installed (eg. there is no `QAxContainer` data in non-Windows
installations).  PyQt-builder can be changed so that it installs the data for
all known bindings whether or not they are actually installed.  Care should be
taken to deal with modules that can be defined in more than one set of `.sip`
files (eg. `QtPdf`).


## Misc

If possible the implemenation should change to support case-insensitive
filesystems.
