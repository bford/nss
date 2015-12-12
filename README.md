This repository is a temporary fork of the Mozilla NSS and NSPR libraries
for experimental implementation and evaluation of TLS 1.3 features.

There are currently three relevant branches (see commit logs for details):

*	[baseline](https://github.com/bford/nss/tree/baseline):
	a recent development snapshot of the NSS and NSPR trees
	supporting only TLS 1.2.

*	[master](https://github.com/bford/nss/tree/master):
	the same snapshot implementing the main record-layer changes
	already specified in the TLS 1.3 draft:
	namely the encrypted content-type trailer and record padding.

*	[headerless](https://github.com/bford/nss/tree/headerless):
	a further modification of the baseline branch adding support
	for (optional) headerless operation, as proposed on the TLS list.

See pull requests
[baselines...master](https://github.com/bford/nss/pull/1/files)
and
[master...headerless](https://github.com/bford/nss/pull/2/files)
for a convenient diff-highlighted view of the relevant deltas.

To build and run relevant tests on any of these branches:

	$ cd nss
	$ make nss_build_all
	$ cd tests/ssl
	$ ./ssl.sh

Note that I've done some minor hacking to the test scripts
(see commit logs) to eliminate most of the tests except those
for the AES-GCM (AEAD) ciphersuites.

