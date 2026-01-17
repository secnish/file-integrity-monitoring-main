# Phase 2: Windows Agent Onboarding

[cite_start]The Wazuh agent runs on the endpoint to collect logs and system events[cite: 22].

### Step 1: Agent Registration (Manager Side)
[cite_start]Before installing the agent software, we must create a secure entry in the manager's database[cite: 59, 60].
1. [cite_start]Run the utility: `sudo /var/ossec/bin/manage_agents`[cite: 62].
2. [cite_start]Choose **A** to add an agent and provide a name (e.g., "Windows-Host")[cite: 63, 66].
3. [cite_start]Choose **E** to extract the key for this agent and copy the output[cite: 68, 69].

### Step 2: Installation and Key Application (Windows Side)
1. [cite_start]Download the MSI installer from the Wazuh documentation[cite: 56, 57].
2. [cite_start]Run the installer with default settings[cite: 58].
3. [cite_start]Open the **Wazuh Agent Manager** GUI[cite: 71].
4. [cite_start]Paste the authentication key and enter the Manager's IP address[cite: 72, 74].
5. [cite_start]**Important:** Restart the agent service to initiate the connection[cite: 74, 85].