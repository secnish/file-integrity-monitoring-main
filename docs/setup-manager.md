# Phase 1: Wazuh Manager Installation (Ubuntu)

[cite_start]This guide covers the deployment of the Wazuh Central components (Manager, Indexer, and Dashboard) on an Ubuntu 20.04+ instance[cite: 19, 29].

### Step 1: Repository Security
[cite_start]To ensure the integrity of the installation, we first add the official Wazuh GPG key[cite: 35, 38].
* Open your terminal and run:
  [cite_start]`curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo gpg --dearmor -o /usr/share/keyrings/wazuh-archive-keyring.gpg` [cite: 37]

### Step 2: Automated Stack Deployment
[cite_start]Using the official Wazuh installation script handles the complex configuration of the Elastic stack components automatically[cite: 45].
* Execute the following command:
  [cite_start]`curl -s0 https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a -i` [cite: 41]
* [cite_start]**Note:** The `-a` flag installs all components, and `-i` allows for interactive mode[cite: 43, 44].

### Step 3: Accessing the Dashboard
[cite_start]Once the script completes, it will provide a username and password[cite: 53]. 
* [cite_start]Identify your VM IP using `ifconfig`[cite: 48, 49].
* [cite_start]Access the UI at `https://<ubuntu-vm-ip>`[cite: 51].
* [cite_start]**Pro Tip:** You will likely see a browser security warning due to the self-signed certificate; click "Advanced" and "Proceed"[cite: 52].