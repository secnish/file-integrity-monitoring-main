# Troubleshooting & Environment Adaptation

### 1. Bridged vs. NAT Networking
[cite_start]In a typical lab, "Bridged" mode is used[cite: 25]. However, due to the **Captive Portal** and **Dynamic IP rotation** of my hostel network, Bridged mode caused frequent connection drops.

**Solution:** I utilized **NAT** for the Ubuntu VM. This keeps the internal IP of the manager stable. 

### 2. Common "Stuck" Points
* [cite_start]**Manager IP Discovery:** If using NAT, ensure you use the IP assigned to the VM's NAT interface or set up Port Forwarding for ports 1514/1515[cite: 48, 51].
* **Service Restarts:** Many users forget to restart the agent after changing `ossec.conf`. [cite_start]The agent will not pick up new FIM rules until the service is cycled[cite: 85].
* [cite_start]**Reference Material:** For visual learners, I highly recommend following the [official lab video](https://youtu.be/QT81wcuoRFY) alongside this documentation[cite: 6, 20].