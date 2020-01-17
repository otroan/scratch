# Releasenotes
## ACL Based Forwarding:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

### Bugfixes:
  - [bdde58534](https://git.fd.io/vpp/commit/?id=bdde58534) abf: use explicit types in api
  - [770a0deaa](https://git.fd.io/vpp/commit/?id=770a0deaa) tests: python3 use byte strings in raw()
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian

## ACLs for Security Groups:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

### Bugfixes:
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [692bfc85f](https://git.fd.io/vpp/commit/?id=692bfc85f) classify: API cleanup
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [b5076cbe1](https://git.fd.io/vpp/commit/?id=b5076cbe1) acl: add missing square brackets to vat_help option in acl api
  - [203bf04d4](https://git.fd.io/vpp/commit/?id=203bf04d4) acl: l2 classify test support python3
  - [2bb7151da](https://git.fd.io/vpp/commit/?id=2bb7151da) tests: python3 changes for span and aclplugin test
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian
  - [29ab3446c](https://git.fd.io/vpp/commit/?id=29ab3446c) acl: perform a sanity check of ACL rules before creating ACL
  - [c02924ec6](https://git.fd.io/vpp/commit/?id=c02924ec6) acl: fix stats-segment counters validation on acl update

## Address Resolution Protocol:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

## Adjacency:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [77cfc0171](https://git.fd.io/vpp/commit/?id=77cfc0171) fib: Adjacency creation notifications for dlegates

### Bugfixes:
  - [e7ee30092](https://git.fd.io/vpp/commit/?id=e7ee30092) fib: Adjacency walk fix for IPv6
  - [7391156ce](https://git.fd.io/vpp/commit/?id=7391156ce) fib: fix use-after-free for interface adj removal
  - [33af8c1ed](https://git.fd.io/vpp/commit/?id=33af8c1ed) fib: fix some typos in fib/mtrie
  - [138c37af5](https://git.fd.io/vpp/commit/?id=138c37af5) fib: do not dump no-longer valid adjacencies

## Bidirectional Forwarding Detection:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [845f51ffe](https://git.fd.io/vpp/commit/?id=845f51ffe) bfd: allow IPv6 link-local address as local address
  - [4682feb1f](https://git.fd.io/vpp/commit/?id=4682feb1f) bfd: API cleanup

## Bit Indexed Explicit Replication:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [f1f5a8a1a](https://git.fd.io/vpp/commit/?id=f1f5a8a1a) bier: API cleanup

## Bonding:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [aa7257863](https://git.fd.io/vpp/commit/?id=aa7257863) bonding: Add /if/lacp/<bond-sw_if_index>/<slave-sw_if_index>/partner-state
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [e83aa456b](https://git.fd.io/vpp/commit/?id=e83aa456b) bonding: add/del secondary mac address callback
  - [cc3aac056](https://git.fd.io/vpp/commit/?id=cc3aac056) bonding: fix interface deletion
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace
  - [a1876b84e](https://git.fd.io/vpp/commit/?id=a1876b84e) bonding: add weight support for active-backup mode
  - [0f09a828a](https://git.fd.io/vpp/commit/?id=0f09a828a) stats: add /if/<n>/<n>/state for lacp interface state

### Bugfixes:
  - [854eb6e3f](https://git.fd.io/vpp/commit/?id=854eb6e3f) bonding: process lacp when bond is admin down
  - [22e108d9a](https://git.fd.io/vpp/commit/?id=22e108d9a) bonding: fix feature.yaml error
  - [6dfd3785e](https://git.fd.io/vpp/commit/?id=6dfd3785e) bonding: drop traffic on backup interface for active-backup mode
  - [a03c7d5b9](https://git.fd.io/vpp/commit/?id=a03c7d5b9) bonding: fix non-null terminated vector
  - [002723c45](https://git.fd.io/vpp/commit/?id=002723c45) lacp: add actor steady state check prior to skip processing lacp pdu
  - [71e5b4710](https://git.fd.io/vpp/commit/?id=71e5b4710) bonding: graph node running after bond-input in feature arc may crash
  - [1a41a35b2](https://git.fd.io/vpp/commit/?id=1a41a35b2) bonding: feature arc may not be enabled for the slave interface
  - [de0302cab](https://git.fd.io/vpp/commit/?id=de0302cab) bonding: traffic traversing the wrong interface
  - [5c828bc1f](https://git.fd.io/vpp/commit/?id=5c828bc1f) bonding: fix non-null-terminated C-string
  - [3d1ef873d](https://git.fd.io/vpp/commit/?id=3d1ef873d) bonding: API cleanup
  - [bac326cb7](https://git.fd.io/vpp/commit/?id=bac326cb7) bonding lacp: deleting virtual interface which was enslaved may cause crash

## Buffer Metadata Change Tracker:
### New features:
  - [d318a996b](https://git.fd.io/vpp/commit/?id=d318a996b) dhcp: ipv6 prefix delegation improvements
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [d7b306657](https://git.fd.io/vpp/commit/?id=d7b306657) mdata: buffer metadata change tracker plugin

### Bugfixes:
  - [3c80c106a](https://git.fd.io/vpp/commit/?id=3c80c106a) build:  Fix typo introduced in src/plugins/mdata/FEATURE.yaml
  - [ea1a65135](https://git.fd.io/vpp/commit/?id=ea1a65135) docs: fix issues with src/scripts/fts.py

## Builtin URL support for the static http or https server:
### New features:
  - [71a5da0c8](https://git.fd.io/vpp/commit/?id=71a5da0c8) http_static: add .json content
  - [43765e2b4](https://git.fd.io/vpp/commit/?id=43765e2b4) builtinurl: initial working attempt

## Data-Plane Objects:
### Bugfixes:
  - [d6f1c9c51](https://git.fd.io/vpp/commit/?id=d6f1c9c51) mpls: support fragmentation of mpls output packet
  - [33af8c1ed](https://git.fd.io/vpp/commit/?id=33af8c1ed) fib: fix some typos in fib/mtrie

## Dynamic Host Configuration Protocol:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [d318a996b](https://git.fd.io/vpp/commit/?id=d318a996b) dhcp: ipv6 prefix delegation improvements
  - [02bfd641b](https://git.fd.io/vpp/commit/?id=02bfd641b) dhcp: Move to plugin

### Bugfixes:
  - [336bccdfe](https://git.fd.io/vpp/commit/?id=336bccdfe) dhcp: client use local logger
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [d3b8c861a](https://git.fd.io/vpp/commit/?id=d3b8c861a) nat: fix dhcp client on outside interface with output feature
  - [211b9f6ad](https://git.fd.io/vpp/commit/?id=211b9f6ad) dhcp: option 61 add missing type field
  - [20b962d3e](https://git.fd.io/vpp/commit/?id=20b962d3e) dhcp: fix dhcpv6 client and dhcpv6 prefix delegation
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [60ad1a59a](https://git.fd.io/vpp/commit/?id=60ad1a59a) dhcp: fix proxy dhcpv6 size check
  - [00217cb19](https://git.fd.io/vpp/commit/?id=00217cb19) dhcp: allocate memory for dns
  - [6bcc6a455](https://git.fd.io/vpp/commit/?id=6bcc6a455) dhcp: fix crash on unicast renewal send
  - [12966a7a0](https://git.fd.io/vpp/commit/?id=12966a7a0) dhcp: python3 support in tests
  - [d5262831a](https://git.fd.io/vpp/commit/?id=d5262831a) dhcp: dhcp6_pd_client_cp API cleanup
  - [b126ebcf4](https://git.fd.io/vpp/commit/?id=b126ebcf4) api: autogenerate event handler functions for *_test.c

## GPRS Tunneling Protocol:
### Bugfixes:
  - [623b4f85e](https://git.fd.io/vpp/commit/?id=623b4f85e) vxlan: reuse inner packet flow hash for tunnel outer header load balance
  - [75c723691](https://git.fd.io/vpp/commit/?id=75c723691) gtpu: Track the dst FIB entry instead of RR sourcing that
  - [5fb2278cb](https://git.fd.io/vpp/commit/?id=5fb2278cb) vxlan geneve gtpu: fix short help
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [55636cb62](https://git.fd.io/vpp/commit/?id=55636cb62) gtpu: use explicit types in api
  - [318fbfe89](https://git.fd.io/vpp/commit/?id=318fbfe89) gtpu: check packet has enough data for gtpu header
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [bd0a00a45](https://git.fd.io/vpp/commit/?id=bd0a00a45) gtpu: msg id fix in send_gtpu_tunnel_details api

## Generic Routing Encapsulation:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [5f8f61733](https://git.fd.io/vpp/commit/?id=5f8f61733) gre: Multi-point interfaces

### Bugfixes:
  - [2e839be97](https://git.fd.io/vpp/commit/?id=2e839be97) gre: fix feature.yaml error
  - [4c16d8006](https://git.fd.io/vpp/commit/?id=4c16d8006) gre: multipoint ingress lookup fix

## IP Neighbour Database:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

### Bugfixes:
  - [fca3c6a3a](https://git.fd.io/vpp/commit/?id=fca3c6a3a) ip-neighbor: set link-type ARP on incomplete adjacencies
  - [5002e7f26](https://git.fd.io/vpp/commit/?id=5002e7f26) ip-neighbor: ip_neighbor_advertise() handles null
  - [c301dc33f](https://git.fd.io/vpp/commit/?id=c301dc33f) ip-neighbor: fix API initialization call

## IP Security:
### New features:
  - [f62a8c013](https://git.fd.io/vpp/commit/?id=f62a8c013) ipsec: bind an SA to a worker
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9534696b4](https://git.fd.io/vpp/commit/?id=9534696b4) ipip: Tunnel flags controlling copying data to/from payload/encap
  - [12989b538](https://git.fd.io/vpp/commit/?id=12989b538) ipsec: remove dedicated IPSec tunnels
  - [01d61e788](https://git.fd.io/vpp/commit/?id=01d61e788) ipsec: add insecure option for format of SA
  - [b325983a4](https://git.fd.io/vpp/commit/?id=b325983a4) ipsec: support 4o6 and 6o4 for tunnel protect
  - [670027a50](https://git.fd.io/vpp/commit/?id=670027a50) ipsec: Add 'detail' option to 'sh ipsec sa'

### Bugfixes:
  - [f3a6622c7](https://git.fd.io/vpp/commit/?id=f3a6622c7) ipsec: AH copy destination and source address from template
  - [02950406c](https://git.fd.io/vpp/commit/?id=02950406c) ipsec: Targeted unit testing
  - [4a56f4e48](https://git.fd.io/vpp/commit/?id=4a56f4e48) ipsec: Test and fix IPSec worker hand-off
  - [568acbb7c](https://git.fd.io/vpp/commit/?id=568acbb7c) ipsec: Fix decap of IPSEC/GRE in transport mode
  - [8dc75c0cc](https://git.fd.io/vpp/commit/?id=8dc75c0cc) ipsec: Init salt value in SA creation CLI (so it's not random)
  - [4505f0154](https://git.fd.io/vpp/commit/?id=4505f0154) ipsec: make sure pad_bytes does not exceed pad data size
  - [dbf68c9aa](https://git.fd.io/vpp/commit/?id=dbf68c9aa) ipsec: Changes to make ipsec encoder/decoders reusable by the plugins
  - [8cdb1a0a6](https://git.fd.io/vpp/commit/?id=8cdb1a0a6) ipsec: fix trailing data overflow
  - [a548d134a](https://git.fd.io/vpp/commit/?id=a548d134a) ipsec: Honour the renumber argument when selecting show instnace
  - [d14fccd6d](https://git.fd.io/vpp/commit/?id=d14fccd6d) ipsec: Coverity warnings
  - [f7f49640b](https://git.fd.io/vpp/commit/?id=f7f49640b) ipsec: ipsec-input: check for too-short packets
  - [c520fe7ab](https://git.fd.io/vpp/commit/?id=c520fe7ab) ipsec: fix esp trace seq number overflow
  - [c41217ab8](https://git.fd.io/vpp/commit/?id=c41217ab8) ikev2: fix GCM cipher
  - [89b249500](https://git.fd.io/vpp/commit/?id=89b249500) ipsec: fix tunnel protection removal
  - [8133c780a](https://git.fd.io/vpp/commit/?id=8133c780a) ipsec: fix use-after-free
  - [769145cdb](https://git.fd.io/vpp/commit/?id=769145cdb) ip: respect buffer boundary when searching for ipv6 headers
  - [d770cfc96](https://git.fd.io/vpp/commit/?id=d770cfc96) ipsec ip tcp l2: multiarch nodes cannot be declared as static
  - [2cdcd0cf4](https://git.fd.io/vpp/commit/?id=2cdcd0cf4) ipsec: Fix NULL encryption algorithm

## IP in IP tunnelling:
### New features:
  - [9534696b4](https://git.fd.io/vpp/commit/?id=9534696b4) ipip: Tunnel flags controlling copying data to/from payload/encap
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

### Bugfixes:
  - [4c6b1b6da](https://git.fd.io/vpp/commit/?id=4c6b1b6da) ikev2: fix crash during SA rekey
  - [3d93ad9f3](https://git.fd.io/vpp/commit/?id=3d93ad9f3) ipip: fix typos in short_help

## IPFIX probe:
### New features:
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

### Bugfixes:
  - [3013e6988](https://git.fd.io/vpp/commit/?id=3013e6988) flowprobe: use explicit types in api
  - [770a0deaa](https://git.fd.io/vpp/commit/?id=770a0deaa) tests: python3 use byte strings in raw()
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [2f71a8889](https://git.fd.io/vpp/commit/?id=2f71a8889) ip: ipfix-export API update
  - [b0d83f188](https://git.fd.io/vpp/commit/?id=b0d83f188) flowprobe: tests support python3

## IPSec crypto engine provided by Intel IPSecMB library:
### New features:
  - [76a36e83e](https://git.fd.io/vpp/commit/?id=76a36e83e) crypto-ipsecmb: improve gcm performance using dedicated API.

### Bugfixes:
  - [561be280f](https://git.fd.io/vpp/commit/?id=561be280f) crypto: add '-maes' compile switch

## IPSec crypto engine provided by native implementation:
### New features:
  - [9fb6d40eb](https://git.fd.io/vpp/commit/?id=9fb6d40eb) misc: add address sanitizer heap instrumentation

### Bugfixes:
  - [561be280f](https://git.fd.io/vpp/commit/?id=561be280f) crypto: add '-maes' compile switch

## IPv6 Neighbor Discovery:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

## Internet Group Management Protocol:
### Bugfixes:
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [4a7fc4cf1](https://git.fd.io/vpp/commit/?id=4a7fc4cf1) igmp: use explicit types in api
  - [770a0deaa](https://git.fd.io/vpp/commit/?id=770a0deaa) tests: python3 use byte strings in raw()
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian

## L2TPv3:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [3ae526271](https://git.fd.io/vpp/commit/?id=3ae526271) l2: l2tp API cleanup

## Layer 2 Forwarding:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9fb6d40eb](https://git.fd.io/vpp/commit/?id=9fb6d40eb) misc: add address sanitizer heap instrumentation
  - [830493392](https://git.fd.io/vpp/commit/?id=830493392) classify: use vector code even when data is not aligned

### Bugfixes:
  - [b2e73b1dc](https://git.fd.io/vpp/commit/?id=b2e73b1dc) l2: fix MAC learn counter update on adding MAC entry
  - [3be9351e5](https://git.fd.io/vpp/commit/?id=3be9351e5) l2: l2_patch_main should not be static
  - [70ef0faea](https://git.fd.io/vpp/commit/?id=70ef0faea) l2: fix l2input_feat_names overflow
  - [9485d99bd](https://git.fd.io/vpp/commit/?id=9485d99bd) interface: Allow VLAN tag-rewrite on non-sub-interfaces too.
  - [d770cfc96](https://git.fd.io/vpp/commit/?id=d770cfc96) ipsec ip tcp l2: multiarch nodes cannot be declared as static

## Layer 3 cross connect:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors

### Bugfixes:
  - [60f5108a9](https://git.fd.io/vpp/commit/?id=60f5108a9) l3xc: use explicit types in api
  - [770a0deaa](https://git.fd.io/vpp/commit/?id=770a0deaa) tests: python3 use byte strings in raw()
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian

## Link Aggregation Control Protocol:
### New features:
  - [aa7257863](https://git.fd.io/vpp/commit/?id=aa7257863) bonding: Add /if/lacp/<bond-sw_if_index>/<slave-sw_if_index>/partner-state
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [ebef4a9e5](https://git.fd.io/vpp/commit/?id=ebef4a9e5) lacp: use explit api types
  - [3f2d5718b](https://git.fd.io/vpp/commit/?id=3f2d5718b) lacp: fix control_ping from plugins
  - [002723c45](https://git.fd.io/vpp/commit/?id=002723c45) lacp: add actor steady state check prior to skip processing lacp pdu
  - [977c1dec6](https://git.fd.io/vpp/commit/?id=977c1dec6) lacp: continuing input packet trace from device driver
  - [cda35b38d](https://git.fd.io/vpp/commit/?id=cda35b38d) lacp: mark is_mp_safe for show and dump binary API
  - [bac326cb7](https://git.fd.io/vpp/commit/?id=bac326cb7) bonding lacp: deleting virtual interface which was enslaved may cause crash

## Link Layer Discovery Protocol:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [5ad541eea](https://git.fd.io/vpp/commit/?id=5ad541eea) interface: Remove residual dpdk bonding code

## Load Balancer:
### New features:
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour
  - [33538a150](https://git.fd.io/vpp/commit/?id=33538a150) lb: add APIs for set interface nat4 and nat6

### Bugfixes:
  - [e69f47143](https://git.fd.io/vpp/commit/?id=e69f47143) lb: lb_add_del_vip and lb_add_del_as doesn't work.
  - [ec44e2637](https://git.fd.io/vpp/commit/?id=ec44e2637) tests: python3 changes for load balancer test
  - [6eb009ac0](https://git.fd.io/vpp/commit/?id=6eb009ac0) lb: vl_api_lb_conf_t_handler has to ntohl
  - [75761b933](https://git.fd.io/vpp/commit/?id=75761b933) api: split vl_api_prefix into two
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian

## Locator ID Separation Protocol Control Plane:
### New features:
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [11b40e7ea](https://git.fd.io/vpp/commit/?id=11b40e7ea) lisp: fix dangling references to bihash tables

## Locator ID Separation Protocol Generic Protocol Extension:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [0c4def0e8](https://git.fd.io/vpp/commit/?id=0c4def0e8) lisp: fix lisp-gpe db hash

## Mapping of Address and Port:
### New features:
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [ff47fb645](https://git.fd.io/vpp/commit/?id=ff47fb645) vppapigen map: raise ValueError when fieldname is python keyword

### Bugfixes:
  - [87663cdf6](https://git.fd.io/vpp/commit/?id=87663cdf6) map: fix ip4-map-t DF behavior
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [be31c2a25](https://git.fd.io/vpp/commit/?id=be31c2a25) map: use explicit types in api
  - [9f3569615](https://git.fd.io/vpp/commit/?id=9f3569615) map: fix MAP-T ip6 port check
  - [3aae3dc7a](https://git.fd.io/vpp/commit/?id=3aae3dc7a) map: Fix a coverity MAP dead-code issue.
  - [4a6d093e7](https://git.fd.io/vpp/commit/?id=4a6d093e7) map: Avoid null dereference in 'map show' and 'map del'
  - [acaa04a22](https://git.fd.io/vpp/commit/?id=acaa04a22) map: Fix inverted 'map security check enable' CLI flag.
  - [360b523b5](https://git.fd.io/vpp/commit/?id=360b523b5) map: fix coverity issue 205684
  - [b15ad9512](https://git.fd.io/vpp/commit/?id=b15ad9512) map: Fix TCP MSS clamping for MAP-E traffic.
  - [eb284a1f8](https://git.fd.io/vpp/commit/?id=eb284a1f8) ip: functional interface to ip fragmentation
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [9e160f82b](https://git.fd.io/vpp/commit/?id=9e160f82b) map: python3 support in tests
  - [d6d50cebd](https://git.fd.io/vpp/commit/?id=d6d50cebd) map: fix DF[Don't fragment] ip4-map-t behaviour
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian
  - [3c7c613cf](https://git.fd.io/vpp/commit/?id=3c7c613cf) map: fix non-null-terminated C-string
  - [e5ff5a36d](https://git.fd.io/vpp/commit/?id=e5ff5a36d) api: enforce vla is last and fixed string type

## Multi-Protocol Label Switching:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9db6ada77](https://git.fd.io/vpp/commit/?id=9db6ada77) fib: Table Replace

### Bugfixes:
  - [3eb8f207b](https://git.fd.io/vpp/commit/?id=3eb8f207b) mpls: api cleanup
  - [eb284a1f8](https://git.fd.io/vpp/commit/?id=eb284a1f8) ip: functional interface to ip fragmentation
  - [bf103d99e](https://git.fd.io/vpp/commit/?id=bf103d99e) mpls: number of mpls tunnel paths returns zero
  - [d6f1c9c51](https://git.fd.io/vpp/commit/?id=d6f1c9c51) mpls: support fragmentation of mpls output packet
  - [75761b933](https://git.fd.io/vpp/commit/?id=75761b933) api: split vl_api_prefix into two

## NSH:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [d3f0a4869](https://git.fd.io/vpp/commit/?id=d3f0a4869) nsh: use explicit api types

## Netmap Device:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace

## Network Address Translation:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour
  - [9db6ada77](https://git.fd.io/vpp/commit/?id=9db6ada77) fib: Table Replace
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [22bb417e9](https://git.fd.io/vpp/commit/?id=22bb417e9) nat: handoff traffic matching for dynamic NAT

### Bugfixes:
  - [e6eaa24f1](https://git.fd.io/vpp/commit/?id=e6eaa24f1) nat: session cleanup fix
  - [d3b8c861a](https://git.fd.io/vpp/commit/?id=d3b8c861a) nat: fix dhcp client on outside interface with output feature
  - [9a6dc8a93](https://git.fd.io/vpp/commit/?id=9a6dc8a93) nat: respect arc features (multi worker)
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [5854b43de](https://git.fd.io/vpp/commit/?id=5854b43de) nat: NAT udp counter & unit test fixes
  - [16572355c](https://git.fd.io/vpp/commit/?id=16572355c) nat: respect udp checksum
  - [8f6d7a787](https://git.fd.io/vpp/commit/?id=8f6d7a787) nat: revert respect udp checksum
  - [a519f213f](https://git.fd.io/vpp/commit/?id=a519f213f) nat: revert fix dual-loop tcp checksum botch
  - [9654a37fa](https://git.fd.io/vpp/commit/?id=9654a37fa) nat: fix dual-loop tcp checksum botch
  - [0d75f7836](https://git.fd.io/vpp/commit/?id=0d75f7836) nat: respect udp checksum
  - [2f71a8889](https://git.fd.io/vpp/commit/?id=2f71a8889) ip: ipfix-export API update
  - [b8d5e4058](https://git.fd.io/vpp/commit/?id=b8d5e4058) nat: tests support python3
  - [7233846ce](https://git.fd.io/vpp/commit/?id=7233846ce) nat: fix use-after-free
  - [6c57a4a98](https://git.fd.io/vpp/commit/?id=6c57a4a98) nat: fix update of outside fibs (output-feature)
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian
  - [5c2f96436](https://git.fd.io/vpp/commit/?id=5c2f96436) misc: fix shebang with missing env
  - [e5ff5a36d](https://git.fd.io/vpp/commit/?id=e5ff5a36d) api: enforce vla is last and fixed string type

## Network Delay Simulator:
### Bugfixes:
  - [e06e7c672](https://git.fd.io/vpp/commit/?id=e06e7c672) nsim: use explicit api types

## PPPoE:
### New features:
  - [f50bac1bb](https://git.fd.io/vpp/commit/?id=f50bac1bb) vppinfra: bihash walk cb typedef and continue/stop controls
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour

### Bugfixes:
  - [04338e85a](https://git.fd.io/vpp/commit/?id=04338e85a) pppoe: use explicit types in api
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line

## Pipe Device:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

### Bugfixes:
  - [df40cb5b5](https://git.fd.io/vpp/commit/?id=df40cb5b5) devices: pipe API cleanup
  - [33af8c1ed](https://git.fd.io/vpp/commit/?id=33af8c1ed) fib: fix some typos in fib/mtrie

## QUIC Protocol:
### New features:
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

### Bugfixes:
  - [7abab3036](https://git.fd.io/vpp/commit/?id=7abab3036) quic: call quic_send_packets only once per ctx
  - [95cd86438](https://git.fd.io/vpp/commit/?id=95cd86438) session: fix listener global endpoint lookup
  - [cfffeae1e](https://git.fd.io/vpp/commit/?id=cfffeae1e) quic: fix accept failure
  - [d9942bcc6](https://git.fd.io/vpp/commit/?id=d9942bcc6) quic: Hotfix crypto context on migrate
  - [038c7e662](https://git.fd.io/vpp/commit/?id=038c7e662) quic: Use per thread next_cid
  - [05d7312eb](https://git.fd.io/vpp/commit/?id=05d7312eb) quic: removing quicly_send call from quic_accept_connection
  - [c9cb8f6d9](https://git.fd.io/vpp/commit/?id=c9cb8f6d9) quic: fix stream tx_fifo race condition
  - [d9577b4aa](https://git.fd.io/vpp/commit/?id=d9577b4aa) quic: clean accept/connect error codepath
  - [65f6cfcdb](https://git.fd.io/vpp/commit/?id=65f6cfcdb) quic: fix import typo
  - [7bd1fd776](https://git.fd.io/vpp/commit/?id=7bd1fd776) quic: Remove qctx opening pool
  - [0b6c9c485](https://git.fd.io/vpp/commit/?id=0b6c9c485) quic: Increase logging
  - [331c428a9](https://git.fd.io/vpp/commit/?id=331c428a9) quic: handle duplicate packet from quicly
  - [7f39e91fe](https://git.fd.io/vpp/commit/?id=7f39e91fe) quic: free qctx after udp cleanup
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [34d92ebde](https://git.fd.io/vpp/commit/?id=34d92ebde) quic: remove redundant function calls
  - [f9d784b6b](https://git.fd.io/vpp/commit/?id=f9d784b6b) quic: fifo size is u32
  - [ea7d4fe14](https://git.fd.io/vpp/commit/?id=ea7d4fe14) quic: fix wrong error checking
  - [3ad984732](https://git.fd.io/vpp/commit/?id=3ad984732) quic: disable failing test
  - [7c7fa9066](https://git.fd.io/vpp/commit/?id=7c7fa9066) quic: fix quicly fifo size mismatch
  - [74dcbf97a](https://git.fd.io/vpp/commit/?id=74dcbf97a) quic: Add PICOTLS_INCLUDE_DIR var to CMakeLists.
  - [ff5a9b6ec](https://git.fd.io/vpp/commit/?id=ff5a9b6ec) hsa: fix vpp_echo session close
  - [caa7acf5c](https://git.fd.io/vpp/commit/?id=caa7acf5c) session: add is_migrating flag
  - [cc702410c](https://git.fd.io/vpp/commit/?id=cc702410c) quic: fix wrong condition in update_fifo_size
  - [6d6456ab4](https://git.fd.io/vpp/commit/?id=6d6456ab4) quic: fix use-after-free
  - [b840c773d](https://git.fd.io/vpp/commit/?id=b840c773d) quic: fix non-null terminated hostname string
  - [ffbfe3a2d](https://git.fd.io/vpp/commit/?id=ffbfe3a2d) quic: fix server opening stream immediately
  - [baf1c7ccc](https://git.fd.io/vpp/commit/?id=baf1c7ccc) quic: disable quic plugin by default
  - [1682b51c4](https://git.fd.io/vpp/commit/?id=1682b51c4) quic: fix rx_callback refactoring
  - [243e1933b](https://git.fd.io/vpp/commit/?id=243e1933b) quic: handle session migration notifications

## Quality of Service:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [4b76c58be](https://git.fd.io/vpp/commit/?id=4b76c58be) qos: api clenup

## SRv6 - Service Chaining Dynamic Proxy:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile

### Bugfixes:
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line

## SRv6 - Service Chaining Masquerading Proxy:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile

### Bugfixes:
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line

## SRv6 - Service Chaining Static Proxy:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile
  - [eeb5fb3a5](https://git.fd.io/vpp/commit/?id=eeb5fb3a5) sr: add "set sr encaps hop-limit" command

### Bugfixes:
  - [5d4b8912d](https://git.fd.io/vpp/commit/?id=5d4b8912d) tests: changes for scapy 2.4.3 migration
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line

## SRv6 Mobuile:
### New features:
  - [57584d99d](https://git.fd.io/vpp/commit/?id=57584d99d) srv6-mobile:
  - [70d8ef89a](https://git.fd.io/vpp/commit/?id=70d8ef89a) srv6-mobile
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile

### Bugfixes:
  - [61f7bfb6d](https://git.fd.io/vpp/commit/?id=61f7bfb6d) srv6-mobile: Revert "srv6-mobile:"
  - [77022b88e](https://git.fd.io/vpp/commit/?id=77022b88e) srv6-mobile
  - [ce7fd674c](https://git.fd.io/vpp/commit/?id=ce7fd674c) srv6-mobile
  - [fa6b556f1](https://git.fd.io/vpp/commit/?id=fa6b556f1) misc: fix 4 coverity warnings in srv6-mobile
  - [9df54b778](https://git.fd.io/vpp/commit/?id=9df54b778) srv6-mobile: fix yamllint failure in FEATURE.yaml

## Segment Routing for IPv6 (SRv6):
### New features:
  - [57584d99d](https://git.fd.io/vpp/commit/?id=57584d99d) srv6-mobile:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [70d8ef89a](https://git.fd.io/vpp/commit/?id=70d8ef89a) srv6-mobile
  - [1b81e6ef6](https://git.fd.io/vpp/commit/?id=1b81e6ef6) srv6-mobile
  - [eeb5fb3a5](https://git.fd.io/vpp/commit/?id=eeb5fb3a5) sr: add "set sr encaps hop-limit" command

### Bugfixes:
  - [13e6fce7c](https://git.fd.io/vpp/commit/?id=13e6fce7c) sr: some fixes for SRv6 CLI/API
  - [61f7bfb6d](https://git.fd.io/vpp/commit/?id=61f7bfb6d) srv6-mobile: Revert "srv6-mobile:"
  - [a6b93eac5](https://git.fd.io/vpp/commit/?id=a6b93eac5) sr: fix deleting an SR l2 steering policy
  - [769145cdb](https://git.fd.io/vpp/commit/?id=769145cdb) ip: respect buffer boundary when searching for ipv6 headers
  - [1096b46d9](https://git.fd.io/vpp/commit/?id=1096b46d9) sr: fix sr_set_encap_source reply

## Segment Routing for MPLS:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

## Session Layer:
### New features:
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

### Bugfixes:
  - [87b0c8929](https://git.fd.io/vpp/commit/?id=87b0c8929) session: remove io event dispatch dbg msg
  - [95cd86438](https://git.fd.io/vpp/commit/?id=95cd86438) session: fix listener global endpoint lookup
  - [f1910326d](https://git.fd.io/vpp/commit/?id=f1910326d) session: close for reset replies independent of state
  - [901467ed7](https://git.fd.io/vpp/commit/?id=901467ed7) session: fix session_main_get_worker_if_valid
  - [3bbbf0dbd](https://git.fd.io/vpp/commit/?id=3bbbf0dbd) session: fix transport proto unformat
  - [989bc47d6](https://git.fd.io/vpp/commit/?id=989bc47d6) session: Fix out of order mq
  - [e140d5d02](https://git.fd.io/vpp/commit/?id=e140d5d02) session: extra checks in session validation
  - [31bd03562](https://git.fd.io/vpp/commit/?id=31bd03562) session: session enable in multiworker
  - [aa43914df](https://git.fd.io/vpp/commit/?id=aa43914df) session: re-set tx fifo event if out of buffers
  - [9d3e1b433](https://git.fd.io/vpp/commit/?id=9d3e1b433) session: fix app attach on error
  - [2d0b2bbb9](https://git.fd.io/vpp/commit/?id=2d0b2bbb9) session: fix show cli with closed session
  - [45b7973dd](https://git.fd.io/vpp/commit/?id=45b7973dd) session: avoid double dispatch of new events
  - [ba13c3b36](https://git.fd.io/vpp/commit/?id=ba13c3b36) session: fix dispatch event logging
  - [cbbc4a255](https://git.fd.io/vpp/commit/?id=cbbc4a255) tls: fix on tcp connection reset
  - [5afea129e](https://git.fd.io/vpp/commit/?id=5afea129e) session: allow transport cleanup only if not deleted
  - [98bd35808](https://git.fd.io/vpp/commit/?id=98bd35808) tls: enable tls engine as the default engine
  - [e24a4bc02](https://git.fd.io/vpp/commit/?id=e24a4bc02) session: increase max ctrl msg size
  - [94d2da0b2](https://git.fd.io/vpp/commit/?id=94d2da0b2) session: fix use-after-free
  - [7fbdb6aa5](https://git.fd.io/vpp/commit/?id=7fbdb6aa5) session: fix typos & cert_key store init
  - [2a1118411](https://git.fd.io/vpp/commit/?id=2a1118411) session: avoid old io dispatch if no slots left to send
  - [caa7acf5c](https://git.fd.io/vpp/commit/?id=caa7acf5c) session: add is_migrating flag
  - [d4aeb84c3](https://git.fd.io/vpp/commit/?id=d4aeb84c3) session: fix use-after-free
  - [b5a2f7056](https://git.fd.io/vpp/commit/?id=b5a2f7056) session: allow transport cleanup in any state
  - [19e52c96d](https://git.fd.io/vpp/commit/?id=19e52c96d) session: Fix missing elt regrab
  - [35174b428](https://git.fd.io/vpp/commit/?id=35174b428) session: fix io_evt mq locking
  - [e1e7fb88e](https://git.fd.io/vpp/commit/?id=e1e7fb88e) session: validate connection in session lookup del
  - [54c93cfc2](https://git.fd.io/vpp/commit/?id=54c93cfc2) session: fix cleanup in closing states
  - [cac31a4a2](https://git.fd.io/vpp/commit/?id=cac31a4a2) session: avoid transport cleanup if previously deleted
  - [1afa7afff](https://git.fd.io/vpp/commit/?id=1afa7afff) session: fix msg freeing on error
  - [27eeb87f4](https://git.fd.io/vpp/commit/?id=27eeb87f4) session: avoid bihash list for session tables
  - [e5ff5a36d](https://git.fd.io/vpp/commit/?id=e5ff5a36d) api: enforce vla is last and fixed string type
  - [5c89fbf28](https://git.fd.io/vpp/commit/?id=5c89fbf28) session: move svm_fifo_clear_deq_ntf to before calling the app callback
  - [fcd5e12b1](https://git.fd.io/vpp/commit/?id=fcd5e12b1) session : make sure session layer is enabled when cli operate the sessions.
  - [73cad33b5](https://git.fd.io/vpp/commit/?id=73cad33b5) svm: fix fifo hdr freelist allocation
  - [b33923349](https://git.fd.io/vpp/commit/?id=b33923349) udp: fix connections move

## Source VRF Select:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [3bab8f9c5](https://git.fd.io/vpp/commit/?id=3bab8f9c5) fib: Decouple source from priority and behaviour

### Bugfixes:
  - [5e913f374](https://git.fd.io/vpp/commit/?id=5e913f374) svs: use explicit types in api
  - [770a0deaa](https://git.fd.io/vpp/commit/?id=770a0deaa) tests: python3 use byte strings in raw()
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [33a58171e](https://git.fd.io/vpp/commit/?id=33a58171e) api: autogenerate api trace print/endian

## Static http https server:
### New features:
  - [e0fd9ed11](https://git.fd.io/vpp/commit/?id=e0fd9ed11) http_static: add "http static cache clear" CLI
  - [5554c56a6](https://git.fd.io/vpp/commit/?id=5554c56a6) http_static: add dynamic GET / POST method hooks

### Bugfixes:
  - [b10105889](https://git.fd.io/vpp/commit/?id=b10105889) http_static: fifo-size is u32
  - [e5ff5a36d](https://git.fd.io/vpp/commit/?id=e5ff5a36d) api: enforce vla is last and fixed string type
  - [3705980a2](https://git.fd.io/vpp/commit/?id=3705980a2) http_static: fix session expiration timer bugs

## Tap Device:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [7c6102b1a](https://git.fd.io/vpp/commit/?id=7c6102b1a) tap: multiqueue support
  - [39807d02c](https://git.fd.io/vpp/commit/?id=39807d02c) tap: add check for vhost-net backend
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle

### Bugfixes:
  - [5de4fb707](https://git.fd.io/vpp/commit/?id=5de4fb707) devices: tap API cleanup
  - [0d3d4824a](https://git.fd.io/vpp/commit/?id=0d3d4824a) tap: fix coverity warning 205875
  - [44d06916b](https://git.fd.io/vpp/commit/?id=44d06916b) tap: Move client registration check to top
  - [0ba86cb1b](https://git.fd.io/vpp/commit/?id=0ba86cb1b) tap: fix cli parser
  - [a069762e8](https://git.fd.io/vpp/commit/?id=a069762e8) tap: revert clean-up when linux will delete the tap interface
  - [ba0da570f](https://git.fd.io/vpp/commit/?id=ba0da570f) tap: fix tap interface not working on Arm issue

## Time-range-based MAC-address filter:
### New features:
  - [cbe25aab3](https://git.fd.io/vpp/commit/?id=cbe25aab3) ip: Protocol Independent IP Neighbors
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [ef3c11ca9](https://git.fd.io/vpp/commit/?id=ef3c11ca9) mactime: add the "mactime.json" builtin URL
  - [5932ce17e](https://git.fd.io/vpp/commit/?id=5932ce17e) tests: add cli_return_response to vpp_papi_provider
  - [2c41a61d5](https://git.fd.io/vpp/commit/?id=2c41a61d5) mactime: add a "top" command to watch device stats

### Bugfixes:
  - [7b22df06f](https://git.fd.io/vpp/commit/?id=7b22df06f) mactime: update api to use explicit types
  - [ead1e536d](https://git.fd.io/vpp/commit/?id=ead1e536d) misc: Fix python scripts shebang line
  - [55cc4c4f0](https://git.fd.io/vpp/commit/?id=55cc4c4f0) mactime: fix handle_get_mactime fcn prototype
  - [78fae1346](https://git.fd.io/vpp/commit/?id=78fae1346) mactime: pass context in reply to mactime_dump
  - [18cd91c61](https://git.fd.io/vpp/commit/?id=18cd91c61) mactime: fix undefined symbol in mactime_test
  - [bb688a4dc](https://git.fd.io/vpp/commit/?id=bb688a4dc) mactime: remove unnecessary function declaration

## Transmission Control Protocol:
### New features:
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

### Bugfixes:
  - [56cef059e](https://git.fd.io/vpp/commit/?id=56cef059e) tcp: fix rxt delivered without sacks
  - [de7fcacb3](https://git.fd.io/vpp/commit/?id=de7fcacb3) tcp: fix listen node coverity warning
  - [79bfb9e09](https://git.fd.io/vpp/commit/?id=79bfb9e09) tcp: fix tcp check tx offload issue
  - [c95eefb39](https://git.fd.io/vpp/commit/?id=c95eefb39) tcp: handle ack advancement with no holes and reneging
  - [a6696719c](https://git.fd.io/vpp/commit/?id=a6696719c) tcp: fix persist assert
  - [edf1da94d](https://git.fd.io/vpp/commit/?id=edf1da94d) tcp: fix scoreboard assert
  - [479f7fec6](https://git.fd.io/vpp/commit/?id=479f7fec6) tcp: fix last sacked with no holes
  - [067f8f963](https://git.fd.io/vpp/commit/?id=067f8f963) tcp: fix duplicate sack whith reneging
  - [2f04cb9f1](https://git.fd.io/vpp/commit/?id=2f04cb9f1) tcp: fix rate samples for old acks
  - [956819afa](https://git.fd.io/vpp/commit/?id=956819afa) tcp: api clenup
  - [b7f035ff4](https://git.fd.io/vpp/commit/?id=b7f035ff4) tcp: validate port reuse
  - [1de7167e7](https://git.fd.io/vpp/commit/?id=1de7167e7) tcp: accept sack reneging as a cc event
  - [3eba7f157](https://git.fd.io/vpp/commit/?id=3eba7f157) tcp: fix tail rescue with sacks
  - [599db9e9d](https://git.fd.io/vpp/commit/?id=599db9e9d) tcp: honor cc pacing rate when resetting pacer
  - [b72a0ff73](https://git.fd.io/vpp/commit/?id=b72a0ff73) tcp: invalidate expired timer handles before dispatching
  - [52be67435](https://git.fd.io/vpp/commit/?id=52be67435) tcp: close session on retransmit failure
  - [fd4c3fe36](https://git.fd.io/vpp/commit/?id=fd4c3fe36) tcp: avoid retransmits post reset
  - [07df79150](https://git.fd.io/vpp/commit/?id=07df79150) tcp: fix ip check in lookup validation
  - [bf1f8b7f2](https://git.fd.io/vpp/commit/?id=bf1f8b7f2) tcp: fix retransmit with no sacks
  - [3ea17d54a](https://git.fd.io/vpp/commit/?id=3ea17d54a) tcp: correct validity check return value
  - [db39656d7](https://git.fd.io/vpp/commit/?id=db39656d7) tcp: rx fifo size is u32
  - [c8be85116](https://git.fd.io/vpp/commit/?id=c8be85116) tcp: correct tcp connection lookup condition
  - [d6ae4bf13](https://git.fd.io/vpp/commit/?id=d6ae4bf13) tcp: improve rate samples for retansmitted segments
  - [81cb8e409](https://git.fd.io/vpp/commit/?id=81cb8e409) tcp: fix sack retransmit beyond snd_nxt
  - [cb711a4ec](https://git.fd.io/vpp/commit/?id=cb711a4ec) tcp: avoid sending acks when data available
  - [c30318da2](https://git.fd.io/vpp/commit/?id=c30318da2) tcp: Init cwnd from ssthresh.
  - [a9e1f7b99](https://git.fd.io/vpp/commit/?id=a9e1f7b99) tcp: fix mss flag in option parsing
  - [8a8b05c52](https://git.fd.io/vpp/commit/?id=8a8b05c52) tcp: avoid head retransmit if scoreboard has no holes
  - [8a047ed74](https://git.fd.io/vpp/commit/?id=8a047ed74) tcp: fix tso not work in single buffer issue
  - [dd60b1b12](https://git.fd.io/vpp/commit/?id=dd60b1b12) tcp: rate sample for persist segments
  - [d4aeb84c3](https://git.fd.io/vpp/commit/?id=d4aeb84c3) session: fix use-after-free
  - [54c93cfc2](https://git.fd.io/vpp/commit/?id=54c93cfc2) session: fix cleanup in closing states
  - [1df833e6d](https://git.fd.io/vpp/commit/?id=1df833e6d) tcp: fix unformat cwnd multiplier
  - [321cfa5fc](https://git.fd.io/vpp/commit/?id=321cfa5fc) tcp: cleanup scoreboard after recovery
  - [d770cfc96](https://git.fd.io/vpp/commit/?id=d770cfc96) ipsec ip tcp l2: multiarch nodes cannot be declared as static
  - [4e1fcf490](https://git.fd.io/vpp/commit/?id=4e1fcf490) tcp: fix rx min/max fifo size parsing
  - [cedcf608f](https://git.fd.io/vpp/commit/?id=cedcf608f) tcp: improve mss computation
  - [92f190a80](https://git.fd.io/vpp/commit/?id=92f190a80) tcp: fix byte tracker samples flush
  - [d25d364d2](https://git.fd.io/vpp/commit/?id=d25d364d2) tcp: fix cc algo name parsing
  - [79c04d622](https://git.fd.io/vpp/commit/?id=79c04d622) tcp: handle fin+rst+syn in closing state

## Transport Layer Security:
### New features:
  - [0d74dd1f8](https://git.fd.io/vpp/commit/?id=0d74dd1f8) tls: improve connection formating
  - [79f89537c](https://git.fd.io/vpp/commit/?id=79f89537c) session: Add certificate store

### Bugfixes:
  - [95cd86438](https://git.fd.io/vpp/commit/?id=95cd86438) session: fix listener global endpoint lookup
  - [e140d5d02](https://git.fd.io/vpp/commit/?id=e140d5d02) session: extra checks in session validation
  - [b1a81aa67](https://git.fd.io/vpp/commit/?id=b1a81aa67) tls: fifo size is u32
  - [cbbc4a255](https://git.fd.io/vpp/commit/?id=cbbc4a255) tls: fix on tcp connection reset
  - [6faac1622](https://git.fd.io/vpp/commit/?id=6faac1622) tls: allow disconnects from main thread

## User Datagram Protocol:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [ff2fad170](https://git.fd.io/vpp/commit/?id=ff2fad170) udp: fix ipv6 listen port registration
  - [95cd86438](https://git.fd.io/vpp/commit/?id=95cd86438) session: fix listener global endpoint lookup
  - [d4aeb84c3](https://git.fd.io/vpp/commit/?id=d4aeb84c3) session: fix use-after-free
  - [8fadb658a](https://git.fd.io/vpp/commit/?id=8fadb658a) udp: do not send received packets to error-drop
  - [b33923349](https://git.fd.io/vpp/commit/?id=b33923349) udp: fix connections move

## VNET GSO:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [72e7312af](https://git.fd.io/vpp/commit/?id=72e7312af) gso: add protocol header parser

### Bugfixes:
  - [a420c5e6c](https://git.fd.io/vpp/commit/?id=a420c5e6c) gso: fix typo in the quad-loop
  - [222b709ad](https://git.fd.io/vpp/commit/?id=222b709ad) gso: fix number of buffers required for segmentation
  - [70ae4efaa](https://git.fd.io/vpp/commit/?id=70ae4efaa) gso: minor fixes to gso segmentation
  - [94afc9391](https://git.fd.io/vpp/commit/?id=94afc9391) gso: fix buffers trace

## VPP Comms Library:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [9fb6d40eb](https://git.fd.io/vpp/commit/?id=9fb6d40eb) misc: add address sanitizer heap instrumentation
  - [d747c3c36](https://git.fd.io/vpp/commit/?id=d747c3c36) vcl: add config option for preferred tls engine
  - [ef7cbf6ad](https://git.fd.io/vpp/commit/?id=ef7cbf6ad) vcl: add api to set lcl ip
  - [57c88938f](https://git.fd.io/vpp/commit/?id=57c88938f) vcl: allow non-blocking connects

### Bugfixes:
  - [6e3c1f8ec](https://git.fd.io/vpp/commit/?id=6e3c1f8ec) vcl: add rx event on epoll ctl if needed
  - [9f3f18f99](https://git.fd.io/vpp/commit/?id=9f3f18f99) vcl: hold errno when calling LDBG
  - [475c9d7bc](https://git.fd.io/vpp/commit/?id=475c9d7bc) vcl: EPOLLOUT should be generated when epoll_ctl called with EPOLLOUT event
  - [da8f218f7](https://git.fd.io/vpp/commit/?id=da8f218f7) vcl: fix multi-thread app segment attaching
  - [96453fd24](https://git.fd.io/vpp/commit/?id=96453fd24) vcl: RX event may lost when accept session repeatedly
  - [64cf459bc](https://git.fd.io/vpp/commit/?id=64cf459bc) vcl: fix disconnect from binary api
  - [d4c709222](https://git.fd.io/vpp/commit/?id=d4c709222) vcl: separate binary api connections per thread worker
  - [b2955355c](https://git.fd.io/vpp/commit/?id=b2955355c) vcl: resolve VCL part session cleanup issue
  - [f0797d130](https://git.fd.io/vpp/commit/?id=f0797d130) build: fix make test with distributed src
  - [ff31ac680](https://git.fd.io/vpp/commit/?id=ff31ac680) vcl: if the ldp user send buf with 0 len, it will assert failed.
  - [e16707b5b](https://git.fd.io/vpp/commit/?id=e16707b5b) vcl: Handle newer Glibc (>2.28) where fcntl is actually fcntl64
  - [592a909a3](https://git.fd.io/vpp/commit/?id=592a909a3) vcl: fix nonblocking accept with >1 event in the queue
  - [f1653e62f](https://git.fd.io/vpp/commit/?id=f1653e62f) vcl: fix epoll connected events sid
  - [bd52e46fe](https://git.fd.io/vpp/commit/?id=bd52e46fe) vcl: handle rx notifications on reused sessions
  - [dbc9c599b](https://git.fd.io/vpp/commit/?id=dbc9c599b) vcl: handle segment map errors
  - [22ba3303d](https://git.fd.io/vpp/commit/?id=22ba3303d) vcl: initialize ctrl_mq in workers
  - [747b3d8b0](https://git.fd.io/vpp/commit/?id=747b3d8b0) vcl: fix ldp_set_app_name overflow

## Virtio PCI Device:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [72e7312af](https://git.fd.io/vpp/commit/?id=72e7312af) gso: add protocol header parser
  - [7c6102b1a](https://git.fd.io/vpp/commit/?id=7c6102b1a) tap: multiqueue support
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace

### Bugfixes:
  - [affc5f6d3](https://git.fd.io/vpp/commit/?id=affc5f6d3) virtio: fix ip4 checksum offload
  - [2c504f89c](https://git.fd.io/vpp/commit/?id=2c504f89c) devices: virtio API cleanup
  - [15d7fd0fe](https://git.fd.io/vpp/commit/?id=15d7fd0fe) virtio: fix checksum offload support
  - [edf3b4b04](https://git.fd.io/vpp/commit/?id=edf3b4b04) virtio: fix the tx queue thread binding
  - [5d4c99f27](https://git.fd.io/vpp/commit/?id=5d4c99f27) devices: vhost API cleanup
  - [157a4ab40](https://git.fd.io/vpp/commit/?id=157a4ab40) gso: fix the tap/virtio driver for header offset
  - [8f011830b](https://git.fd.io/vpp/commit/?id=8f011830b) virtio: fix use-after-free
  - [06c194d91](https://git.fd.io/vpp/commit/?id=06c194d91) virtio: feature arc have higher priority than redirect
  - [7331005c1](https://git.fd.io/vpp/commit/?id=7331005c1) devices: vhoost cpu->copy array overflow on tcp jumbo frame (65535 bytes)
  - [4442f7cb2](https://git.fd.io/vpp/commit/?id=4442f7cb2) devices: vhost not reading packets from vring
  - [a069762e8](https://git.fd.io/vpp/commit/?id=a069762e8) tap: revert clean-up when linux will delete the tap interface
  - [efa119db3](https://git.fd.io/vpp/commit/?id=efa119db3) tap: interface rx counter not increment correct
  - [a75ad8764](https://git.fd.io/vpp/commit/?id=a75ad8764) devices: skip checksum calculation if guest supports checksum offload
  - [14bea1bb6](https://git.fd.io/vpp/commit/?id=14bea1bb6) gso: fix l3 and l4 header offset in case of tagged interface
  - [5cd987dda](https://git.fd.io/vpp/commit/?id=5cd987dda) devices: vhost-user crashes displaying show trace for deleted interface
  - [7dfcf7f1f](https://git.fd.io/vpp/commit/?id=7dfcf7f1f) gso: remove the ip checksum flag in case of ipv6

## Virtual eXtensible LAN:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [623b4f85e](https://git.fd.io/vpp/commit/?id=623b4f85e) vxlan: reuse inner packet flow hash for tunnel outer header load balance
  - [5fb2278cb](https://git.fd.io/vpp/commit/?id=5fb2278cb) vxlan geneve gtpu: fix short help
  - [1ec9fdbf2](https://git.fd.io/vpp/commit/?id=1ec9fdbf2) vxlan: fix vxlan hw offload issue

## VxLAN-GPE:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process

### Bugfixes:
  - [5fb2278cb](https://git.fd.io/vpp/commit/?id=5fb2278cb) vxlan geneve gtpu: fix short help

## host-interface Device AF_PACKET:
### New features:
  - [39d69112f](https://git.fd.io/vpp/commit/?id=39d69112f) api: multiple connections per process
  - [6b0dd5502](https://git.fd.io/vpp/commit/?id=6b0dd5502) build: add yaml file linting to make checkstyle
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace

### Bugfixes:
  - [3b2db9002](https://git.fd.io/vpp/commit/?id=3b2db9002) devices: af_packet API cleanup
  - [90b34ed67](https://git.fd.io/vpp/commit/?id=90b34ed67) devices: fix issue of per_interface_next_index

## rdma device driver:
### New features:
  - [d8c1ef925](https://git.fd.io/vpp/commit/?id=d8c1ef925) rdma: api: prepare support for direct verb
  - [812afe712](https://git.fd.io/vpp/commit/?id=812afe712) rdma: add rdma API
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace
  - [0dcafcc50](https://git.fd.io/vpp/commit/?id=0dcafcc50) rdma: add support for MAC changes
  - [74eba446b](https://git.fd.io/vpp/commit/?id=74eba446b) rdma: add support for input feature arcs

### Bugfixes:
  - [b644eb54f](https://git.fd.io/vpp/commit/?id=b644eb54f) rdma: add explicit types in api
  - [972d71da8](https://git.fd.io/vpp/commit/?id=972d71da8) rdma: fix next node rx redirect
  - [a50892e15](https://git.fd.io/vpp/commit/?id=a50892e15) rdma: fix name auto-generation on create
  - [386ebb6e2](https://git.fd.io/vpp/commit/?id=386ebb6e2) rdma: build: fix ibverb compilation test
  - [0dd97d473](https://git.fd.io/vpp/commit/?id=0dd97d473) rdma: fix crash when failing to read pci addr on create
  - [90ea5dc1b](https://git.fd.io/vpp/commit/?id=90ea5dc1b) rdma: fix crash when failing to detect numa node on create
  - [df213385d](https://git.fd.io/vpp/commit/?id=df213385d) rdma: prevent loopback of broadcast packets
  - [4a98388da](https://git.fd.io/vpp/commit/?id=4a98388da) rdma: make sure pci subsystem is initialized
  - [7ff07354c](https://git.fd.io/vpp/commit/?id=7ff07354c) rdma: fix non-NULL terminated C-string overflow
  - [1ec093fe7](https://git.fd.io/vpp/commit/?id=1ec093fe7) rdma: fix pending packets check on tx

## vmxnet3 device driver:
### New features:
  - [7ca5aaac1](https://git.fd.io/vpp/commit/?id=7ca5aaac1) vlib: add flag to explicitelly mark nodes which can init per-node packet trace
  - [2985e0af6](https://git.fd.io/vpp/commit/?id=2985e0af6) vmxnet3: per interface gso support

### Bugfixes:
  - [277f03f06](https://git.fd.io/vpp/commit/?id=277f03f06) vmxnet3: use explicit types in api
  - [4354317bf](https://git.fd.io/vpp/commit/?id=4354317bf) vlib: only dump 1st buffer in chain by default
  - [ddf625d60](https://git.fd.io/vpp/commit/?id=ddf625d60) vmxnet3: interface rx counter not increment correctly


