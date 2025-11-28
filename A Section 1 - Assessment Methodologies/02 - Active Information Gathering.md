--- 
		  		![[1647976170241.png]]
## DNS
The Domain Name System (DNS) is a protocol that converts domain names into IP addresses, similar to a telephone directory. Public DNS servers, like Cloudflare (1.1.1.1) and Google (8.8.8.8), maintain records of all domains on the internet.

![[Pasted image 20241123013248.png]]

## _`/etc/hosts`_ file
 _/etc/hosts_ is a file used by the operating system to translate hostnames to IP-addresses. It is also called the ‘hosts’ file. By adding lines to this file, we can map arbitrary hostnames to arbitrary IP-addresses, which then we can use for testing websites locally.
 
``` txt
127.0.0.1    baeldung.com
127.0.0.1:8080    baeldung.com
```

## `dig` command
 The dig (domain information groper) command is **a flexible tool for interrogating DNS name servers**. It performs DNS lookups and displays the answers that are returned from the queried name server(s).
 ```
 dig axfr zonetransfer.me
```

## [dnsenum](https://github.com/fwaeytens/dnsenum) Tool
multithreaded perl script to enumerate DNS information of a domain and to discover non-contiguous ip blocks.

``` bash
┌──(skullhat㉿skullhat)-[~]
└─$ dnsenum zonetransfer.me
dnsenum VERSION:1.2.6

-----   zonetransfer.me   -----
```

## [Fierce](https://github.com/mschwager/fierce) tool 

Fierce is a free, open-source tool that helps locate scattered IP addresses and hostnames for specific domains or subdomains.

``` bash
$ fierce --domain google.com --subdomains accounts admin ads 
```

## [Netdiscover](https://github.com/netdiscover-scanner/netdiscover)

Netdiscover is a network address discovering tool, developed mainly for those wireless networks without dhcp server, it also works on hub/switched networks. Its based on arp packets, it will send arp requests and sniff for replies.

```bash 
sudo netdiscover -i eth0 -r 192.168.2.0./24
```


## Nmap

 short for Network Mapper, is an open-source tool that is used to scan IP addresses and ports of a machine or on a network.
 
==Nmap can be used for the following purposes 

-   creating a complete network Map
-   detecting open ports on local and remote systems
-   getting os system and software details
-   finding vulnerabilities on local and remote hosts
-   detecting installed applications on a host

``` bash
sudo nmap -sn 192.168.0.1 
# -sn: Ping Scan - disable port scan
```

``` txt 
#File name: ips.txt
10.20.30.51
10.20.30.47
10.20.30.1
10.20.30.3
10.20.30.2
```


``` bash
sudo nmap -iL ips.txt -O -sC -sV -F  -oN
sudo nmap -sn 182.1.0.205 -p 165-255 -v  -oX 
sudo nmap 125.25.32.2 -sS 
sudo nmap 125.25.32.2 -sU #UDP Port scan
sudo nmap 125.25.32.2  -A # Enable OS detection, version detection, script scanning, and traceroute

```


