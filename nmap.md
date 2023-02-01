# Nmap

TCP scan of the 1,000 most common ports
`nmap 10.129.42.253`


`nmap -sV -sC -p- 10.129.42.253`

`-sC` Nmap scripts should be used to try and obtain more detailed information.

The script scan -sC flag causes Nmap to report the server headers http-server-header page and the page title http-title for any web page hosted on the webserver.

`-sV` perform a version scan.

`-p-` scan all 65,535 TCP ports.

## Run specific Nmap script

`nmap --script <script name> -p<port> <host>`
