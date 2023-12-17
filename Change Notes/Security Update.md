# Change Management Notes - Security Update CHG-13447

## 2023-11-07

### Overview
This change will establish a route based VPN tunnel with the corporate website. A route-based VPN tunnel is a configuration where an encrypted connection (tunnel) created between two endpoints (device and VPN service) is referenced by a network route that determines which traffic is sent through the tunnel based on a destination IP address. 

### Features 
* New VPN tunnel interface
* Establish corporate policies
* Configuration of IPSec profiles

### Benefits
* Allows for configuration of many policies
* Supports dynamic router traffic information
* Encrypts application data
* Quickly authenticates data

### Impact
The impact is expected to be minimal as the configuration is isolated to a specific subnet and tunnel.

### Known Bugs
Internal network proxies, which are used for connecting to the Internet in some networking configurations, are not supported by the route-based VPN tunnel.
