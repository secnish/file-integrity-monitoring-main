# Troubleshooting & Environment Adaptation

### 1. Bridged vs. NAT Networking
In a typical lab, "Bridged" mode is used[cite: 25]. However, due to the **Captive Portal** and **Dynamic IP rotation** of my hostel network, Bridged mode caused frequent connection drops.

**Solution:** I utilized **NAT** for the Ubuntu VM. This keeps the internal IP of the manager stable. 

### 2. Common "Stuck" Points
* **Manager IP Discovery:** If using NAT, ensure you use the IP assigned to the VM's NAT interface or set up Port Forwarding for ports 1514/1515.
* **Service Restarts:** Many users forget to restart the agent after changing `ossec.conf`. The agent will not pick up new FIM rules until the service is cycled.
* **Reference Material:** For visual learners, I highly recommend following the [official lab video](https://youtu.be/QT81wcuoRFY) alongside this documentation.