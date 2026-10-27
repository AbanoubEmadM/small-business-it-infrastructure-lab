# Task 4 — Inspect Essential Services

## 1. Objective

Inspect the status of essential system services on the RHEL 9 server and determine whether they are running and configured to start automatically at boot.

## 2. Tools Used

| Command | Purpose |
|---|---|
| `systemctl status` | Inspect service status, including whether the service is active and enabled |

## 3. Services Inspected

| Service | Active State | Enabled at Boot | Purpose |
|---|---|---|---|
| `NetworkManager` | Active | Yes | Manages network interfaces and connections |
| `sshd` | Active | Yes | Provides secure remote administration through SSH |
| `firewalld` | Active | Yes | Manages host firewall rules |

## 4. Findings

All three inspected services were reported as active and enabled.

- **NetworkManager:** Running and configured to start automatically, supporting network connectivity.
- **SSH daemon (`sshd`):** Running and configured to start automatically, providing the service required for remote administration.
- **Firewalld:** Running and configured to start automatically, providing host-level traffic filtering.

## 5. Conclusion

The initial service inspection confirmed that NetworkManager, SSH, and firewalld were active and enabled at the time of inspection.

This establishes a baseline for subsequent configuration, connectivity testing, and security work.

## 6. Scope and Limitations

This task inspected service states only. It did not verify SSH authentication security, firewall rule correctness, or end-to-end remote connectivity. Those checks should be performed separately when the project reaches the relevant tasks.

No service configuration changes were made during this inspection.