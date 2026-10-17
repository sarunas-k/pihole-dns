# Pi-hole

DNS ad blocker on a QNAP NAS

## Architecture

| Item | Value |
| :--- | :--- |
| Host | QNAP NAS, Container Station |
| Image | `pihole/pihole:2026.10.0` (pinned) |
| Network | external `qnet-static-eth0-79e6cc` **must already exist** (created in Container Station); compose does not create it |
| IP | `192.168.1.113` |
| Data | `/share/Container/pihole/etc-pihole` mounts to `/etc/pihole` |

Clients use `192.168.1.113` as DNS. Blocked domains are answered locally and the rest is forwarded upstream.

## Usage

```bash
docker compose up -d
```
