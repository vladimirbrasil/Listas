domain_name
===========

Synopsis
--------

Domain Name manipulation library for Ruby

Description
-----------

* Parses a domain name ready for extracting the registered domain and
  TLD.

        require "domain_name"

        host = DomainName("a.b.example.co.uk")
        host.domain         #=> "example.co.uk"
        host.tld            #=> "uk"
        host.cookie_domain?("example.co.uk")    #=> true
        host.cookie_domain?("co.uk")            #=> false

        host = DomainName("[::1]")  # IP addresses like "192.168.1.1" and "::1" are also acceptable
        host.ipaddr?        #=> true
        host.cookie_domain?("0:0:0:0:0:0:0:1")  #=> true


Caveats
-------

* It does not currently perform the strict domain label validation
  defined in RFC 5891 and 5892.  It is being worked on on the
  `unicode` branch.

Installation
------------

	gem install domain_name

References
----------

* [RFC 3492](http://tools.ietf.org/html/rfc3492) (Obsolete; just for test cases)

* [RFC 5890](http://tools.ietf.org/html/rfc5890)

* [RFC 5891](http://tools.ietf.org/html/rfc5891)

* [RFC 5892](http://tools.ietf.org/html/rfc5892)

* [RFC 5893](http://tools.ietf.org/html/rfc5892)

* [Public Suffix List](http://publicsuffix.org/list/)

* [Effective TLD Names List](http://mxr.mozilla.org/mozilla-central/source/netwerk/dns/effective_tld_names.dat?raw=1)

License
-------

Copyright (c) 2011, 2012 Akinori MUSHA

Licensed under the 2-clause BSD license.

Some portion of this library is copyrighted by third parties and
licensed under MPL 1.1/GPL 2.0/LGPL 2.1 or 3-clause BSD license,
See `LICENSE.txt` for details.
