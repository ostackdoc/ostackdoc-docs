This guide refers to the following types of hosts:

- **Deployment** host, which runs the Ansible playbooks
- **Target hosts**, where Ansible installs OpenStack services and infrastructure components

## Installation Workflow

The following diagram shows the general workflow of an OpenStack-Ansible installation. This may slightly change as per the specific deployment scenario.

![](img/deployment-work-flow.jpg)

## Installation Requirements and Recommendations

### Software Requirements

Ensure that all hosts within an OpenStack-Ansible (OSA) environment meet the following minimum requirements:

* Ubuntu
    - Ubuntu 16.04 LTS (Xenial Xerus) or Ubuntu 18.04 LTS (Bionic Beaver)
    - Linux kernel version 3.13.0-34-generic or later is required.

* CentOS
    - Centos 7, fully updated.
    - Linux kernel version 3.10.0 or later.

* openSUSE
    - Leap 42.X, fully updated.
    - Linux kernel version 4.4.X or later.

- Secure Shell (SSH) client and server that support public key authentication

- Network Time Protocol (NTP) client for time synchronization (such as ntpd or chronyd)

- Python 2.7.*x*

- en_US.UTF-8 as the locale

!!! Note
    At the moment of writing this guid, the openstacl-ansible playbook deployment on CentOS 7.x and openSUSE Leap 42.x is **experimental**. We highly recommend using Ubuntu in your production deployment.

### CPU Recommendation

* Compute hosts should have multicore processors with [hardware-assisted virtualization extensions](https://en.wikipedia.org/wiki/Hardware-assisted_virtualization). These extensions provide a significant performance boost and improve security in virtualized environments.

* Infrastructure (control plane) hosts should have multicore processors for best performance. Some services, such as MySQL, benefit from additional CPU cores and other technologies, such as [Hyper-threading](https://en.wikipedia.org/wiki/Hyper-threading).

### Storage and Disk Recommendations

Different hosts have different disk space requirements based on the services running on each host:

#### Deployment hosts

A minimum of **10 GB** of disk space is sufficient for holding the OpenStack-Ansible repository content and additional required software.

#### Compute hosts

Disk space requirements depend on the total number of instances running on each host and the amount of disk space allocated to each instance.

!!! Tip
    Consider disks that provide higher I/O throughput with lower latency, such as SSD drives in a RAID array if you use the local storage of the compute host for instance storage. 

!!! note
    If your deployment include a shared storage like Ceph you will  definitely be  using it in the compute host without using the local storage  of the compute host for instance storage. In this case the local disk of the compute host required for host OS installation and relevant OpenStack agent installation requirements.
