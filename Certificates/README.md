# Create "Root Dev CA" and nginx default certificate+key 
```shell
docker run -it --rm  -v $(pwd):/exportImport ubuntu:26.04 bash -c "/exportImport/genCerts.sh"
```
Do not add (or share/publish any other way) the ca.key file (Root CA key) to the repository


openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout local2.key -out local2.crt

# Useful links
* Online Certificate Decoder: https://www.sslshopper.com/certificate-decoder.html
* Online CSR Decoder: https://www.sslshopper.com/csr-decoder.html
* OpenSSL Essentials: SSL Certificates, Private Keys and CSRs: https://www.digitalocean.com/community/tutorials/openssl-essentials-working-with-ssl-certificates-private-keys-and-csrs
* 