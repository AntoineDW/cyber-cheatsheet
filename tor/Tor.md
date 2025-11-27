# Tor

## Start the Tor service
```bash
sudo systemctl enable tor
sudo service tor start
```

## Change the Proxychains configuration file
Comment the following line: `strict_chain`
Uncomment the following line: `dynamic_chain`

Add the following two lines at the end of the file:
```
socks4   127.0.0.1   9050
socks5   127.0.0.1   9050
```

## Run a command with the Tor proxy enabled
```bash
proxychains4 [command]
```
