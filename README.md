# PiLab
Raspberry Pi Home Lab
##Initial Set-Up

---

### What I Used:
- **Raspberry Pi 4 Model B** (4GB RAM)
- **Type 10 MicroSD card** (32GB)
- **Power supply**
- **HDMI cable, monitor, keyboard, and mouse**


---

### 1: Install Kali Linux

1. Downloaded the official **Kali ARM image** for Raspberry Pi:  
   🔗 [https://www.kali.org/get-kali/#kali-arm](https://www.kali.org/get-kali/#kali-arm)
2. Flashed the image to my SD card using **Balena Etcher**.
3. Inserted the SD card into the Raspberry Pi and booted.

**Default credentials** (changed on first boot):  
- Username: `kali`  
- Password: `kali`

---

### 2: Initial Steps
1. Change password:  
   ```bash
   passwd
   ```
2. Updated the apps:
   ```bash
   sudo apt update && sudo apt full-upgrade -y
   ```
3. Expand the filesystem:  
   ```bash
   sudo raspi-config
   ```
   → Advanced Options → Expand Filesystem → Reboot

---

### 3: Set Up Tools
Kali comes with many tools preinstalled, but I wanted more:
```bash
sudo apt install kali-linux-large
```
Or install individual tools like:
```bash
sudo apt install nmap wireshark metasploit-framework burpsuite john
```

---

### 4: Enable SSH for Remote Access
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```
You can now SSH into your Pi from another device.

---

### 5: Connect to Home Lab Network
- Use **Ethernet** for stability, or configure Wi-Fi in `/etc/wpa_supplicant/wpa_supplicant.conf`
- If you're using a second Wi-Fi adapter for attacks (like monitor mode), check its chipset compatibility.

---

### 6: Harden Your Pi
Since it’s a pentesting tool on your network, secure it:
- Change all default passwords
- Set up a firewall (`ufw` or `iptables`)
- Disable unnecessary services
- (Optional) Create a non-root user for daily use

---

### 🧰 Optional Extras:
- **PiJuice or battery pack** for portable ops
- **USB rubber ducky** for HID attacks
- **Install P4wnP1 A.L.O.A.** (for USB attack platform)
- **Set up VPN or Tor routing** for anonymized testing

---

Would you like to set up a specific type of tool (like Metasploit, Burp, or Wireshark), or are you building out a particular scenario (e.g., phishing, web app testing, etc.)?
