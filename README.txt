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
