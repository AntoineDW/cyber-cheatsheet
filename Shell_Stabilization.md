# Shell stabilization

## Using Python
```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
```

`CTRL + Z`

```bash
stty raw -echo; fg
```

## Using rlwrap
```bash
rlwrap nc -lvnp [port]
```
