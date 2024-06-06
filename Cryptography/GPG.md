# GPG

GPG is a encryption toolbox.

## Decrypt a AES256 encrypted message
```bash
gpg --import [public_key]
gpg --output [output_file] --cipher-algo AES256 --decrypt [file_to_decrypt]
```
