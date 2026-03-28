## Was the vpn successful, but not anymore?
Were you able to connect to your network and ping/ssh local addresses - but not anymore?
You might have followed some other temp steps online for WireGuard and just done them temporarily.

Let's try to stabilise our PiVPN using the IP table:
Locate the config file: ` sudo iptables -t nat -L -n -v | grep MASQUERADE `

Ensure we have this:

`PostUp = iptables -t nat -A POSTROUTING -s 10.78.116.0/24 -o eth0 -j MASQUERADE`

`PostDown = iptables -t nat -D POSTROUTING -s 10.78.116.0/24 -o eth0 -j MASQUERADE`

**Do a restart:**
`sudo systemctl restart wg-quick@wg0`

*_Still not working_?*
On your client(s) add: `PersistentKeepalive = 25`
