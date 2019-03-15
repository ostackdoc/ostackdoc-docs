Here is an example test environment for a working OpenStack-Ansible (OSA) deployment with a small number of servers.

This example environment has the following characteristics:

- One infrastructure node for the **control plane** host (32 vCPU, 128 GB RAM, 2 TB RAID1 HDD)
- One compute node (32 vCPU, 128 GB RAM, 2 TB RAID1 HDD)
- One Storage node (2 vCPU,  64 GB RAM, 2 TB RAID1 HDD).
- Two Network Interface Card (NIC) for each host on a bond setup as `bond0`
- Internet access via the router address `192.168.10.1` on the Management Network

The following figure depicts this test environment and its components.

![](img/openstack-test-env-v1.jpg)
