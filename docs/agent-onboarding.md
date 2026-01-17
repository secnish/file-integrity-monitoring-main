# Phase 2: Windows Agent Onboarding

The Wazuh agent runs on the endpoint to collect logs and system events.

### Step 1: Agent Registration (Manager Side)
Before installing the agent software, we must create a secure entry in the manager's database.
1. Run the utility: `sudo /var/ossec/bin/manage_agents`.
2. Choose **A** to add an agent and provide a name (e.g., "Windows-Host").
3. Choose **E** to extract the key for this agent and copy the output.

### Step 2: Installation and Key Application (Windows Side)
1. Download the MSI installer from the Wazuh documentation.
2. Run the installer with default settings.
3. Open the **Wazuh Agent Manager** GUI.
4. Paste the authentication key and enter the Manager's IP address.
5. **Important:** Restart the agent service to initiate the connection.