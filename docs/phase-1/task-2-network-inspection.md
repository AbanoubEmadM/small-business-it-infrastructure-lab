# Task 2: Inspect Networking

## 1. Objective

Inspect the RHEL server's current network configuration to identify its network interface, IP address, default gateway, DNS servers, and NetworkManager connection profile.

This inspection establishes the network baseline before introducing additional infrastructure services.

## 2. Network Configuration

| Property | Observed Value |
|---|---|
| **VirtualBox Network Mode** | Bridged Adapter |
| **Network Interface** | enp0s3 |
| **IP Address** | 192.168.x.x |
| **Default Gateway** | 192.168.x.x |
| **DNS Servers** | 8.8.8.8, 8.8.4.4 |
| **NetworkManager Profile** | enp0s3 |
| **Connection Type** | Ethernet |
| **NetworkManager Device** | enp0s3 |

## 3. Tools Used

| Command | Purpose |
|---|---|
| `ip link show` | Inspect network interfaces and their link state |
| `ip addr show` | Inspect interface IP addresses |
| `ip route` | Inspect routing entries and the default route |
| `nmcli dev show` | Inspect active device configuration, including IP and DNS information |
| `nmcli connection show` | List NetworkManager connection profiles and their associated settings |

## 4. Findings

- The primary network interface is recorded as enp0s3.
- The server's recorded IPv4 address is 192.168.x.x.
- The recorded default gateway is 192.168.x.x.
- Two DNS servers are configured: 8.8.8.8 and 8.8.4.4.
- The NetworkManager connection profile is named enp0s3 and has the Ethernet connection type.
- The virtual machine uses Bridged Adapter networking.

## 5. Technical Notes

NetworkManager connection profiles store connection settings, while device inspection commands show the current state of network interfaces. Comparing both helps distinguish the configured profile from the network configuration currently in effect.

Because the virtual machine uses bridged networking, its IP address must be appropriate for the physical LAN. Any static address should be checked for conflicts with other devices and the network's DHCP allocation range.

## 6. Conclusion

The initial network inspection identified the server's primary interface, recorded IP configuration, default gateway, DNS servers, and NetworkManager profile.

This information will support future connectivity testing and the integration of the RHEL server into the small-business infrastructure lab.

## 7. Evidence
