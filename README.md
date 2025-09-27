# Buffer Overflow Export

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

## Steps







