# Notes: EoIP (Ethernet over IP)
EoIP is a Mikrotik/RouterOS-proprietary tunneling protocol, that as
the name suggests, tunnels Ethernet over IP.

## Advantages
* If you need remote layer two access, EoIP gives you a lot more
flexibility.
* IP addressing of remote clients can easily be handled by your
existing DHCP server.
* Works over SSTP, OpenVPN and IPSec.
* VLANs work as expected for a L2 connection.

## Caveats
### MTU issues
By default, EoIP interfaces have an MTU of 1458. *You'll probably
want to manually set this to 1500*. If you don't, adding the EoIP
interface to a bridge will pull down the MTU of the bridge and all
its interfaces to match. This can cause a lot of weird behaviour.