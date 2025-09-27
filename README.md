# Backdoor Command Execution

## Objective

Demonstrate and document exploitation of the vsftpd 2.3.4 backdoor present in the vulnerable Metasploitable2 VM. The lab shows network discovery (nmap), triggering the intentional backdoor by sending a specially-crafted username (contains :)), connecting to the backdoor TCP port, and obtaining a root shell. All work is performed in a controlled host-only lab (Kali attacker, Metasploitable2 victim).

### Skills Learned

- Network reconnaissance with nmap (service/version detection).
- Interacting with services using nc (netcat) and crafting single-line payloads.
- Timing-sensitive exploitation (race between trigger and backdoor listener).
- Verifying successful remote code execution (whoami) and basic post-exploit checks.
- Thinking through mitigations for a backdoored/malicious server (patching, firewalling, least privilege).

### Tools Used

- Kali Linux (attacker).
- Metasploitable2 (victim — contains vsftpd 2.3.4 backdoor).
- ip / ip addr (network enumeration).
- ping (connectivity check).
- nmap (nmap -sV for service/version detection).
- nc / netcat (sending username/password payload; connecting to backdoor port).

### Environment Setup 
- Host-only network adapter for both VMs (isolated lab network).
- Kali IP: 192.168.56.102 (eth0).
- Metasploitable2 IP: 192.168.56.101 (eth0).
- Confirm both VMs are powered on and on the same Host-Only network.
- No external network access required.

## Steps

<img width="959" height="504" alt="screenshot with ips" src="https://github.com/user-attachments/assets/b62680f1-10a6-4d18-ac70-f029ad115ace" />
# Confirm network and IPs

<img width="959" height="503" alt="kali pinging meta" src="https://github.com/user-attachments/assets/202ec2c5-4da9-445d-a406-6a13bbf1e9be" />
# Verify connectivity

<img width="957" height="505" alt="3 network scan" src="https://github.com/user-attachments/assets/d55b64da-a8af-4dd0-8f4c-011ade382f92" />
# Confirm port 21/tcp is open and vsftpd 2.3.4 reported

<img width="959" height="262" alt="exploit working" src="https://github.com/user-attachments/assets/ad28764b-f43a-4f51-a2c9-0e3ca025776b" />
# Trigger the vsftpd backdoor and immediately connect to the backdoor shell
# Once connected, ran commands like 'whoami' and 'root' to verify it worked








