OpenStack-Ansible supports a number of different network architectures, and can be deployed using a single network interface for non-production workloads or using multiple network interfaces or bonded interfaces for production workloads.

Our OpenStack-Ansible production environment reference architectures in this guide segments traffic using VLANs across multiple network interfaces or bonds.

The default networks used in an OpenStack-Ansible in this deployment can be observed in the following table:


**Network**       |	**`CIDR`**        | **`VLAN`**
------------------|-------------------|-------------
Management Network|	`172.25.236.0/22` | `100`
Overlay Network 	| `172.25.240.0/22`	| `300`  
Storage Network	  | `172.29.244.0/22` |	`200`
