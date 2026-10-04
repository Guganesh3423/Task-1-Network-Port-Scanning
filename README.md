# Task 1 - Scan Local Network for Open Ports

## Objective
To scan the local network and identify active devices and open TCP ports using Nmap.

## Tools Used
- Nmap 7.99.1
- Npcap 1.88
- Windows CMD

## Network Information
- Local IP: 192.168.1.16
- Subnet Mask: 255.255.255.0
- Network Range: 192.168.1.0/24

## Steps Performed

1. Installed Nmap and verified the installation.
2. Used `ipconfig` to identify the local IP address and network range.
3. Used Nmap host discovery to identify active devices.
4. Performed a TCP SYN scan using:
   `nmap -sS 192.168.1.0/24`
5. Identified open ports on the discovered devices.
6. Analyzed common services and possible security risks.
7. Saved the scan results as `network_scan.txt`.

## Important Open Ports Found

| IP Address | Open Ports |
|------------|------------|
| 192.168.1.1 | 21, 53, 80, 443 |
| 192.168.1.3 | 8008, 8009, 8080, 8443, 9000 |
| 192.168.1.9 | 443, 8800 |
| 192.168.1.16 | 135, 139, 445, 6881 |

## Security Observations

- FTP (21) may transmit data without encryption.
- HTTP (80/8080) does not provide encryption by itself.
- SMB (445) should be restricted to trusted networks.
- NetBIOS (139) is a legacy service and should be disabled if unnecessary.
- MSRPC (135) should be protected using firewall rules.

An open port does not automatically mean that the device is vulnerable. 
Security depends on the service, configuration, authentication, firewall rules, and software version.

## Result

The local network was successfully scanned using Nmap, open ports were identified, and the scan results were saved for analysis.
