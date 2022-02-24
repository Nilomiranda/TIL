If you are trying to run a service in a specific port in your computer and this port is already in use and you want to kill the current process blocking the port usage

Do this first, switching `PORT_NUMBER` for the port you want to use.

```bash
sudo lsof -i :PORT_NUMBER
```

It will return something like this:

```
COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME

node 28634 danilomiranda 26u IPv6 0xbdc7fda94ba81397 0t0 TCP *:ddi-tcp-1 (LISTEN)
```

Get the `PID number` and run the following command in your terminal:

```bash
kill -9 PID_NUMBER
```


**OBS:** This was only tested on Mac OS.