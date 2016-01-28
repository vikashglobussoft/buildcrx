# Introduction #
BuildCRX is a standalone utility for Windows/Linux to RSA sign and pack a zip-file containing chrome extension data into a CRX file.

## About BuildCRX ##
Chrome extensions are contained in a .CRX package, which consists of the following elements -

  * FILE\_MAGIC (Cr24)
  * File Version
  * Public Key Length
  * Signature Length
  * Public Key
  * Signature
  * ZIP DATA containing chrome extension file layout

The chrome and chromium binaries can create this type of package for you, however if you are using a build-system you probably don't want to install chrome or chromium. As an alternative there are several utilities that do the same thing (without using chrome) that employ a combination of a scripting or shell technology to perform the work and OpenSSL to do the signing.

Unfortunately those tools require an interpreter or shell to run and also require crypto libraries to perform the signing - which could pose an issue if you are attempting to build your CRX within windows or in an automated build environment - enter BuildCRX!

BuildCRX is a windows/linux utility written in C, which has no external dependencies; it does not require chrome/ium or the OpenSSL binaries to be installed on the sytem. BuildCRX statically includes libcrypto from the OpenSSL project, so it should run without installing any other libraries.

I have created a list of alternative utilities for building .CRX packages here:
> http://www.curetheitch.com/projects/buildcrx/other-building-utilities/ (Python, Ruby, BASH, etc.)