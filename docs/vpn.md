**Start and enable the agent:**

```bash
sudo systemctl start vpnagentd.service
sudo systemctl enable vpnagentd.service
```

**Optionally, start the binary directly:**

```bash
sudo /opt/cisco/secureclient/bin/vpnagentd
```

**Check status of Cisco AnyConnect VPN background agent service:**

```bash
systemctl status vpnagentd.service
```

> **Note:** `vpnagentd.service` is the name of the systemd service.