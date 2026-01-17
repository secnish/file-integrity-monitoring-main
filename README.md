## SIEM & File Integrity Monitoring (FIM) Lab with Wazuh

<img width="1732" height="1048" alt="image" src="https://github.com/user-attachments/assets/36a2239c-5a60-496b-8c7d-bc709f958667" />


## 1. Project Summary

This project demonstrates the deployment of an enterprise-grade Open-Source SIEM (Wazuh) to monitor a Windows endpoint in real-time. The primary objective was to move beyond "passive logging" by configuring **File Integrity Monitoring (FIM)** to detect unauthorized changes in critical directories, simulating a defense against ransomware or unauthorized data exfiltration.

## 2. Technical Architecture

The lab environment utilizes a client-server architecture to simulate a real-world enterprise network.

**Manager:** Wazuh Manager hosted on **Ubuntu Server** (VirtualBox).


**Endpoint:** Windows host machine running the **Wazuh Agent**.


**Networking:** Configured with a **Bridged Adapter** to ensure seamless telemetry flow between the virtualized manager and the physical host.



## 3. Implementation Phases

### Phase 1: Manager Deployment

The Wazuh manager was deployed on Ubuntu using an automated installation script to ensure all components (Indexer, Dashboard, and Server) were correctly integrated.

**Key Command:** `sudo bash ./wazuh-install.sh -a -i` 


**Verification:** Accessed the web dashboard via the Ubuntu VM’s internal IP.



### Phase 2: Agent Onboarding & Secure Authentication

Security was maintained during onboarding by generating unique RSA keys on the manager before registering the Windows endpoint.

**Tool Used:** `/var/ossec/bin/manage_agents` 


**Result:** Established a secure, encrypted heartbeat between the Windows host and the SIEM.



### Phase 3: Advanced FIM Configuration

To demonstrate tactical depth, I configured **Real-Time File Integrity Monitoring** by modifying the `ossec.conf` file on the Windows agent.

**Monitored Path:** `C:\Users\abc\Test` 


**Logic:** Enabled `realtime="yes"` to ensure that any file creation, modification, or deletion triggers an immediate alert in the SOC dashboard.



## 4. Investigative Results (The "So What?")

Once the lab was live, I performed a simulated "Malicious File Modification" test.

1. **Action:** Created and deleted files within the monitored `Test` directory.
2. **Observation:** The Wazuh Dashboard successfully ingested the event and categorized it under the **Integrity Monitoring** module.
3. **Insight:** This visibility is critical for detecting **Defense Evasion** (T1562) or **Data Destruction** (T1485) techniques within the MITRE ATT&CK framework.

## 5. Challenges & Troubleshooting

**Connectivity:** Encountered initial issues with Agent-Manager communication. Resolved by ensuring VirtualBox was set to **Bridged Mode**, allowing the VM to reside on the same subnet as the host.


**Permissions:** Ensuring administrative access on the Windows host was required to modify the `ossec.conf` and restart the agent service.



---

## 6. How to Use This Repo

1. Review the `Wazuh-Guide.pdf` for step-by-step installation instructions .


2. Check the `/configs` folder (to be added) for my custom `ossec.conf` snippets.
