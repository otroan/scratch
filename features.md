# IPFIX probe
Maintainer: Ole Troan <ot@cisco.com>  
State: production

IPFIX flow probe. Works in the L2, or IP input feature path.

- L2 input feature
- IPv4 / IPv6 input feature
- Recording of L2, L3 and L4 information

## Missing
- Output path
- Export over IPv6
- Export over TCP/SCTP

# Mapping of Address and Port (MAP)
Maintainer: Ole Troan <ot@cisco.com>  
State: production

IPv4 as a service mechanisms. Tunnel or translate an IPv4 address, an IPv4 subnet or a shared IPv4 address. In shared IPv4 address mode, only UDP, TCP and restricted ICMP is supported.

- LW46 BR (RFC7596)
  - Fragmentation and Reassembly
- MAP-E BR (RFC7597)
- MAP-T BR (RFC7599)

# IP in IP tunnelling
Maintainer: Ole Troan <ot@cisco.com>  
State: production

Implements IP{v4,v6} over IP{v4,v6} tunnelling as described in RFC2473. This module also implement the border relay of 6RD (RFC5969).

- IPv4/IPv6 over IPv4/IPv6 encapsulation
  - Fragmentation and Reassembly
  - Configurable MTU
  - Inner to outer Traffic Class / TOS copy
  - Configurable Traffic Class / TOS
- ICMPv4 / ICMPv6 proxying
- 6RD (RFC5969)
  - Border Relay

## Missing
- Tunnel PMTUD
- Tracking of FIB state for tunnel state
- IPv6 extension headers (Tunnel encapsulation limit option)

