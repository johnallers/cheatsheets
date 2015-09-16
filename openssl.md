Extracted from "Bulletproof SSL and TLS" by Ivan Ristic

**Version**

	openssl version
	openssl version -a
**Help**

	openssl help
**Generate RSA key, encrypted with AES-128 (PEM format)**

	openssl genrsa -aes128 -out fd.key 2048
**View key structure**

	openssl rsa -text -in fd.key
**Export public part of RSA key**

	openssl rsa -in fd.key -pubout - out fd-public.key
**Generate DSA parameters, then DSA key**

	openssl dsaparam -genkey 2048 | openssl -out dsa.key -a es128
**Generate ECDSA key**

	openssl ecparam -genkey -name secp256r1 | openssl ec -out ec.key -aes128
**Create cert signing request (CSR)**

	openssl req -new -key fd.key -out fd.csr
**Check CSR**

	openssl req -text -in fd.csr -noout
**Create CSR from existing certificate**

	openssl x509 -x509toreq -in fd.crt -out fd.csr -signkey fd.key
**Create a self-signed certificate**

	openssl req -new -x509 -days 365 -key fd.key -out fd.crt
**Create self-signed certificate with Subject Alternative Names (SAN)**

File: fd.ext

	subjectAltName = DNS:*.myhost.com, DNS:myhost.com

Command

	openssl x509 -req -days 365 \
	-in fd.csr -signkey fd.key -out fd.crt \
	-extfile fd.ext 
**Examine certificate**

	openssl x509 -text -in fd.crt -noout
