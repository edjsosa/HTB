# SMB

SMB provides many vectors for vertical and lateral movement.

Sensitive data, including credentials, can be in network file shares.

Some SMB versions may be vulnerable to RCE exploits such as [EternalBlue](https://www.avast.com/c-eternalblue).

## Nmap script for enumerating SMB

`nmap --script smb-os-discovery.nse -p445 10.10.10.40`

`nmap -A -p445 10.129.42.253`

`-A` enables OS detection, version detection, script scanning, and traceroute

## smbclient

`smbclient -N -L \\\\10.129.42.253`

`smbclient` can enumerate and interact with SMB shares.

`-N` suppresses the password prompt.

`-L` specifies that we want to retrieve a list of available shares on the remote host.

### Non-credential

`smbclient \\\\10.129.42.253\\users`

### Credentialed

`smbclient -U bob \\\\10.129.42.253\\users`

