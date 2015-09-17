Extracted from "Bulletproof SSL and TLS" by Ivan Ristic

# Formats

**Binary (DER) certificate**

Contains an X.509 certificate in its raw form, using DER ASN.1 encoding.

**ASCII (PEM) certificate**

Contains a base64-encoded DER certificate.

**Binary (DER) key**

Contains a private key in its raw form, using DER ASN.1 encoding.

Alternative formats:

* OpenSSL uses its own format.
* PKCS#8 (RFC 5208) - not widely used.

**ASCII (PEM) key**

Base64-encoded DER key. Sometimes contains additional metadata (algorithm used for password protection).

**PKCS#7 certificate**
A complex format designed for the transport of signed or encrypted data (RD2315).

* Can include entire certificate chain.
* Usually has .p7b and .p7c extensions.
* Supported by Java keytool utility.

**PKCS#12 (PFX) key and certificate**

A complex format that can store and protect a server key along with entire certificate chain.

* Usually has .p12 and .pfx extensions.
* Common with Microsoft products.
* Also used with client certificates.