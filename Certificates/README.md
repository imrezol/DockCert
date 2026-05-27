# Create "Root Dev CA" certificate and key
```bash
docker run -it -v $(pwd):/exportImport ubuntu:26.04 bash
```
Do not add (or share/publish any other way) the ca.key file (Root CA key) to the repository

# Import CA certificate as trutes CA to client machines
 * MAC 
     * Keychain Access.app
     * File -> Import Items -> Choose ca.pem
     * login -> Certificates -> local.negentropics.com -> Right Click -> Get Info -> Trust -> Secure Socket Layer (SSL): Always Trust
 


# Useful links
* Online Certificate Decoder: https://www.sslshopper.com/certificate-decoder.html
* Online CSR Decoder: https://www.sslshopper.com/csr-decoder.html