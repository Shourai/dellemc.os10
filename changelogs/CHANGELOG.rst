======================================================================
Ansible Network Collection for Dell EMC SmartFabric OS10 Release Notes
======================================================================

.. contents:: Topics

v1.2.3
======

Bugfixes
--------

- Fixed issue in os10.py for show tech-support command fail in version from 2.10 to 2.15(https://github.com/ansible-collections/dellemc.os10/issues/152)


v1.2.2
======

Bugfixes
--------

- Fixed issue in os10_command and os10_config modules to breaks prompt/answer (https://github.com/ansible-collections/dellemc.os10/issues/149)


v1.2.1
======

Release Summary
---------------

This is the minor release of the ``dellemc.os10`` collection.
This changelog contains all changes to the modules in this collection
that have been added after the release of ``dellemc.os10`` 1.2.0.

Bugfixes
--------

- Fixed issue in os10_interface fails on vlan and loopback interfaces due to no negotiation (https://github.com/ansible-collections/dellemc.os10/issues/133)
- Fixed issue in Replace bool auto_neg with 4-option negotiation (https://github.com/ansible-collections/dellemc.os10/pull/134)
- Fixed issue in parsing error when trying to add more than 55 or more character in hostname (https://github.com/ansible-collections/dellemc.os10/issues/145)


v1.2.0
======

Release Summary
---------------

This is the minor release of the ``dellemc.os10`` collection.
This changelog contains all changes to the modules in this collection
that have been added after the release of ``dellemc.os10`` 1.1.0.

Minor Changes
-------------

- Add support for configuring negotiation settings on an interface (https://github.com/ansible-collections/dellemc.os10/pull/77)
- Add support for setting FEC on interfaces (https://github.com/ansible-collections/dellemc.os10/issues/92).
- Adding support to configure interface speed in os10_interface role (https://github.com/ansible-collections/dellemc.os10/pull/62)
- Adding support to configure username sshkey os10_users role (https://github.com/ansible-collections/dellemc.os10/pull/7)
- os10_lag - Add support for vlt-port-channel option (https://github.com/ansible-collections/dellemc.os10/pull/108).
- os10_system role - Add support for ``hardware l3 ipv6-extended-prefix`` (https://github.com/ansible-collections/dellemc.os10/pull/45).

Bugfixes
--------

- Fixed issue in os10_vrf role when mapping multiple interfaces in the vrf (https://github.com/ansible-collections/dellemc.os10/issues/81)
- Fixed issue in removing interface ip vrf forwarding (https://github.com/ansible-collections/dellemc.os10/issues/67)
- Fixed issue in removing interface ipv6 address with state absent (https://github.com/ansible-collections/dellemc.os10/issues/60)

v1.1.1
======

Minor Changes
-------------

- Adding support for Ansible version 2.9 (https://github.com/ansible-collections/dellemc.os10/pull/58)

v1.1.0
======

Major Changes
-------------

- os10_bgp - Enhanced router bgp keyword support for non-default vrf which are supported for default vrf and additional keyword to support both default and non-default vrf
- os10_snmp role - Added support for snmp V3 features in community, group, host, engineID

Minor Changes
-------------

- Enhanced os10_bgp role to support internal BGP redistribution under address-family for V4 and V6
- Enhanced os10_bgp role to support maximum-prefix configuration under BGP peer and peer-group.
- os10_ntp role - Added support for vrf and sha1 and sha2-256 authentication-key types
- os10_snmp role - Added support for source-interface and vrf
- os10_template - add template for show spanning tree compatibility mode
- os10_template - add template for show vlt error disabled ports
- os10_uplink role - Added support for downstream disable-links and auto-recover

Breaking Changes / Porting Guide
--------------------------------

- os10_bgp - Changed "subnet"  key as list format instead of dictionary format under "listen" key to support multiple neighbor prefix for listen command
- os10_bgp - Changed "vrf" key as list format instead of dictionary format to supprot multiple VRF in router BGP and changed the "vrf" key name to "vrfs"

Bugfixes
--------

- Fixed issue in using interface range in os10_vlan members. (https://github.com/ansible-collections/dellemc.os10/issues/53)

v1.0.2
======

Bugfixes
--------

- Fix issue in using ip_and_mask along with members in os10_vlan role (https://github.com/ansible-collections/dellemc.os10/issues/42)
- Fix issue in using list of strings for `commands` argument for `os10_command` module (https://github.com/ansible-collections/dellemc.os10/issues/43)
- Fixed os10_vlan role idempotency issue with description and members (https://github.com/ansible-collections/dellemc.os10/issues/46)

v1.0.1
======

Release Summary
---------------

Added changelog.

v1.0.0
======

Major Changes
-------------

- New role os10_aaa - Facilitates the configuration of Authentication Authorization and Accounting (AAA), TACACS and RADIUS server.
- New role os10_acl - Facilitates the configuration of Access Control lists.
- New role os10_bfd - Facilitates the configuration of BFD global attributes.
- New role os10_bgp - Facilitates the configuration of border gateway protocol (BGP) attributes.
- New role os10_copy_config - This role pushes the backup running configuration into a OS10 device.
- New role os10_dns - Facilitates the configuration of domain name service (DNS).
- New role os10_ecmp - Facilitates the configuration of equal cost multi-path (ECMP) for IPv4.
- New role os10_fabric_summary Facilitates to get show system information of all the OS10 switches in the fabric.
- New role os10_flow_monitor Facilitates the configuration of ACL flow-based monitoring attributes.
- New role os10_image_upgrade Facilitates installation of OS10 software images.
- New role os10_interface Facilitates the configuration of interface attributes.
- New role os10_lag Facilitates the configuration of link aggregation group (LAG) attributes.
- New role os10_lldp Facilitates the configuration of link layer discovery protocol (LLDP) attributes at global and interface level.
- New role os10_logging Facilitates the configuration of global logging attributes and logging servers.
- New role os10_network_validation Facilitates validation of wiring connection, BGP neighbors, MTU between neighbors and VLT pair.
- New role os10_ntp Facilitates the configuration of network time protocol (NTP) attributes.
- New role os10_prefix_list Facilitates the configuration of IP prefix-list.
- New role os10_qos Facilitates the configuration of quality of service attributes including policy-map and class-map.
- New role os10_raguard Facilitates the configuration of IPv6 RA Guard attributes.
- New role os10_route_map Facilitates the configuration of route-map attributes.
- New role os10_snmp Facilitates the configuration of  global SNMP attributes.
- New role os10_system Facilitates the configuration of hostname and hashing algorithm.
- New role os10_template The role takes the raw string input from the CLI of OS10 device, and returns a structured text in the form of a Python dictionary.
- New role os10_uplink Facilitates the configuration of uplink attributes like uplink-state group.
- New role os10_users Facilitates the configuration of global system user attributes.
- New role os10_vlan Facilitates the configuration of virtual LAN (VLAN) attributes.
- New role os10_vlt Facilitates the configuration of virtual link trunking (VLT).
- New role os10_vrf Facilitates the configuration of virtual routing and forwarding (VRF).
- New role os10_vrrp Facilitates the configuration of virtual router redundancy protocol (VRRP) attributes.
- New role os10_vxlan Facilitates the configuration of virtual extensible LAN (VXLAN) attributes.
- New role os10_xstp Facilitates the configuration of xSTP attributes.

New Plugins
-----------

Cliconf
~~~~~~~

- os10 - Use OS10 cliconf to run commands on Dell EMC PowerSwitch devices.

New Modules
-----------

- os10_command - Run commands on devices running Dell EMC SmartFabric OS1O.
- os10_config - Manage configuration on devices running OS10.
- os10_facts - Collect facts from devices running OS10.
