# SQLMap

An automatic SQL injection and database takeover tool.

## Try to find SQLi vunerabilities on an HTTP request
First, intercept the HTTP request using the vulnerable parameters using BurpSuite and copy/paste the result in a .txt file.

```bash
sqlmap -r [request_file] --dbms=[dbms] --dump
```
