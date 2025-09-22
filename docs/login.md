**First-time Login**
```bash
ssh -i /home/user/.ssh/id_ed25519 'ecu'
```

Depending on `StrictHostKeyChecking` and whether you pre-scanned the key, you may be prompted to trust the host.

> **Note:** Replace `user` with your user directory.
 
After configuring SSH key and host entry ([on this page](ssh.md)), you can log in with `ssh ecu`:


```console-session
✿ user@archlinux [~] $ ssh ecu

############################################################################
#                     East Carolina University                             #
#        Unauthorized use of this system is strictly prohibited.           #
#                                                                          #
#    By accessing this system you agree to comply with the Policies,       #
# Guidelines, and Regulations at http://www.ecu.edu/itcs/help/itcspolicies #
############################################################################

Last login: Wed Sep 17 13:07:57 2025 from <client-ip-address>  # IP redacted
[username@csstu ~]$ 
```
> Where `username` would be your **PirateID**.

**Verify `known_hosts` Fingerprints**
```bash
ssh-keygen -lf ~/.ssh/known_hosts | grep csstu.intra.ecu.edu
```

**Fingerprints:**
```
3072 SHA256:SX5PMos63auLspbXjkAviHB/3e86f43pBBc2BRaM0ZU csstu.intra.ecu.edu (RSA)
256  SHA256:QpqK5EOOHzKBj3GZobkJszm2nc3xfTofOhkQQWU19kA csstu.intra.ecu.edu (ECDSA)
256  SHA256:aiDs3Pu8PvjDyyIUp6vN7d+s5lxQkz+Lgevu75b9TR0 csstu.intra.ecu.edu (ED25519)
```
