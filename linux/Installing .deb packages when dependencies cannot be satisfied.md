If you attempt to install a `.deb` package in Ubuntu and you face this error:

```
Error: Cannot satisfy dependencies
```

Try using `dpkg` to install instead.

```bash
sudo dpkg -i application_to_install.dev
```
