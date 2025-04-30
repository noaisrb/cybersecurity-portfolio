# Project 1 – Local Network Analysis with Netdiscover and Nmap

## Objective

The goal of this project is to identify active devices on my local network, discover their IP and MAC addresses, and analyze exposed services. The process is carried out from a Kali Linux machine and represents the first step in a basic network security assessment.

---

## Tools Used

- **Kali Linux** (virtual machine with bridged adapter)
- `ip a` – To check local IP and active interface
- `netdiscover` – To detect active devices in the network
- `nmap` – To scan ports, services, and detect operating systems

---

## Steps Performed

### 1. Checking local IP address

Command used:

```bash
ip a

Result: the active interface was eth0 and the assigned IP was 192.168.1.x, which confirms that I was on a real local network with subnet 192.168.1.0/24.

![IP Scan](screenshot_ip.png)

### 2. Discovering devices with netdiscover

Command used:

```bash
sudo netdiscover -r 192.168.1.0/24

![Netdiscover Scan](screenshot_netdiscover.png)


### Scanning the router (192.168.1.1) with nmap

```bash
sudo nmap -sV -O 192.168.1.1

The router has three open ports: SSH, HTTP, and HTTPS.

It runs Dropbear SSH server and a lightweight HTTP server (mini_httpd).

The operating system is detected as embedded Linux (Linux 3.2 - 4.14).

![Nmap Scan](screenshot_nmap.png)


## What I Learned

This first project gave me practical experience with essential network discovery techniques used in cybersecurity. I learned to:

- Identify my own IP address and understand how local networks are structured.
- Use `netdiscover` to detect devices connected to a real local network and interpret the meaning of IP addresses, MACs, and vendors.
- Perform a basic Nmap scan to detect open ports, running services, and operating system fingerprints on a router.
- Read and analyze Nmap output, including how to identify potential services (like SSH and HTTP) and their versions.
- Understand how basic scanning tools can be used in early stages of a penetration test or security audit.

