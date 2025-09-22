**Instructions cover the following (for now):**

- Installing **Cisco Secure Client** on Arch Linux / [Arch-based Linux distributions](https://wiki.archlinux.org/title/Arch-based_distributions)
- Enabling `vpnagentd` (Cisco Secure Client VPN Agent Daemon)
- Connecting to ECU VPN via Cisco Secure Client GUI
- Generating SSH keys & `~/.ssh/config`
- Verifying host keys and logging into `csstu.intra.ecu.edu`
- Copying to server with `scp`, building, and submitting

> **Tested:** [Arch Linux](https://archlinux.org)  
> **Server:** `csstu.intra.ecu.edu` _Red Hat Enterprise Linux 9.6 (Plow)_

**View additional operating system release information by executing:**
``` bash-session
[user@csstu ~]$ cat /etc/os-release
```
**Instruction Links**

- [Install Cisco Secure Client (pacman)](install.md)
- [Enable VPN Agent Daemon](vpn.md)
- [Connect to VPN via Cisco Secure Client](connect.md)
- [SSH Keys and Configuration](ssh.md)
- [Login and Host Verification](login.md)
- [SCP → Build → Submit](workflow.md)

