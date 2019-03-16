OpenStack-Ansible supports a number of different network architectures, and can be deployed using a single network interface for non-production workloads or using multiple network interfaces or bonded interfaces for production workloads.

Our OpenStack-Ansible production environment reference architectures in this guide segments traffic using VLANs across multiple network interfaces or bonds.

The default networks used in an OpenStack-Ansible in this deployment can be observed in the following table:


**Network**       |	**CIDR**          | **VLAN**
------------------|-------------------|-------------
Management Network|	`172.25.236.0/22` | `100`
Overlay Network 	| `172.25.240.0/22`	| `300`  
Storage Network	  | `172.29.244.0/22` |	`200`

!!! Note
    Unless, if we specifically do mention about a new network architecture  we will be referring to the same network architecture above through out this document.

## Management Network

The `Management Network`, also referred to as the `Container network`, provides management of and communication between the infrastructure and OpenStack services running in containers or on metal. The management network uses a dedicated `VLAN` typically connected to the `br-mgmt` bridge, and may also be used as the primary interface used to interact with the server via `SSH`.

## Overlay Network

The `Overlay Network`, also referred to as the `Tunnel Network`, provides connectivity between hosts for the purpose of `tunneling` encapsulated traffic using `VXLAN`, `GRE`, or other protocols. The `Overlay Network` uses a dedicated `VLAN` typically connected to the `br-vxlan` bridge.

## Storage Network

The `Storage Network` provides segregated access to Block Storage from OpenStack services such as `Cinder, Glance, Ceph`, etc.. The `Storage Network` uses a dedicated `VLAN` typically connected to the `br-storage` bridge.

!!! Note
    The `CIDRs` and `VLANs` listed for each network are examples and may be different in your environment.

Additional `VLANs` may be required for the following purposes:

  * External provider networks for `Floating IPs` and instances
  * Self-service `Project/Tenant` networks for instances
  * Other OpenStack services

## Network Interfaces

### Single Interface or Bond

OpenStack-Ansible supports the use of a `single` interface or set of `bonded` interfaces that carry `traffic` for OpenStack services as well as instances.

The following diagram demonstrates hosts using a single interface:

![](img/single-interface.jpg)
