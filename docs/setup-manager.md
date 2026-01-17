# Phase 1: Wazuh Manager Installation (Ubuntu)

This guide covers the deployment of the Wazuh Central components (Manager, Indexer, and Dashboard) on an Ubuntu 20.04+ instance.

### Step 1: Repository Security
To ensure the integrity of the installation, we first add the official Wazuh GPG key.
* Open your terminal and run:
  `curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo gpg --dearmor -o /usr/share/keyrings/wazuh-archive-keyring.gpg` 

### Step 2: Automated Stack Deployment
Using the official Wazuh installation script handles the complex configuration of the Elastic stack components automatically.
* Execute the following command:
  `curl -s0 https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a -i` 
* **Note:** The `-a` flag installs all components, and `-i` allows for interactive mode.

### Step 3: Accessing the Dashboard
Once the script completes, it will provide a username and password. 
* Identify your VM IP using `ifconfig`.
* Access the UI at `https://<ubuntu-vm-ip>`.
* **Pro Tip:** You will likely see a browser security warning due to the self-signed certificate; click "Advanced" and "Proceed".