Easy Certificate Creation (EZCert)
==================================


SSH Public Key To Certificate
-----------------------------

The CACreateCert certificate utility was developed in order to
facilitate using X509 client certificates for authentication with
a web server over the https protocol when all the user has uploaded
to the server for identification is an OpenSSH RSA public key (e.g.
id_rsa.pub).

(In other words, the user pastes an OpenSSH RSA public key into a
form on the web server and the web server responds with a client
certificate that the user can then download and use together with
the corresponding private key to authenticate to that web server.)


Any Old Certificate
-------------------

However, the CACreateCert utility has grown a number of additional
options making it useful for creation of several other kinds of
X509 certificates.

It may be helpful to first view the Example.html page to see how a
full set of certificates and keys for a complete certificate chain
may be generated (including individual user client authentication
certificates).  If more detail is needed on the veritable plethora
of options available when running the CACreateCert utility, look
at the output of the CACreateCert -h command.


Secure E-mail
-------------

Secure email in the form of S/MIME has existed since before the start
of the 21st century.  To use S/MIME to transmit encrypted email(s), both
the sender and the receiver must each have an "email" certificate that
contains their "public" key and email address and they must possess the
non-shared private key that goes with the "public" key.  However, since
these are X.509 certificates we are talking about, and X.509 certificates
are always validated in a chain where there must always be at least two
certificates in any valid chain (a "root" certificate and a "leaf"
certificate), the "email" certificate (which is the "leaf" certificate)
will need a "root" certificate that signs it.

It is possible to create a "root" self-signed "email" certificate.
This is not really recommended because it does not conform to the
standard and therefore email encrypted and/or signed with such a
certificate might be rejected by the receiver.

However, using the `--acme` option, it's trivial to use the CACreateCert
utility to create a root certificate and then use that to sign your
"email" leaf certificate generated with the `--email` option.

The `CACreateCert --help` output contains a "CREATING AN EMAIL CERTIFICATE"
example in the "EXAMPLES" section that demonstrates how to create your very
own email signing certificate.


Convert Public Key Formats Too
------------------------------

A ConvertPubKey utility is also provided that can convert between
OpenSSH and X.509 public key formats without using OpenSSH or OpenSSL.


License
-------

This software is licensed under the GNU Affero General Public License
as published by the Free Software Foundation, either version 3 of
the License, or (at your option) any later version.  See the included
file LICENSE.txt or the web site <http://www.gnu.org/licenses/>.
