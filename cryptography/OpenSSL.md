# OpenSSL

OpenSSL is an encryption toolbox.

## Decrypt a AES256CBC encrypted file
```bash
openssl aes-256-cbc -d -in [encrypted_file] -out [output_file]
```

## Decrypt a RSA encrypted file using a private key
```bash
openssl pkeyutl -decrypt -in [encrypted_file] -inkey [private_key] -out [output_file]
```

## Show the parameters of a RSA private key
```bash
openssl rsa -in [private_key] -text -noout
```

## Show the parameters of a Diffie-Hellman key
```bash
openssl dhparam -in [diffie_hellman_key] -text -noout
```

## Generate a Diffie-Hellman key
```bash
openssl dhparam -out [output_file] 2048
```

## Generate a 2048-bit private key
```bash
openssl genrsa -out [output_file] 2048
```

## Generate a hashed password for /etc/passwd
```bash
openssl passwd -1 [password]
```
