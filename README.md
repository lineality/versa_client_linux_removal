### versa_client_linux_removal
```bash
sudo apt purge versa-sase-client
```
# Remove versa from Ubuntu
## versa_client_linux_removal_documentation





# linux client auto-starts, cannot be stopped, and comes with no install scripts, documentation, instruction, and online there is little documentation:


### installed with a file such as:
```text
versa-sase-client-7.4.8.deb
```
- from output
```terminal
... VersaSASEClient 
```


## inspect, run in cli
```bash
systemctl list-unit-files | grep -i versa
```
- example output
```output
versa-sase.service                                    enabled         enabled
```

## find exact package name
```bash
apt list --installed | grep -i versa
```

```output
versa-sase-client/now 7.4.8-0 amd64 [installed,local]
```


```bash
dpkg -l | grep -i versa
```

```output
versa-sase-client/now 7.4.8-0 amd64 [installed,local]
```
```bash
dpkg -l | grep -i versa
```

```output
ii  libu2f-udev                                   1.1.10-3build3                           all          Universal 2nd Factor (U2F) — transitional package
ii  libuchardet0:amd64                            0.0.8-1build1                            amd64        universal charset detection library - shared library
ii  libuuid1:amd64                                2.39.3-9ubuntu6.3                        amd64        Universally Unique ID library
ii  python3-chardet                               5.2.0+dfsg-1                             all          Universal Character Encoding Detector (Python3)
ii  rsync                                         3.2.7-1ubuntu1.2                         amd64        fast, versatile, remote (and local) file-copying tool
ii  uuid-dev:amd64                                2.39.3-9ubuntu6.3                        amd64        Universally Unique ID library - headers and static libraries
ii  uuid-runtime                                  2.39.3-9ubuntu6.3                        amd64        runtime components for the Universally Unique ID library
ii  versa-sase-client                             7.4.8-0                                  amd64        Versa Secure Access is a resilient and reliable “work-from-home” solution and is the industry’s first to deliver SASE services and private connectivity for employees who are remote or working from home.
```

# Uninstall package: With correct package name, remove it: purge will also remove configuration files.

```Bash
sudo apt purge <package-name>
```

- For example:
```bash
sudo apt purge versa-sase-client
