# Phase 3: Real-Time File Integrity Monitoring (FIM)

Wazuh uses "Syscheck" to monitor for unauthorized file changes.

### Step 1: Modifying the Agent Configuration
To enable real-time tracking on a specific folder, we must edit the `ossec.conf` file on the Windows agent.
* **File Path:** `C:\Program Files (x86)\ossec-agent\ossec.conf` 
* Add the following XML block inside the `<syscheck>` section:
  `<directories realtime="yes">C:\Users\abc\Test</directories>` 

### Step 2: Verification Workflow
1. Restart the Wazuh agent service.
2. In the Wazuh Dashboard, navigate to **Agents** and ensure the status is **Active**.
3. Go to **Integrity Monitoring** and perform a file change (Create/Modify/Delete) in the `Test` folder.
4. Confirm the alert triggers in the dashboard.