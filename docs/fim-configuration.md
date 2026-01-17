# Phase 3: Real-Time File Integrity Monitoring (FIM)

[cite_start]Wazuh uses "Syscheck" to monitor for unauthorized file changes[cite: 77].

### Step 1: Modifying the Agent Configuration
[cite_start]To enable real-time tracking on a specific folder, we must edit the `ossec.conf` file on the Windows agent[cite: 78].
* [cite_start]**File Path:** `C:\Program Files (x86)\ossec-agent\ossec.conf` [cite: 80]
* Add the following XML block inside the `<syscheck>` section:
  [cite_start]`<directories realtime="yes">C:\Users\abc\Test</directories>` [cite: 81, 82, 83]

### Step 2: Verification Workflow
1. [cite_start]Restart the Wazuh agent service[cite: 84, 85].
2. [cite_start]In the Wazuh Dashboard, navigate to **Agents** and ensure the status is **Active**[cite: 88, 89].
3. [cite_start]Go to **Integrity Monitoring** and perform a file change (Create/Modify/Delete) in the `Test` folder[cite: 90, 91].
4. [cite_start]Confirm the alert triggers in the dashboard[cite: 92].