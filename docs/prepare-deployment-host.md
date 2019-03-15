![](img/prepare-deployment-host.jpg)

In this section we are going to discuss how we are going to prepare OpenStack-Ansible host. This is the host that will hold the OpenStack-Ansible playbook Repository and deployment configurations.

Since this guide has been prepared using **Ubuntu Linux 18.04 LTS** operating systems you will not find the instructions on configuring other supported operating systems for OpenStack-Ansible. Please refer to the respective configurations manuals of those operating systems and adjust a particular configuration that suits your needs.

!!! Note
    When you install OpenStack in a production environment, we recommend using a separate deployment host that contains Ansible and orchestrates the OpenStack-Ansible (OSA) installation on the target hosts.

    In a test environment, we recommend using one of the infrastructure target hosts as the deployment host.

To use a target host as a deployment host, follow the steps in [Prepare the target hosts](/prepare-the-target-hosts/) on the deployment host.
