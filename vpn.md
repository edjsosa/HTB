# Connect to VPN
`sudo openvpn user.ovpn`

The `user.ovpn` file is the VPN key that we download from either the Academy module section or the main HTB platform Access page.

If we type `ifconfig` in another terminal window, we will see a tun adapter if we successfully connected to the VPN.

Show IP address
`ifconfig/ip a`

Show networks accessible via the VPN
`netstat -rn`