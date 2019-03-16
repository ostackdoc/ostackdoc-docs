OpenStack-Ansible supports a number of different network architectures, and can be deployed using a single network interface for non-production workloads or using multiple network interfaces or bonded interfaces for production workloads.

Our OpenStack-Ansible production environment reference architectures in this guide segments traffic using VLANs across multiple network interfaces or bonds.

The default networks used in an OpenStack-Ansible in this deployment can be observed in the following table:


**Network**       |	**CIDR**          | **VLAN**
------------------|-------------------|-------------
Management Network|	`172.25.236.0/22` | `100`
Overlay Network 	| `172.25.240.0/22`	| `300`  
Storage Network	  | `172.29.244.0/22` |	`200`

!!! Note
    Unless, if we specifically do mention about a new network architecture  we will be referring to the same network architecture above through this document.

## Management Network

The `Management Network`, also referred to as the `Container network`, provides management of and communication between the infrastructure and OpenStack services running in containers or on metal. The management network uses a dedicated `VLAN` typically connected to the `br-mgmt` bridge, and may also be used as the primary interface used to interact with the server via `SSH`.
