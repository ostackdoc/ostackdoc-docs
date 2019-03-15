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
