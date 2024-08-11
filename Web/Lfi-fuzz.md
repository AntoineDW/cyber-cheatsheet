# Lfi-fuzz

A python script to enumerate and attempt to get code execution from LFI vulnerabilities.

## Attempt to get a LFI on an API endpoint
```bash
cd /opt/lfi-fuzz
python3 lfi-fuzz.py -u [url]?param=LFI
```

