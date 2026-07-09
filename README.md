<img width="1920" height="922" alt="arp_spoofing" src="https://github.com/user-attachments/assets/187a968c-e40d-475e-ba59-61e8fdc3261f" /># Man-in-the-Middle (MitM) via ARP Spoofing

## 📖 Overview
This document provides a step-by-step walkthrough of setting up a Man-in-the-Middle (MitM) attack using ARP (Address Resolution Protocol) Spoofing. By poisoning the ARP cache of both the target machine and the network gateway, we position our attacking machine in the middle of their communications. This allows us to intercept, monitor, and potentially modify the traffic.

---

## ⚙️ Phase 1: Pre-Attack Setup

Before launching the attack, we must configure our attacking machine's network interfaces. This includes changing our MAC address for evasion/tracking purposes and enabling IP forwarding so we don't accidentally cause a Denial of Service (DoS) for the target.

### 1. MAC Address Spoofing
To obfuscate our hardware identity, we temporarily bring down the `eth0` network interface, change its MAC address to a custom value (`00:11:22:33:44:55`), and bring the interface back up.
bash
sudo ifconfig eth0 down
sudo ifconfig eth0 hw ether 00:11:22:33:44:55
sudo ifconfig eth0 up
<img width="1920" height="922" alt="arp_spoofing" src="https://github.com/user-attachments/assets/16231fa6-5c42-44be-b126-30d807870139" />
