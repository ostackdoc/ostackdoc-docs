![](img/prepare-deployment-host.jpg)

In this section we are going to discuss how we are going to prepare OpenStack-Ansible host. This is the host that will hold the OpenStack-Ansible playbook Repository and deployment configurations.

Since this guide has been prepared using **Ubuntu Linux 18.04 LTS** operating systems you will not find the instructions on configuring other supported operating systems for OpenStack-Ansible. Please refer to the respective configurations manuals of those operating systems and adjust a particular configuration that suits your needs.

!!! Note
    When you install OpenStack in a production environment, we recommend using a separate deployment host that contains Ansible and orchestrates the OpenStack-Ansible (OSA) installation on the target hosts.

    In a test environment, we recommend using one of the infrastructure target hosts as the deployment host.

To use a target host as a deployment host, follow the steps in [Prepare the target hosts](/prepare-the-target-hosts/) on the deployment host.

# Configuring the Operating System

This section covers how to install and configure **Ubuntu 18.04 LTS Serer** in our OpenStack-Ansible host.

## Install the Operating System

If your have downloaded your Ubuntu server image download the installation ISO from alternate download section.

### Alternative Ubuntu Server installer

Since we  require advanced networking and storage features such as; LVM, RAID, multipath, vlans, bonds, or re-using existing partitions, you will want to continue to use the alternate installer.

[Download the alternate installer](http://cdimage.ubuntu.com/releases/18.04.2/release/ubuntu-18.04.2-server-amd64.iso)

!!! Note
    We do not cover on how to install the Ubuntu server here. We assume that you already know howto do it.

###  Configure The Network  Interfaces.

We assume that your OpenStack Ansible host has two network interface cards. We are planning our network like below

**1\.** Configure one network card for accessing the Internet
 Network:`192.168.10.0/24`

**2\.** Configure the other network card for accessing our OpenStack deployment management network.
Network: `172.29.236.0/24`
