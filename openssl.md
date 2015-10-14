**Get Certificate for a specific site**

	openssl s_client -connect {HOSTNAME}:{PORT} -showcerts

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
**Convert between PEM and DER format**

	openssl x509 -inform PEM -in fd.pem -outform DER -out fd.der

	openssl x509 -inform DER -in fd.der -outform PEM -out fd.pem
To convert keys replace `x509` with `rsa` or `dsa`, as appropriate.

**Convert key, certificate and intermediate certificates to single PKCS#12 file**

	openssl pkcs12 -export \
		-name "My Certificate" \
		-out fd.p12 \
		-inkey fd.key \
		-in fd.crt \
		-certfile fd-chain.crt
Reverse, but only to a single file:

	openssl pkcs12 -in fd.p12 -out fd.pem -nodes
**Convert betwen PEM and PKCS#7**

	openssl cr12pkcs7 -nocrl -out fd.p7b -certfile fd.crt -certfile fd-chain.crt
	
	openssl pkcs7 -in fd.p7b -print_certs -out fd.pem
**List supported ciphers**

	openssl ciphers -v 'ALL:COMPLEMENTOFALL'
	openssl ciphers -v 'RC4'
	openssl ciphers -v 'RC4+SHA'
**Performance**

	openssl speed aes-128-cbc
Activate hardware acceleration

	openssl speed -evp aes-128-cbc
