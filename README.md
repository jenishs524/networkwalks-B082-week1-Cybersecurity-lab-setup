<div align="center">

# 🔐 Personal Cybersecurity Lab Setup

**Building an isolated virtual lab for cybersecurity, penetration testing, and ethical hacking practice**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/VirtualBox-7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Virtualization-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This project focuses on setting up a **virtual cybersecurity and penetration-testing laboratory** using Oracle VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, networking, reconnaissance, vulnerability assessment, and security-testing activities can be practiced safely.

The lab uses a private virtual network so additional target machines can be added later.

---

## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private **NAT Network**.
- Configure network connectivity for Kali Linux.
- Assign an IP address to the Kali VM.
- Verify network connectivity.
- Create a clean VM snapshot.
- Document the complete lab setup.

---

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Ethical hacking practice
- Security-tool experimentation

⚠️ **Important:** Use this laboratory only on systems that you own or have explicit permission to test.

---

## 🏗️ Lab Architecture

```text
                HOST COMPUTER
                      │
                Oracle VirtualBox
                      │
                ┌─────▼─────┐
                │ NAT Network│
                │10.0.0.0/24│
                └─────┬─────┘
                      │
                ┌─────▼─────┐
                │    Kali   │
                │   Linux   │
                │ 10.0.0.2  │
                └───────────┘
```

Additional target machines can be connected to the same virtual network in future projects.

---

## ⚙️ Lab Configuration

| 🧩 Component ⚙️ Configuration | |
|---|---|
| 🖥️ Host OS | Kali Linux |
| 🧠 Host RAM | 7.7 GiB |
| ⚡ Processor | Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz |
| 🧰 Hypervisor | VirtualBox 7.2 |
| 🐉 Security OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip is used to extract Kali Linux virtual-machine files.

**Download:**  
https://7-zip.org/download.html

---

## Step 2. Install VirtualBox

Oracle VirtualBox is installed as the hypervisor for the cybersecurity lab.

**Download:**  
https://www.virtualbox.org/wiki/Downloads

---

## Step 3. Create the NAT Network

Open VirtualBox and create a dedicated NAT Network.

Configure it as:

```text
Network Name: CyberLab
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled
```

A NAT Network allows multiple virtual machines connected to the same network to communicate with each other.

---

## Step 4. Import Kali Linux

Download Kali Linux from the official Kali Linux website and import the virtual machine into VirtualBox.

**Download:**  
https://www.kali.org/get-kali/

Configure the VM network adapter:

```text
Adapter 1
Attached to: NAT Network
Network:     CyberLab
```

---

## Step 5. Configure the Kali Linux Network

Check the Kali Linux network configuration:

```bash
ip a
```

Check the routing table:

```bash
ip route
```

Example configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

---

## Step 6. Verify the Lab Network

Test the gateway:

```bash
ping 10.0.0.1
```

Test Internet connectivity:

```bash
ping 8.8.8.8
```

Check DNS resolution:

```bash
nslookup google.com
```

---

## Step 7. Create a Clean VM Snapshot

After completing the initial configuration, create a VirtualBox snapshot.

Example snapshot name:

```text
Clean Kali - Lab Setup
```

This provides a clean recovery point before starting future cybersecurity exercises.

---

# 🔎 Lab Verification

| ✅ Test | 🧾 Command | 🎯 Expected Result |
|---|---|---|
| 🌐 Check IP address | `ip a` | Kali IP displayed |
| 📡 Test gateway | `ping 10.0.0.1` | Successful replies |
| 🌍 Test Internet | `ping 8.8.8.8` | Successful replies |
| 🔎 Test DNS | `nslookup google.com` | Domain resolves |
| 🧰 Verify Nmap | `nmap --version` | Nmap version displayed |

---

# 💡 What I Learned

Through this project, I learned how to:

- Create a virtual cybersecurity laboratory.
- Configure VirtualBox networking.
- Configure a NAT Network.
- Install and configure Kali Linux.
- Configure IPv4 networking.
- Verify network connectivity.
- Create and use VM snapshots.
- Prepare an environment for future cybersecurity exercises.

---

# 🔐 Security & Ethical Use

This laboratory is intended strictly for education and authorized security testing.

Do not scan, attack, or test systems without proper authorization.

---

# 🔗 Tools & Resources

- **7-Zip:** https://7-zip.org/download.html
- **VirtualBox:** https://www.virtualbox.org/wiki/Downloads
- **Kali Linux:** https://www.kali.org/get-kali/

---

# 👤 Author

**Jenik Shrestha**

Cybersecurity Student | Ethical Hacking | Penetration Testing

---

## 📌 Project Information

**Project:** Personal Cybersecurity Lab Setup  
**Environment:** Oracle VirtualBox + Kali Linux  
**Network:** 10.0.0.0/24
