# OpenEBL Services Deployment Repository

Welcome to the OpenEBL Services Deployment Repository! This repository contains Ansible playbooks and configurations to deploy OpenEBL services on your servers.

## Prerequisites

Before getting started, please ensure you have the following prerequisites:

- IP addresses of your servers
    - Suggest to use Ubuntu 22.04.3 LTS or above
- Several servers (physical machines, VMs, or cloud instances) ready for deployment.
- SSH access to each server with appropriate SSH credentials (username, SSH private key file).


## Deployment Steps

To deploy OpenEBL services on your servers, follow these steps:

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/openebl/openebl-deployment.git
    ```

2. Navigate to the ansible directory under the cloned repository directory:

    ```bash
    cd openebl-deployment/ansible
    ```

3. Copy the example inventory file (`inventory_example.yaml`) as `inventory.yml` and update with the IP addresses and SSH credentials of your servers. Ensure that you have separate groups for different types of servers (e.g., web servers, database servers).

4. Review and customize the Ansible playbooks and configurations based on your deployment requirements. You can find the variables setting in the `group_vars/` and `host_vars` directories.

    - group_vars: the variables in each file will be applied to all hosts defined in the group, the file name is the group name.
    - host_vars: the variables in each file will be applied to the host aligned to the file name.

5. Run the Ansible playbooks to deploy OpenEBL services:

    ```bash
    cd openebl-deployment/ansible
    ansible-playbook -i inventory/inventory.yml playbook.yml
    ```

    You can replace `inventory.yml` with the path to your self-defined inventory files with different filenames if you have different sets of allocations to execute the deployment playbook.

6. Monitor the deployment process for any errors or issues.

## Contributing

If you encounter any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.
