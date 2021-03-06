## VPP Feature list:
[ACL Based Forwarding](#acl-based-forwarding)  
[ACLs for Security Groups](#acls-for-security-groups)  
[Address Resolution Protocol](#address-resolution-protocol)  
[Adjacency](#adjacency)  
[Bidirectional Forwarding Detection](#bidirectional-forwarding-detection)  
[Bit Indexed Explicit Replication](#bit-indexed-explicit-replication)  
[Bonding](#bonding)  
[Buffer Metadata Change Tracker](#buffer-metadata-change-tracker)  
[Builtin URL support for the static http or https server](#builtin-url-support-for-the-static-http-or-https-server)  
[Data-Plane Objects](#data-plane-objects)  
[Dynamic Host Configuration Protocol](#dynamic-host-configuration-protocol)  
[GPRS Tunneling Protocol](#gprs-tunneling-protocol)  
[Generic Routing Encapsulation](#generic-routing-encapsulation)  
[IP Neighbour Database](#ip-neighbour-database)  
[IP Security](#ip-security)  
[IP in IP tunnelling](#ip-in-ip-tunnelling)  
[IPFIX probe](#ipfix-probe)  
[IPSec crypto engine provided by Intel IPSecMB library](#ipsec-crypto-engine-provided-by-intel-ipsecmb-library)  
[IPSec crypto engine provided by Openssl library](#ipsec-crypto-engine-provided-by-openssl-library)  
[IPSec crypto engine provided by native implementation](#ipsec-crypto-engine-provided-by-native-implementation)  
[IPv6 Neighbor Discovery](#ipv6-neighbor-discovery)  
[Internet Group Management Protocol](#internet-group-management-protocol)  
[L2TPv3](#l2tpv3)  
[Layer 2 Forwarding](#layer-2-forwarding)  
[Layer 3 cross connect](#layer-3-cross-connect)  
[Link Aggregation Control Protocol](#link-aggregation-control-protocol)  
[Link Layer Discovery Protocol](#link-layer-discovery-protocol)  
[Load Balancer](#load-balancer)  
[Locator ID Separation Protocol Control Plane](#locator-id-separation-protocol-control-plane)  
[Locator ID Separation Protocol Generic Protocol Extension](#locator-id-separation-protocol-generic-protocol-extension)  
[Mapping of Address and Port](#mapping-of-address-and-port)  
[Multi-Protocol Label Switching](#multi-protocol-label-switching)  
[NSH](#nsh)  
[Netmap Device](#netmap-device)  
[Network Address Translation](#network-address-translation)  
[Network Delay Simulator](#network-delay-simulator)  
[PPPoE](#pppoe)  
[Pipe Device](#pipe-device)  
[QUIC Protocol](#quic-protocol)  
[Quality of Service](#quality-of-service)  
[SRv6 - Service Chaining Dynamic Proxy](#srv6---service-chaining-dynamic-proxy)  
[SRv6 - Service Chaining Masquerading Proxy](#srv6---service-chaining-masquerading-proxy)  
[SRv6 - Service Chaining Static Proxy](#srv6---service-chaining-static-proxy)  
[SRv6 Mobuile](#srv6-mobuile)  
[Segment Routing for IPv6 (SRv6)](#segment-routing-for-ipv6-(srv6))  
[Segment Routing for MPLS](#segment-routing-for-mpls)  
[Session Layer](#session-layer)  
[Source VRF Select](#source-vrf-select)  
[Static http https server](#static-http-https-server)  
[Tap Device](#tap-device)  
[Time-range-based MAC-address filter](#time-range-based-mac-address-filter)  
[Transmission Control Protocol](#transmission-control-protocol)  
[Transport Layer Security](#transport-layer-security)  
[User Datagram Protocol](#user-datagram-protocol)  
[VNET GSO](#vnet-gso)  
[VPP Comms Library](#vpp-comms-library)  
[Virtio PCI Device](#virtio-pci-device)  
[Virtual eXtensible LAN](#virtual-extensible-lan)  
[VxLAN-GPE](#vxlan-gpe)  
[host-interface Device AF_PACKET](#host-interface-device-af_packet)  
[rdma device driver](#rdma-device-driver)  
[vmxnet3 device driver](#vmxnet3-device-driver)  

## Feature Details:
VPP version: v20.05-rc0-12-g13e6fce7c

### ACL Based Forwarding
Maintainer: Neale Ranns <nranns@cisco.com>  



- Policy Based Routing
- ACLs match traffic to be forwarded
- Each rule in the ACL has an associated 'path' which determines how the traffic will be forwarded. This path is described as a FIB path, so anything possible with basic L3 forwarding is possible with ABF (with the exception of output MPLS labels)
- ACLs are grouped into a policy
- ACL priorities within the policy determine which traffic is preferentially matched
- Policies are attached to interfaces.
- ABF runs as an input feature in the L3 path

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

Source Code: [https://git.fd.io/vpp/tree/src/plugins/abf](https://git.fd.io/vpp/tree/src/plugins/abf) 
### ACLs for Security Groups
Maintainer: Andrew Yourtchenko <ayourtch@gmail.com>  

The ACL plugin allows to implement access control policies
at the levels of IP address ownership (by locking down
the IP-MAC associations by MACIP ACLs), and by using network
and transport level policies in inbound and outbound ACLs.
For non-initial fragments the matching is done on network
layer only. The session state in stateful ACLs is maintained
per-interface (e.g. outbound interface ACL creates the session
while inbound ACL matches it), which simplifies the design
and operation. For TCP handling, the session processing
tracks "established" (seen both SYN segments and seen ACKs for them),
and "transient" (all the other TCP states) sessions.

- Inbound MACIP ACLs
  - filter the source IP:MAC address statically configured bindings

- Stateless inbound and outbound ACLs
  - permit/deny packets based on their L3/L4 info

- Stateful inbound and outbound ACLs
  - create inbound sessions based on outbound traffic and vice versa


Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

Source Code: [https://git.fd.io/vpp/tree/src/plugins/acl](https://git.fd.io/vpp/tree/src/plugins/acl) 
### Address Resolution Protocol
Maintainer: Neale Ranns <nranns@cisco.com>  

An implementation of the Address resolution protocol (ARP) as described in RFC826

- ARP responder

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

Source Code: [https://git.fd.io/vpp/tree/src/vnet/arp](https://git.fd.io/vpp/tree/src/vnet/arp) 
### Adjacency
Maintainer: Neale Ranns <nranns@cisco.com>  

Adjacencies represent the next-hop information required to reach a directly connected neighbour.

- An adjacency represents how to send different traffic types to a peer
- The principles properties of an adjacency are the interface and rewrite. The rewrite will be prepended to the packet as it is forward through the interface.
- The rewrite is provided either by the interface type. It can be constructed either from fixed interface properties (i.e. src,dst IP address on a P2P tunnel) or from a resolution protocol (like ARP on an Ethernet link).
- An Adjacency is said to be complete when the rewrite is present and incomplete when it is not,
- An adjacency that is a leaf in the DPO graph is terminal/normal (i.e on a physical interface). When not terminal it is termed a midchain (i.e. one on a virtual interface, e.g. GRE tunnel). Midchain adjacencies can be stacked/joined onto the the DPO graph that described subsequent forwarding (i.e. how to send the the GRE tunnel's destination address).
- Glean adjacencies describe how to broadcast packets onto a subnet

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [77cfc0171](https://git.fd.io/vpp/commit/?id=77cfc0171) fib: Adjacency creation notifications for dlegates

Source Code: [https://git.fd.io/vpp/tree/src/vnet/adj](https://git.fd.io/vpp/tree/src/vnet/adj) 
### Bidirectional Forwarding Detection
Maintainer: Klement Sekera <ksekera@cisco.com>  

An implementation of Bidirectional Forwarding Detection (BFD).

- BFD protocol implementation

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/bfd](https://git.fd.io/vpp/tree/src/vnet/bfd) 
### Bit Indexed Explicit Replication
Maintainer: Neale Ranns <nranns@cisco.com>  

An implementation of Bit Indexed Explicit Replication (BIER)

- Multicast Using Bit Index Explicit Replication (https://tools.ietf.org/html/rfc8279)
- Encapsulation for Bit Index Explicit Replication (BIER) in MPLS and Non-MPLS Networks (https://tools.ietf.org/html/rfc8296)

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/bier](https://git.fd.io/vpp/tree/src/vnet/bier) 
### Bonding
Maintainer: Steven Luong <sluong@cisco.com>  

Bonding implementation

- Interface bonding support with the following options - mode active-backup - mode lacp - load-balance l2 | l23 | l34 - numa-only - mode xor - load-balance l2 | l23 | l34 - mode round-robin - mode broadcast

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [aa7257863](https://git.fd.io/vpp/commit/?id=aa7257863) bonding: Add /if/lacp/<bond-sw_if_index>/<slave-sw_if_index>/partner-state
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [e83aa456b](https://git.fd.io/vpp/commit/?id=e83aa456b) bonding: add/del secondary mac address callback
  - [cc3aac056](https://git.fd.io/vpp/commit/?id=cc3aac056) bonding: fix interface deletion
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace
  - [a1876b84e](https://git.fd.io/vpp/commit/?id=a1876b84e) bonding: add weight support for active-backup mode
  - [0f09a828a](https://git.fd.io/vpp/commit/?id=0f09a828a) stats: add /if/<n>/<n>/state for lacp interface state

Source Code: [https://git.fd.io/vpp/tree/src/vnet/bonding](https://git.fd.io/vpp/tree/src/vnet/bonding) 
### Buffer Metadata Change Tracker
Maintainer: Dave Barach <dave@barachs.net>  

The Buffer Metadata Change Tracker (mdata)
uses the before / after graph node main loop performance
callback hooks to snapshoot buffer metadata, then
compare and summarize results per-node.
Answers the question "what buffer metadata does a particular
graph node change?" by direct observation.
Zero performance impact until enabled.

- Buffer Metadata Change Tracker

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [d318a996b](https://git.fd.io/vpp/commit/?id=d318a996b) dhcp: ipv6 prefix delegation improvements
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [d7b306657](https://git.fd.io/vpp/commit/?id=d7b306657) mdata: buffer metadata change tracker plugin

Source Code: [https://git.fd.io/vpp/tree/src/plugins/mdata](https://git.fd.io/vpp/tree/src/plugins/mdata) 
### Builtin URL support for the static http or https server
Maintainer: Dave Barach <dave@barachs.net>  

The (builtinurl) plugin adds a set of URLs to the static http/https server. Current URLs, all of which return data in .json fmt: <root-url>/version.json - vpp version info <root-url>/interface_list.json - list of interfaces <root-url>/interface_stats - single interface via HTTP POST <root-url>/interface_stats - all intfcs via HTTP GET.

- Builtin URLs for the static http/https server

Feature maturity level: development  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [71a5da0c8](https://git.fd.io/vpp/commit/?id=71a5da0c8) http_static: add .json content
  - [43765e2b4](https://git.fd.io/vpp/commit/?id=43765e2b4) builtinurl: initial working attempt

Source Code: [https://git.fd.io/vpp/tree/src/plugins/builtinurl](https://git.fd.io/vpp/tree/src/plugins/builtinurl) 
### Data-Plane Objects
Maintainer: Neale Ranns <nranns@cisco.com>  

Data-Plane Objects (DPO)

- A DPO is a generic term (a.k.a abstract base class) for objects that perform [a set of] actions on packets in the data-plane
- Concrete examples of DPO types are; adjacency, mpls-imposition, replication.
- DPOs are stacked/joined to form a processing graph that packets traverse to describe the full set of actions a packet should experience.
- DPO graphs can be rooted at any point in the VLIB graph - notable examples are L3 FIB lookup, ABF, L3XC.

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Source Code: [https://git.fd.io/vpp/tree/src/vnet/dpo](https://git.fd.io/vpp/tree/src/vnet/dpo) 
### Dynamic Host Configuration Protocol
Maintainer: Dave Barach <dave@barachs.net>, Neale Ranns <nranns@cisco.com>  

An implemenation of the Dynamic Host Configuration Protocol (DHCP) client

- DHCP client (v4/v6)
- DHCPv6 prefix delegation
- DHCP Proxy / Option 82

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [d318a996b](https://git.fd.io/vpp/commit/?id=d318a996b) dhcp: ipv6 prefix delegation improvements
  - [02bfd641b](https://git.fd.io/vpp/commit/?id=02bfd641b) dhcp: Move to plugin

Source Code: [https://git.fd.io/vpp/tree/src/plugins/dhcp](https://git.fd.io/vpp/tree/src/plugins/dhcp) 
### GPRS Tunneling Protocol
Maintainer: Hongjun Ni <hongjun.ni@intel.com>  

An implementation of the GPRS Tunnelling Protocol

- GTPU decapsulation
- GTPU encapsulation

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Source Code: [https://git.fd.io/vpp/tree/src/plugins/gtpu](https://git.fd.io/vpp/tree/src/plugins/gtpu) 
### Generic Routing Encapsulation
Maintainer: Neale Ranns <nranns@cisco.com>  

An implementation of Generic Routing Encapsulation (GRE)

- L3 tunnels, all combinations of IPv4 and IPv6
- Encap/Decap flags to control the copying of DSCP, ECN, DF from overlay to underlay and vice-versa.
- L2 tunnels

Feature maturity level: production  
Supports: API CLI MULTITHREAD  

Not yet implemented:  
- GRE keys

Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [5f8f61733](https://git.fd.io/vpp/commit/?id=5f8f61733) gre: Multi-point interfaces

Source Code: [https://git.fd.io/vpp/tree/src/vnet/gre](https://git.fd.io/vpp/tree/src/vnet/gre) 
### IP Neighbour Database
Maintainer: Neale Ranns <nranns@cisco.com>  



- IP protocol independent Database of Neighbours (aka peers)
- limits on number of peers, recycling and aging

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

Source Code: [https://git.fd.io/vpp/tree/src/vnet/ip-neighbor](https://git.fd.io/vpp/tree/src/vnet/ip-neighbor) 
### IP Security
Maintainer: Neale Ranns <nranns@cisco.com>  

An implementation of IPSec

- IPSec (https://tools.ietf.org/html/rfc4301)
- Authetication Header (https://tools.ietf.org/html/rfc4302)
- Encapsulating Security Payload (https://tools.ietf.org/html/rfc4303)

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [f62a8c013](https://git.fd.io/vpp/commit/?id=f62a8c013) ipsec: bind an SA to a worker
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9534696b4](https://git.fd.io/vpp/commit/?id=9534696b4) ipip: Tunnel flags controlling copying data to/from payload/encap
  - [12989b538](https://git.fd.io/vpp/commit/?id=12989b538) ipsec: remove dedicated IPSec tunnels
  - [01d61e788](https://git.fd.io/vpp/commit/?id=01d61e788) ipsec: add insecure option for format of SA
  - [b325983a4](https://git.fd.io/vpp/commit/?id=b325983a4) ipsec: support 4o6 and 6o4 for tunnel protect
  - [670027a50](https://git.fd.io/vpp/commit/?id=670027a50) ipsec: Add 'detail' option to 'sh ipsec sa'

Source Code: [https://git.fd.io/vpp/tree/src/vnet/ipsec](https://git.fd.io/vpp/tree/src/vnet/ipsec) 
### IP in IP tunnelling
Maintainer: Ole Troan <ot@cisco.com>  

Implements IP{v4,v6} over IP{v4,v6} tunnelling as
described in RFC2473. This module also implements the
border relay of 6RD (RFC5969).

- IPv4/IPv6 over IPv4/IPv6 encapsulation
  - Fragmentation and Reassembly
  - Configurable MTU
  - Inner to outer Traffic Class / TOS copy
  - Configurable Traffic Class / TOS

- ICMPv4 / ICMPv6 proxying
- 6RD (RFC5969)
  - Border Relay


Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  

Not yet implemented:  
- Tunnel PMTUD
- Tracking of FIB state for tunnel state
- IPv6 extension headers (Tunnel encapsulation limit option)

Feature commits:
  - [9534696b4](https://git.fd.io/vpp/commit/?id=9534696b4) ipip: Tunnel flags controlling copying data to/from payload/encap
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

Source Code: [https://git.fd.io/vpp/tree/src/vnet/ipip](https://git.fd.io/vpp/tree/src/vnet/ipip) 
### IPFIX probe
Maintainer: Ole Troan <ot@cisco.com>  

IPFIX flow probe. Works in the L2, or IP input feature path.

- L2 input feature
- IPv4 / IPv6 input feature
- Recording of L2, L3 and L4 information

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  

Not yet implemented:  
- Output path
- Export over IPv6
- Export over TCP/SCTP

Feature commits:
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

Source Code: [https://git.fd.io/vpp/tree/src/plugins/flowprobe](https://git.fd.io/vpp/tree/src/plugins/flowprobe) 
### IPSec crypto engine provided by Intel IPSecMB library
Maintainer: Neale Ranns <nranns@cisco.com>  



- SHA(1, 224, 256, 384, 512)
- CBC(128, 192, 256)
- GCM(128, 192, 256)

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [76a36e83e](https://git.fd.io/vpp/commit/?id=76a36e83e) crypto-ipsecmb: improve gcm performance using dedicated API.

Source Code: [https://git.fd.io/vpp/tree/src/plugins/crypto_ipsecmb](https://git.fd.io/vpp/tree/src/plugins/crypto_ipsecmb) 
### IPSec crypto engine provided by Openssl library
Maintainer: Damjan Marion <damarion@cisco.com>  



- SHA(1, 224, 256, 384, 512)
- CBC(128, 192, 256)
- GCM(128, 192, 256)
- CTR(128, 192, 256)
- DES, 3DES
- MD5

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Source Code: [https://git.fd.io/vpp/tree/src/plugins/crypto_openssl](https://git.fd.io/vpp/tree/src/plugins/crypto_openssl) 
### IPSec crypto engine provided by native implementation
Maintainer: Damjan Marion <damarion@cisco.com>  

An implentation of a native crypto-engine

- CBC(128, 192, 256)
- GCM(128, 192, 256)

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [9fb6d40eb](https://git.fd.io/vpp/commit/?id=9fb6d40eb) misc: add address sanitizer heap instrumentation

Source Code: [https://git.fd.io/vpp/tree/src/plugins/crypto_ia32](https://git.fd.io/vpp/tree/src/plugins/crypto_ia32) 
### IPv6 Neighbor Discovery
Maintainer: Neale Ranns <nranns@cisco.com>  

An implementation of the IPv6 Neighbor discovery protocol as described in RFC4861 and RFC4862.

- Neighbor discovery.
- ND Auto address configuration
- Multicast Listener Discovery - only as host role to send adverts
- Router Advertisements

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

Source Code: [https://git.fd.io/vpp/tree/src/vnet/ip6-nd](https://git.fd.io/vpp/tree/src/vnet/ip6-nd) 
### Internet Group Management Protocol
Maintainer: Neale Ranns <nranns@cisco.com>  

An implementation of the Internet Group Management Protocol (IGMP)

- IGMPv3 only.

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Source Code: [https://git.fd.io/vpp/tree/src/plugins/igmp](https://git.fd.io/vpp/tree/src/plugins/igmp) 
### L2TPv3
Maintainer: unmaintained  

An initial and incomplete implementation of L2TPv3 (RFC3931).

- L2TPv3 over IPv6

Feature maturity level: experimental  
Supports: API CLI  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/l2tp](https://git.fd.io/vpp/tree/src/vnet/l2tp) 
### Layer 2 Forwarding
Maintainer: John Lo <loj@cisco.com>  

Layer 2 Bridging and Cross-Connect Support

- Layer 2 (L2) Cross-connect (xconnect) of two interfaces
- Layer 2 (L2) Bridging of multiple interfaces in a bridge domain (BD)
  - Forwarding via destination MAC address of packet
  - MAC learning enable/disable on BD or per interface
  - MAC aging with specified aging interval enable/disable
  - MAC flush of learned MACs on interface down, BD deletion, or by user
  - User added static MACs not subject to aging nor overwritten by MAC learn
  - User added MACs not subject to aging but can be overwritten by MAC learn
  - Unicast forwarding enable/disable
  - Unknown unicast flooding enable/disable
  - Multicast/broadcast flooding enable/disable
  - ARP-termination to avoid flooding of ARP requests
  - Enable/disable unicast of ARP requests instead of flooding
  - BVI (Bridge Virtual Interface) for IP forwarding from or to BD
  - Set interface in BD to send unknown unicast packets instead of flooding
  - Support of split horizon group (SHG) on BD interfaces

- VLAN tag rewrite on L2 bridging or xconnect interfaces

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9fb6d40eb](https://git.fd.io/vpp/commit/?id=9fb6d40eb) misc: add address sanitizer heap instrumentation
  - [830493392](https://git.fd.io/vpp/commit/?id=830493392) classify: use vector code even when data is not aligned

Source Code: [https://git.fd.io/vpp/tree/src/vnet/l2](https://git.fd.io/vpp/tree/src/vnet/l2) 
### Layer 3 cross connect
Maintainer: Neale Ranns <nranns@cisco.com>  



- cross connect all ingress traffic on an L3 interface to an output FIB path.
- the path can describe any output (with the exception of MPLS labels)
- The same functions can be acheived by using a dedicated VRF for the table and adding a default route with the same path. However, the L3XC is more efficient in memory and CPU

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

Source Code: [https://git.fd.io/vpp/tree/src/plugins/l3xc](https://git.fd.io/vpp/tree/src/plugins/l3xc) 
### Link Aggregation Control Protocol
Maintainer: Steven Luong <sluong@cisco.com>  

Link Aggregation Control Protocol implementation (LACP)

- Support LACP version 1 specification including marker protocol

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [aa7257863](https://git.fd.io/vpp/commit/?id=aa7257863) bonding: Add /if/lacp/<bond-sw_if_index>/<slave-sw_if_index>/partner-state
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/plugins/lacp](https://git.fd.io/vpp/tree/src/plugins/lacp) 
### Link Layer Discovery Protocol
Maintainer: Klement Sekera <ksekera@cisco.com>  

Link Layer Discovery Protocol (LLDP) implementation

- link layer discovery protocol implementation

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/lldp](https://git.fd.io/vpp/tree/src/vnet/lldp) 
### Load Balancer
Maintainer: Pfister <ppfister@cisco.com>, Hongjun Ni <hongjun.ni@intel.com>  



- GRE tunnel mode
- NAT mode
- L3DSR mode
- Consistent Hash
- Connection Track

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour
  - [33538a150](https://git.fd.io/vpp/commit/?id=33538a150) lb: add APIs for set interface nat4 and nat6

Source Code: [https://git.fd.io/vpp/tree/src/plugins/lb](https://git.fd.io/vpp/tree/src/plugins/lb) 
### Locator ID Separation Protocol Control Plane
Maintainer: Florin Coras <fcoras@cisco.com>  

Locator ID Separation Protocol control plane (LISP) implementation

- ITR, ETR and RTR mode of operation
- Multitenancy
- Multihoming
- Source/dest map-cache lookups
- RLOC-probing
- Support for Ethernet, IPv4, IPv6 and NSH EIDs (payloads)
- Map-resolver failover algorithm

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/lisp-cp](https://git.fd.io/vpp/tree/src/vnet/lisp-cp) 
### Locator ID Separation Protocol Generic Protocol Extension
Maintainer: Florin Coras <fcoras@cisco.com>  

Locator ID Separation Protocol Generic Protocol Extension (LISP-GPE) implementation

- ITR, ETR and RTR modes
- Support for Ethernet, IPv4, IPv6 and NSH EIDs (payloads)
- Source/dest forwarding
- IPv4 and IPv6 RLOCs

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/lisp-gpe](https://git.fd.io/vpp/tree/src/vnet/lisp-gpe) 
### Mapping of Address and Port
Maintainer: Ole Troan <ot@cisco.com>  

Mapping of Address and Port (MAP): IPv4 as a service mechanisms. Tunnel or translate an IPv4 address, an IPv4 subnet or a shared IPv4 address. In shared IPv4 address mode, only UDP, TCP and restricted ICMP is supported.

- LW46 BR (RFC7596)
  - Fragmentation and Reassembly

- MAP-E BR (RFC7597)
- MAP-T BR (RFC7599)

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [ff47fb645](https://git.fd.io/vpp/commit/?id=ff47fb645) vppapigen map: raise ValueError when fieldname is python keyword

Source Code: [https://git.fd.io/vpp/tree/src/plugins/map](https://git.fd.io/vpp/tree/src/plugins/map) 
### Multi-Protocol Label Switching
Maintainer: Neale Ranns <nranns@cisco.com>  

An implementation of Multi-Protocol Label Switching (MPLS)

- Label imposition/disposition - pipe and uniform mode
- Tunnels - unidirectional

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9db6ada77](https://git.fd.io/vpp/commit/?id=9db6ada77) fib: Table Replace

Source Code: [https://git.fd.io/vpp/tree/src/vnet/mpls](https://git.fd.io/vpp/tree/src/vnet/mpls) 
### NSH
Maintainer: Hongjun Ni <hongjun.ni@intel.com>, Vengada <venggovi@cisco.com>  

NSH for SFC

- NSH Classifier
- NSH Forwarder
- NSH SF
- NSH Proxy
- NSH OAM
- NSH Metadata

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/plugins/nsh](https://git.fd.io/vpp/tree/src/plugins/nsh) 
### Netmap Device
Maintainer: Damjan Marion <damarion@cisco.com>  

Create a netmap interface, which is a high speed user-space interface that allows VPP to patch into a linux namespace, a linux container, or a physical NIC without the use of DPDK.

- L4 checksum offload

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  

Not yet implemented:  
- API dump

Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace

Source Code: [https://git.fd.io/vpp/tree/src/vnet/devices/netmap](https://git.fd.io/vpp/tree/src/vnet/devices/netmap) 
### Network Address Translation
Maintainers: Ole Troan <ot@cisco.com>, Filip Varga <fivarga@cisco.com>  

The Network Address Translation (NAT) plugin offers a multiple address translation functions. These can be used in a raft of different scenarios. CPE, CGN, etc.

- NAT44
  - 1:1 NAT
  - 1:1 NAT with ports
  - VRF awareness
  - Multiple inside interfaces
  - Hairpinning
  - IPFIX
  - Syslog
  - Endpoint dependent NAT
  - TCP MSS clamping
  - Local bypass (DHCP)

- CGN - deterministic NAT
- NAT64
- NAT66
- DS-lite
- 464XLAT

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour
  - [9db6ada77](https://git.fd.io/vpp/commit/?id=9db6ada77) fib: Table Replace
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [22bb417e9](https://git.fd.io/vpp/commit/?id=22bb417e9) nat: handoff traffic matching for dynamic NAT

Source Code: [https://git.fd.io/vpp/tree/src/plugins/nat](https://git.fd.io/vpp/tree/src/plugins/nat) 
### Network Delay Simulator
Maintainer: Dave Barach <dave@barachs.net>  

Introduces configurable network delay and loss

- Network delay and loss fraction simulator

Feature maturity level: production  
Supports: CLI MULTITHREAD  
Source Code: [https://git.fd.io/vpp/tree/src/plugins/nsim](https://git.fd.io/vpp/tree/src/plugins/nsim) 
### PPPoE
Maintainer: Hongjun Ni <hongjun.ni@intel.com>  

PPP over Ethernet

- PPPoE Control Plane packet dispatch
- PPPoE decapsulation
- PPPoE encapsulation

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour

Source Code: [https://git.fd.io/vpp/tree/src/plugins/pppoe](https://git.fd.io/vpp/tree/src/plugins/pppoe) 
### Pipe Device
Maintainer: Damjan Marion <damarion@cisco.com>  

Create a pipe device interface, which can pass packets bidirectionally in one side of the pipe to the other side of the pipe. While similar in behavior to a unix pipe, it is not a host-based pipe.

- L4 checksum offload

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  

Not yet implemented:  
- does not use hw-address
- does not support tagged traffic
- API dump filtering by sw_if_index

Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

Source Code: [https://git.fd.io/vpp/tree/src/vnet/devices/pipe](https://git.fd.io/vpp/tree/src/vnet/devices/pipe) 
### QUIC Protocol
Maintainer: Aloys Augustin <aloaugus@cisco.com>  

IETF QUIC Protocol implementation

- host stack integration via session layer
- based on the Quicly library: https://github.com/h2o/quicly

Feature maturity level: experimental  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [d1b9e7068](https://git.fd.io/vpp/commit/?id=d1b9e7068) quic: Implement crypto contexts
  - [ecb9d18c5](https://git.fd.io/vpp/commit/?id=ecb9d18c5) quic: update quicly to v0.0.8-vpp
  - [c00f480ba](https://git.fd.io/vpp/commit/?id=c00f480ba) quic: Add support for unidirectional streams
  - [deaf97f45](https://git.fd.io/vpp/commit/?id=deaf97f45) quic: Add aggregated quicly stats
  - [1802fcc5f](https://git.fd.io/vpp/commit/?id=1802fcc5f) quic: add more detailed statistics
  - [69885b72a](https://git.fd.io/vpp/commit/?id=69885b72a) quic: update quicly to v0.0.7-vpp
  - [2f566c23f](https://git.fd.io/vpp/commit/?id=2f566c23f) quic: add conn-timeout config option
  - [dcbbf2833](https://git.fd.io/vpp/commit/?id=dcbbf2833) quic: Add support for ckpair & crypto engine
  - [340c15c6e](https://git.fd.io/vpp/commit/?id=340c15c6e) docs: add spellcheck to 'make docs' sphinx docs
  - [79f89537c](https://git.fd.io/vpp/commit/?id=79f89537c) session: Add certificate store
  - [00078b991](https://git.fd.io/vpp/commit/?id=00078b991) quic: make quic fifo size configurable via cli
  - [72c159e64](https://git.fd.io/vpp/commit/?id=72c159e64) quic: update quicly to v0.0.5
  - [dd4d8ac29](https://git.fd.io/vpp/commit/?id=dd4d8ac29) quic: Create custom event logger
  - [ff1f6faaa](https://git.fd.io/vpp/commit/?id=ff1f6faaa) quic: Add Tx, Rx and packet drop counters
  - [922f0b211](https://git.fd.io/vpp/commit/?id=922f0b211) quic: add cli command for stats

Source Code: [https://git.fd.io/vpp/tree/src/plugins/quic](https://git.fd.io/vpp/tree/src/plugins/quic) 
### Quality of Service
Maintainer: Neale Ranns <nranns@cisco.com>  

An implentation of Quality of Service (QoS)

- Record - extract QoS bits from packets headers and write in metadata
- Mapp - defines simple transform of QoS bits from/to each packet layer
- Mark - write [mapped] QoS bits into packet headers
- Store - write in packet metadata a fixed QoS value

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/qos](https://git.fd.io/vpp/tree/src/vnet/qos) 
### SRv6 - Service Chaining Dynamic Proxy
Maintainer: Francois Clad <fclad@cisco.com>  

SRv6 dynamic proxy

- SRv6 - dynamic service chaining proxy (draft-ietf-spring-sr-service-programming-01)

Feature maturity level: production  
Supports: CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile

Source Code: [https://git.fd.io/vpp/tree/src/plugins/srv6-ad](https://git.fd.io/vpp/tree/src/plugins/srv6-ad) 
### SRv6 - Service Chaining Masquerading Proxy
Maintainer: Francois Clad <fclad@cisco.com>  

SRv6 masquerading proxy

- SRv6 - masquerading service chaining proxy (draft-ietf-spring-sr-service-programming-01)

Feature maturity level: production  
Supports: CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile

Source Code: [https://git.fd.io/vpp/tree/src/plugins/srv6-am](https://git.fd.io/vpp/tree/src/plugins/srv6-am) 
### SRv6 - Service Chaining Static Proxy
Maintainer: Francois Clad <fclad@cisco.com>  

SRv6 static proxy

- SRv6 - static service chaining proxy (draft-ietf-spring-sr-service-programming-01)

Feature maturity level: production  
Supports: CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile
  - [eeb5fb3a5](https://git.fd.io/vpp/commit/?id=eeb5fb3a5) sr: add "set sr encaps hop-limit" command

Source Code: [https://git.fd.io/vpp/tree/src/plugins/srv6-as](https://git.fd.io/vpp/tree/src/plugins/srv6-as) 
### SRv6 Mobuile
Maintainer: Tetsuya Murakami <tetsuya.mrk@gmail.com>  

SRv6 Mobile End Functions. GTP4.D, GTP4.E, GTP6.D, GTP6.D.Di and GTP6.E are supported.

- GTP4.D
- GTP4.E
- GTP6.D
- GTP6.D.Di
- GTP6.E

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [57584d99d](https://git.fd.io/vpp/commit/?id=57584d99d) srv6-mobile:
  - [70d8ef89a](https://git.fd.io/vpp/commit/?id=70d8ef89a) srv6-mobile
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile

Source Code: [https://git.fd.io/vpp/tree/src/plugins/srv6-mobile](https://git.fd.io/vpp/tree/src/plugins/srv6-mobile) 
### Segment Routing for IPv6 (SRv6)
Maintainer: Pablo Camarillo <pcamaril@cisco.com>  

Full SRv6 Network Programming implementation

- Support for SRv6 Network Programming (draft-ietf-spring-srv6-network-programming-07)
- SR Headend behaviors (H.Encaps, H.Encaps.Red, H.Encaps.L2, H.Encaps.L2.Red)
- SR Endpoint behaviors (End, End.X, End.T) for intermediate TE with PSP support
- SR Endpoint behaviors (End.DX4, End.DX6, End.DT4, End.DT6, End.DX2) for overlay creation
- SR Endpoint behaviors (End.B6.Encaps.Red) for BindingSID instantiation
- Support for SRH insertion (draft-filsfils-spring-srv6-net-pgm-insertion-01)
- SR counters
- SR policy implementation (draft-ietf-spring-segment-routing-policy-02)
- SR steering based on IP prefix / L2 interface classification

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [57584d99d](https://git.fd.io/vpp/commit/?id=57584d99d) srv6-mobile:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [70d8ef89a](https://git.fd.io/vpp/commit/?id=70d8ef89a) srv6-mobile
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile
  - [eeb5fb3a5](https://git.fd.io/vpp/commit/?id=eeb5fb3a5) sr: add "set sr encaps hop-limit" command

Source Code: [https://git.fd.io/vpp/tree/src/vnet/srv6](https://git.fd.io/vpp/tree/src/vnet/srv6) 
### Segment Routing for MPLS
Maintainer: Pablo Camarillo <pcamaril@cisco.com>  

SR-MPLS

- SR Policy support
- Automated steering (SR steering based on NextHop/Color)

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/srmpls](https://git.fd.io/vpp/tree/src/vnet/srmpls) 
### Session Layer
Maintainer: Florin Coras <fcoras@cisco.com>  

The session layer facilitates the interaction between northbound applications and southbound transport protocols. To this end, northbound, through the app-interface sub layer, the session layer exposes APIs for applications to interact with abstract units of communication, i.e., sessions. And southbound, through the transport protocol interface, it exposes APIs that allow transport protocols to exchange data and events (ctrl and io) with applications, without actually being aware of how that communication is carried out.

- Manages allocation and tracking of sessions (6-tuple lookup tables)
- App namespaces that constrain application access to network resources
- Conveys data and notifications (ctrl and io) between transport protocols and apps
- Transport protocol interface
  - Provides generic transport protocol template
  - Converts between transport and application representation of data
  - Schedules sessions/connections for sending

- Application interface
  - Maintains per application state
  - Manages allocation of shared memory resources used for exchanging data between applications and transports
  - Exposes a native C and a binary api for builtin and external apps respectively


Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [b092b77cf](https://git.fd.io/vpp/commit/?id=b092b77cf) tcp: Enable TCP timewait port use
  - [d1b9e7068](https://git.fd.io/vpp/commit/?id=d1b9e7068) quic: Implement crypto contexts
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [ef4f3e7fe](https://git.fd.io/vpp/commit/?id=ef4f3e7fe) session svm: support for segments larger than 4GB
  - [cfdb10918](https://git.fd.io/vpp/commit/?id=cfdb10918) session: Add mq debug cli
  - [c00f480ba](https://git.fd.io/vpp/commit/?id=c00f480ba) quic: Add support for unidirectional streams
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [11e9e3510](https://git.fd.io/vpp/commit/?id=11e9e3510) session tcp: support pacer idle timeouts
  - [d9035a409](https://git.fd.io/vpp/commit/?id=d9035a409) session tcp: add opaque data to show cli
  - [91f90d082](https://git.fd.io/vpp/commit/?id=91f90d082) session: more show cli output
  - [93e060aee](https://git.fd.io/vpp/commit/?id=93e060aee) session: Increasing the Header lengthe size
  - [de6caf481](https://git.fd.io/vpp/commit/?id=de6caf481) session: Add crypto context
  - [45ec9f49b](https://git.fd.io/vpp/commit/?id=45ec9f49b) session: ckpair store & crypto engine as mq params
  - [dd97a48d9](https://git.fd.io/vpp/commit/?id=dd97a48d9) session: reschedule asap when snd space constrained
  - [79ba25d40](https://git.fd.io/vpp/commit/?id=79ba25d40) session: support registration of custom crypto engines
  - [ef7cbf6ad](https://git.fd.io/vpp/commit/?id=ef7cbf6ad) vcl: add api to set lcl ip
  - [2a7ea2ee9](https://git.fd.io/vpp/commit/?id=2a7ea2ee9) session tcp: infra for transports to send buffers
  - [c31dc31f8](https://git.fd.io/vpp/commit/?id=c31dc31f8) tcp: improve pacing after idle send periods
  - [be237bf02](https://git.fd.io/vpp/commit/?id=be237bf02) tcp: retry lost retransmits
  - [79f89537c](https://git.fd.io/vpp/commit/?id=79f89537c) session: Add certificate store
  - [36ebcfffb](https://git.fd.io/vpp/commit/?id=36ebcfffb) tcp: use sacks for timer based recovery
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace
  - [5c29029ef](https://git.fd.io/vpp/commit/?id=5c29029ef) session: builtin app rx notifications regardless of state
  - [7c8f828ba](https://git.fd.io/vpp/commit/?id=7c8f828ba) session: limit pacer bucket size
  - [1292d19c7](https://git.fd.io/vpp/commit/?id=1292d19c7) session: add session enable option in config file
  - [1146ff4bc](https://git.fd.io/vpp/commit/?id=1146ff4bc) tcp: enable gso in tcp hoststack
  - [5bb23ecd0](https://git.fd.io/vpp/commit/?id=5bb23ecd0) session: improve cli
  - [dfb3b8771](https://git.fd.io/vpp/commit/?id=dfb3b8771) session: add explicit reset api

Source Code: [https://git.fd.io/vpp/tree/src/vnet/session](https://git.fd.io/vpp/tree/src/vnet/session) 
### Source VRF Select
Maintainer: Neale Ranns <nranns@cisco.com>  



- Determine the input VRF/table based on the source IP address
- routes are added to tables.
- route lookup is performed using the packet's source address
- The route is programmed with the table in which the subsequent destination address lookup will be performed
- Tables are bound to interfaces.
- SVS runs as an input feature in the L3 path

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour

Source Code: [https://git.fd.io/vpp/tree/src/plugins/svs](https://git.fd.io/vpp/tree/src/plugins/svs) 
### Static http https server
Maintainer: Dave Barach <dave@barachs.net>  

A simple caching static http / https server A built-in vpp host stack application. Supports HTTP GET and HTTP POST methods.

- An extensible static http/https server with caching

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [e0fd9ed11](https://git.fd.io/vpp/commit/?id=e0fd9ed11) http_static: add "http static cache clear" CLI
  - [5554c56a6](https://git.fd.io/vpp/commit/?id=5554c56a6) http_static: add dynamic GET / POST method hooks

Source Code: [https://git.fd.io/vpp/tree/src/plugins/http_static](https://git.fd.io/vpp/tree/src/plugins/http_static) 
### Tap Device
Maintainer: damarion@cisco.com sluong@cisco.com sykazmi@cisco.com  

Create a tap v2 device interface, which connects to a tap interface on the host system.

- Virtio

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  

Not yet implemented:  
- API dump filtering by sw_if_index

Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [7c6102b1a](https://git.fd.io/vpp/commit/?id=7c6102b1a) tap: multiqueue support
  - [39807d02c](https://git.fd.io/vpp/commit/?id=39807d02c) tap: add check for vhost-net backend
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

Source Code: [https://git.fd.io/vpp/tree/src/vnet/devices/tap](https://git.fd.io/vpp/tree/src/vnet/devices/tap) 
### Time-range-based MAC-address filter
Maintainer: Dave Barach <dave@barachs.net>  

Device-input/output arc driver level MAC filter. Checks to see if traffic is allowed to/from the given MAC address, and takes the appropriate action. Intended for the home gateway use-case, where WAN traffic is billed per bit.

- Static / time-range / data quota based MAC address filter

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [ef3c11ca9](https://git.fd.io/vpp/commit/?id=ef3c11ca9) mactime: add the "mactime.json" builtin URL
  - [5932ce17e](https://git.fd.io/vpp/commit/?id=5932ce17e) tests: add cli_return_response to vpp_papi_provider
  - [2c41a61d5](https://git.fd.io/vpp/commit/?id=2c41a61d5) mactime: add a "top" command to watch device stats

Source Code: [https://git.fd.io/vpp/tree/src/plugins/mactime](https://git.fd.io/vpp/tree/src/plugins/mactime) 
### Transmission Control Protocol
Maintainer: Florin Coras <fcoras@cisco.com>  

High speed and scale Transmission Control Protocol (TCP) implementation

- Core functionality (RFC793, RFC5681, RFC6691)
- Extensions for high performance (RFC7323)
- Congestion control extensions (RFC3465, RFC8312)
- Loss recovery extensions (RFC2018, RFC3042, RFC6582, RFC6675, RFC6937)
- Detection and prevention of spurious retransmits (RFC3522)
- Defending spoofing and flooding attacks (RFC6528)
- Partly implemented features (RFC1122, RFC4898, RFC5961)
- Delivery rate estimation (draft-cheng-iccrg-delivery-rate-estimation)

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [93e053ebe](https://git.fd.io/vpp/commit/?id=93e053ebe) tcp: add FEATURE.yaml
  - [b092b77cf](https://git.fd.io/vpp/commit/?id=b092b77cf) tcp: Enable TCP timewait port use
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [f4ce6ba22](https://git.fd.io/vpp/commit/?id=f4ce6ba22) tcp: add no csum offload config option
  - [11e9e3510](https://git.fd.io/vpp/commit/?id=11e9e3510) session tcp: support pacer idle timeouts
  - [d9035a409](https://git.fd.io/vpp/commit/?id=d9035a409) session tcp: add opaque data to show cli
  - [b3dce89a7](https://git.fd.io/vpp/commit/?id=b3dce89a7) tcp: improve lost rxt heuristic
  - [cf4c2102d](https://git.fd.io/vpp/commit/?id=cf4c2102d) tcp: validate the IP address while checking TCP connection
  - [46ec6e018](https://git.fd.io/vpp/commit/?id=46ec6e018) tcp: track lost rxt segments in byte tracker
  - [2a7ea2ee9](https://git.fd.io/vpp/commit/?id=2a7ea2ee9) session tcp: infra for transports to send buffers
  - [c31dc31f8](https://git.fd.io/vpp/commit/?id=c31dc31f8) tcp: improve pacing after idle send periods
  - [be237bf02](https://git.fd.io/vpp/commit/?id=be237bf02) tcp: retry lost retransmits
  - [02833ff32](https://git.fd.io/vpp/commit/?id=02833ff32) tcp: custom checksum calculations for Ipv4/Ipv6
  - [36ebcfffb](https://git.fd.io/vpp/commit/?id=36ebcfffb) tcp: use sacks for timer based recovery
  - [7436b4367](https://git.fd.io/vpp/commit/?id=7436b4367) tcp: compute snd time for rate sample
  - [1dbda64b4](https://git.fd.io/vpp/commit/?id=1dbda64b4) tcp: use rate sample rtt in recovery if possible
  - [558e3e095](https://git.fd.io/vpp/commit/?id=558e3e095) tcp: handle sack reneging
  - [1146ff4bc](https://git.fd.io/vpp/commit/?id=1146ff4bc) tcp: enable gso in tcp hoststack
  - [78dae0088](https://git.fd.io/vpp/commit/?id=78dae0088) tcp: validate connections in output
  - [5bb23ecd0](https://git.fd.io/vpp/commit/?id=5bb23ecd0) session: improve cli
  - [017dc4524](https://git.fd.io/vpp/commit/?id=017dc4524) tcp: send rwnd update only if wnd is large enough
  - [182d21983](https://git.fd.io/vpp/commit/?id=182d21983) tcp: force zero window on full rx fifo
  - [a495a3ea1](https://git.fd.io/vpp/commit/?id=a495a3ea1) tcp: track zero rwnd errors
  - [a436a4222](https://git.fd.io/vpp/commit/?id=a436a4222) tcp: add option for always on event logging
  - [dfb3b8771](https://git.fd.io/vpp/commit/?id=dfb3b8771) session: add explicit reset api
  - [12f6936cd](https://git.fd.io/vpp/commit/?id=12f6936cd) tcp: set cc_algo on connection alloc
  - [d206724e7](https://git.fd.io/vpp/commit/?id=d206724e7) tcp: allow cc algos to set pacing rate
  - [9094b5c31](https://git.fd.io/vpp/commit/?id=9094b5c31) tcp: extend protocol configuration

Source Code: [https://git.fd.io/vpp/tree/src/vnet/tcp](https://git.fd.io/vpp/tree/src/vnet/tcp) 
### Transport Layer Security
Maintainers: Florin Coras <fcoras@cisco.com>, Ping Yu <ping.yu@intel.com>  

Transport Layer Security (TLS) protocol implementation that consists of a set of engines that act as wrappers for existing TLS implementations, e.g., OpenSSL, Picotls and MbedTLS, and a framework that integrates the engines into VPP's host stack

- Framework that supports pluggable TLS engines
- OpenSSL, Picotls and MbedTLS engines

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [0d74dd1f8](https://git.fd.io/vpp/commit/?id=0d74dd1f8) tls: improve connection formating
  - [79f89537c](https://git.fd.io/vpp/commit/?id=79f89537c) session: Add certificate store

Source Code: [https://git.fd.io/vpp/tree/src/vnet/tls](https://git.fd.io/vpp/tree/src/vnet/tls) 
### User Datagram Protocol
Maintainer: Florin Coras <fcoras@cisco.com>  

User Datagram Protocol (UDP) implementation

- host stack integration via session layer
- standalone per port dispatcher for tunneling protocols

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/udp](https://git.fd.io/vpp/tree/src/vnet/udp) 
### VNET GSO
Maintainer: ayourtch@gmail.com sykazmi@cisco.com  

Generic Segmentation Offload

- Basic GSO support
- GSO for VLAN tagged packets
- Provide inline function to get header offsets

Feature maturity level: experimental  
Supports: API CLI  

Not yet implemented:  
- Tunnels i.e. VXLAN

Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [72e7312af](https://git.fd.io/vpp/commit/?id=72e7312af) gso: add protocol header parser

Source Code: [https://git.fd.io/vpp/tree/src/vnet/gso](https://git.fd.io/vpp/tree/src/vnet/gso) 
### VPP Comms Library
Maintainer: Florin Coras <fcoras@cisco.com>  

VPP Comms Library (VCL) simplifies app interaction with session layer by exposing APIs that are similar to but not POSIX-compliant.

- Abstracts vpp host stack sessions to integer session handles
- Exposes its own async communication functions, i.e., epoll, select, poll
- Supports multi-worker applications
- Sessions cannot be shared between multiple threads/processes
- VCL Locked Sessions (VLS)
  - Ensure through locking that only one thread accesses a session at a time
  - Detects and registers forked processes as new VCL workers. It does not register threads as new workers.

- LD_PRELOAD shim (LDP)
  - Intercepts syscalls and injects them into VLS.
  - Applications that are supported work with VCL and implicitly with VPP's host stack without any code change
  - It does not support all syscalls and syscall options


Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9fb6d40eb](https://git.fd.io/vpp/commit/?id=9fb6d40eb) misc: add address sanitizer heap instrumentation
  - [d747c3c36](https://git.fd.io/vpp/commit/?id=d747c3c36) vcl: add config option for preferred tls engine
  - [ef7cbf6ad](https://git.fd.io/vpp/commit/?id=ef7cbf6ad) vcl: add api to set lcl ip
  - [57c88938f](https://git.fd.io/vpp/commit/?id=57c88938f) vcl: allow non-blocking connects

Source Code: [https://git.fd.io/vpp/tree/src/vcl](https://git.fd.io/vpp/tree/src/vcl) 
### Virtio PCI Device
Maintainer: Mohsin Kazmi <sykazmi@cisco.com>  

Create a virtio-backed PCI device interface

- connection to the emulated pci interface presented to vpp from the host interface.

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  

Not yet implemented:  
- API dump filtering by sw_if_index

Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [72e7312af](https://git.fd.io/vpp/commit/?id=72e7312af) gso: add protocol header parser
  - [7c6102b1a](https://git.fd.io/vpp/commit/?id=7c6102b1a) tap: multiqueue support
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace

Source Code: [https://git.fd.io/vpp/tree/src/vnet/devices/virtio](https://git.fd.io/vpp/tree/src/vnet/devices/virtio) 
### Virtual eXtensible LAN
Maintainer: John Lo <loj@cisco.com>  

Virtual eXtensible LAN (VXLAN) tunnels support L2 overlay networks that span L3 networks

- VXLAN tunnel for support of L2 overlay/virtual networks (RFC-7348)
- Support either IPv4 or IPv6 underlay network VTEPs
- Flooding via headend replication if all VXLAN tunnels in BD are unicast ones
- Multicast VXLAN tunnel can be added to BD to flood via IP multicast
- VXLAN encap with flow-hashed source port for better underlay IP load balance
- VXLAN decap optimization via vxlan-bypass IP feature on underlay interfaces
- VXLAN decap HW offload using flow director with DPDK on Intel Fortville NICs

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/vxlan](https://git.fd.io/vpp/tree/src/vnet/vxlan) 
### VxLAN-GPE
Maintainer: Hongjun Ni <hongjun.ni@intel.com>  

VxLAN-GPE tunnel handling

- VxLAN-GPE decapsulation
- VxLAN-GPE encapsulation

Feature maturity level: production  
Supports: API CLI MULTITHREAD  
Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

Source Code: [https://git.fd.io/vpp/tree/src/vnet/vxlan-gpe](https://git.fd.io/vpp/tree/src/vnet/vxlan-gpe) 
### host-interface Device AF_PACKET
Maintainer: Damjan Marion <damarion@cisco.com>  

Create a host interface that will attach to a linux AF_PACKET interface, one side of a veth pair. The veth pair must already exist. Once created, a new host interface will exist in VPP with the name 'host-<ifname>', where '<ifname>' is the name of the specified veth pair. Use the 'show interface' command to display host interface details.

- L4 checksum offload

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  

Not yet implemented:  
- API dump details beyond sw_if_index and name

Feature commits:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace

Source Code: [https://git.fd.io/vpp/tree/src/vnet/devices/af_packet](https://git.fd.io/vpp/tree/src/vnet/devices/af_packet) 
### rdma device driver
Maintainer: Benoît Ganne <bganne@cisco.com>  

rdma device driver support

- rdma driver for Mellanox ConnectX-4/5 adapters

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [d8c1ef925](https://git.fd.io/vpp/commit/?id=d8c1ef925) rdma: api: prepare support for direct verb
  - [812afe712](https://git.fd.io/vpp/commit/?id=812afe712) rdma: add rdma API
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace
  - [0dcafcc50](https://git.fd.io/vpp/commit/?id=0dcafcc50) rdma: add support for MAC changes
  - [74eba446b](https://git.fd.io/vpp/commit/?id=74eba446b) rdma: add support for input feature arcs

Source Code: [https://git.fd.io/vpp/tree/src/plugins/rdma](https://git.fd.io/vpp/tree/src/plugins/rdma) 
### vmxnet3 device driver
Maintainer: Steven Luong <sluong@cisco.com>  

vmxnet3 device driver support

- vmxnet3 device driver to connect to ESXi server, VMWare Fusion, and VMWare Workstation

Feature maturity level: production  
Supports: API CLI STATS MULTITHREAD  
Feature commits:
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace
  - [2985e0af6](https://git.fd.io/vpp/commit/?id=2985e0af6) vmxnet3: per interface gso support

Source Code: [https://git.fd.io/vpp/tree/src/plugins/vmxnet3](https://git.fd.io/vpp/tree/src/plugins/vmxnet3) 

