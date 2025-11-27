# SSH

SSH is a protocol allowing secured communication between two devices.

## Connect using a private key (which needs 600 permissions):
```bash
ssh -i [key] [user]@[ip]
```

## Port forwarding via SSH tunnel
```bash
ssh -L [remote_port]:localhost:[local_port] [user]@[ip]
```

Then the remote port should be available on `localhost`
