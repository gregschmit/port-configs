# SSL (Secure Sockets Layer) Directory

This directory is meant to contain the private keys, host certificates, intermediate certificates, and certificate signing requests that you may need on the server.

## Helpful `OpenSSL` Commands

 - How to generate a private key:

`openssl genpkey -algorithm rsa -pkeyopt rsa_keygen_bits:4096 -out key.pem`

 - How to generate a certificate signing request from a private key:

`openssl req -out csr.pem -key key.pem -new`

 - How to sign a certificate (in this case, with your own key - this is known as a self-signed certificate):

`openssl x509 -req -days 365 -in csr.pem -signkey key.pem -out crt.pem`
