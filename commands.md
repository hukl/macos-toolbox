<a href="https://flattr.com/submit/auto?user_id=hukl&url=https%3A%2F%2Fgithub.com%2Fhukl%2Ffreebsd-toolbox%2Fblob%2Fmaster%2Fcommands.md" target="_blank"><img src="https://api.flattr.com/button/flattr-badge-large.png" alt="Flattr this" title="Flattr this" border="0"></a>

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
```

# Introspection
```
opensnoop -n <processnamme>             # snoop file opens as they occur. Uses DTrace.
```

# Software

```

```

# Services

```

```

# Network

```
ifconfig <iface> inet <ip/mask>         # configure IP address on interface
ifconfig <iface> inet <ip/mask> alias   # configure IP address alias on interface
ifconfig <iface> del <ip>               # remove IP address from interface
route add -net default <gw_ip>          # add default route
route add -net <ip/mask> <gw_ip>        # add a custom route for given network
/etc/rc.d/netif restart && \            # restart networking and routing after changing the configuration
/etc/rc.d/routing restart                 without rebooting. Execute in tmux or screen session
netstat -rn                             # display routing table
netstat -an                             # display all connections
netstat -m                              # display buffer usage
netstat -Lan                            # display status of listen queues
netstat -s                              # display extensive statistics per protocol (use -p tcp to only show tcp)
sockstat -l                             # display listening sockets, process names and pids
sysctl kern.ipc.numopensockets          # display number of open sockets
vmstat -z | egrep "ITEM|tcpcb"          # number of hash table buckets to handle incoming tcp connections
                                          increase net.inet.tcp.tcbhashsize if hitting the limit
sysctl net.inet.tcp.hostcache.list      # display current content of hostcache with its parameters per IP
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
