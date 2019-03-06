# Users
```

```



# System Configuration

```
ifconfig                                # show and configure network interface parameters
```


# System Statistics

```
top                                     # display and update information about the top cpu processes
ps auxwww | grep <processname>          # display process status
CTRL-t                                  # on running commands will output useful info
vm_stat 5                               # show Mach virtual memory statistics every 5 seconds
```

# Introspection
```
opensnoop -n <processnamme>             # snoop file opens as they occur. Uses DTrace.
sudo fs_usage | grep …                  # See File access and filter for specific filenames
lsof -i :3000                           # Find out PID of a Proccess currently holding a given Port                 
```

# Software

```

```

# Services

```

```

# Network

```
nettop                                  # extensive traffic info for each running process
ifconfig <iface> inet <ip/mask>         # configure IP address on interface
ifconfig <iface> inet <ip/mask> alias   # configure IP address alias on interface
ifconfig <iface> del <ip>               # remove IP address from interface
route add -net default <gw_ip>          # add default route
route add -net <ip/mask> <gw_ip>        # add a custom route for given network
netstat -rn                             # display routing table
netstat -an                             # display all connections
netstat -m                              # display buffer usage
netstat -Lan                            # display status of listen queues
netstat -s                              # display extensive statistics per protocol (use -p tcp to only show tcp)
```

# Firewall

```

```

# IPsec

```
ipsec start                             # start VPN and establish (auto=start) VPN connections
setkey -D                               # show extensive Kernel information about current connections
setkey -DP                              # show more condensed connection information
ipsec statusall [conn]                  # show returns detailed status information either on connection or all 
                                          connections if no name is provided
ipsec leases                            # show current leases from virtual IP address pool
ipsec rereadsecrets                     # flushes and rereads all secrets defined in ipsec.secrets
ipsec rereadall                         # flushes and rereads all secrets defined in ipsec.secrets as well as all 
                                          certificates and and certificate revocation lists
ipsec update                            # sends a HUP signal to the daemon that determines any changes in ipsec.conf 
                                          and updates the configuration on the running IKE daemon charon
ipsec reload                            # sends a USR1 signal to the daemon that reloads the whole configuration 
                                          on the running IKE daemon charon based on the actual ipsec.conf
ipsec restart                           # terminates all ipsec connections, sends a TERM signal to the daemon and     
                                          restarts it afterwards
ipsec stroke up [conn]                  # initiate connection [conn]
ipsec stroke down [conn]                # terminate connection [conn]
```

# SSL

```
                                        # Check expiration dates of remotes host certificates
echo | openssl s_client -servername NAME -connect HOST:PORT 2>/dev/null | openssl x509 -noout -dates
