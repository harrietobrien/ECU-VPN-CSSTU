**Ensure a user ssh-agent is running**
```bash
systemctl --user enable --now ssh-agent
```

**Generate a new ED25519 key and `ssh-add`**
```bash
ssh-keygen -t ed25519 -C "username@ecu.edu"
ssh-add ~/.ssh/id_ed25519
```
> **Note:** Replace `username` with your PirateID. 

**Create SSH Client Configuration File: `~/.ssh/config`**
```bash
mkdir -p ~/.ssh && chmod 700 ~/.ssh
vim ~/.ssh/config
```
⤷ `-p` : If the specified parent directory DNE, `mkdir -p` will create 
it along with any necessary intermediate directories.  
⤷ `700` : Octal representation of permissions passed to `chmod` (command that changes file mode bits).

```bash
vim ~/.ssh/config
```
**Enter or paste the following:**
```conf
Host ecu
    HostName csstu.intra.ecu.edu
    User username  # PirateID
    Port 22
    IdentityFile ~/.ssh/id_ed25519
    StrictHostKeyChecking accept-new
    UserKnownHostsFile ~/.ssh/known_hosts
```

**Pre-add the server host key (optional):**
```bash
ssh-keyscan csstu.intra.ecu.edu >> ~/.ssh/known_hosts
```
**Install your public key on the server:**
```bash
ssh-copy-id -i ~/.ssh/id_ed25519.pub ecu
```
**Expected output (example):**
```
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/user/.ssh/id_ed25519.pub"
...
Number of key(s) added: 1
Now try logging in with: ssh -i /home/user/.ssh/id_ed25519 'ecu'
```
where `user` would be your home user directory.

