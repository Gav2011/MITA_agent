<div align="center">
  
<img src="https://cdn.modeminc.com/mguard/MGuardBanner.png" alt="MGuard Banner" width="800"/>

*MGaurd*

</div>

---

## What is MGuard?

MGuard is a **lightweight network intelligence agent** that deploys in seconds. It continuously scans your LAN and WAN, assigns every discovered IP an evidence-based threat score from 0–100, and alerts you before an intrusion becomes a breach.

---

## Quick Start

**Windows (current platform)**

Download the agent directly:

```
https://cdn.modeminc.com/MGuard/MGuard_Agent.exe
```

Or use the install script:

```sh
curl -sSL https://cdn.modeminc.com/MGuard/MGuard_Install.sh | sh
```

Run the agent:

```sh
MGuard_Agent.exe
```

> Linux, macOS, and Docker support are coming soon.

---

## Features

| Feature | Description |
|---|---|
| **LAN Discovery** | ARP sweep across all reachable subnets. Detects new, missing, and rogue devices. |
| **WAN Monitoring** | Passive inspection of all WAN traffic correlated against 14M+ known-bad IP ranges. Requires router syslog or firewall log forwarding for full WAN visibility. |
| **IP Threat Scoring** | Composite 0–100 score per IP weighing port behavior, GeoIP risk, ASN reputation, and ML anomaly detection. |
| **Instant Alerts** | Sub-second threshold alerts via webhooks. Discord, [Bark Notifications](https://apps.apple.com/us/app/bark-custom-notifications/id1403753865), |
| **Auto Response** | Push firewall rules, BGP null-routes, or VLAN quarantines automatically when a host crosses a defined threshold. |
| **Multi-Agent Mesh** | Deploy across multiple network segments. Agents share intelligence. |

---

## Threat Score Reference

| Score | Level | Meaning |
|---|---|---|
| 0 – 15 | **SAFE** | Known-good or whitelisted host |
| 16 – 34 | **LOW** | Minor anomalies, unusual ports or timing |
| 35 – 54 | **MED** | Reputation signals or elevated scan activity |
| 55 – 74 | **HIGH** | Known bad ASN, active scanning, or C2 behavior |
| 75 – 89 | **CRIT** | Confirmed malicious actor or active exploit attempt |
| 90 – 100 | **BLOCK** | Immediate automated response recommended |

Scores are computed from:

- **GeoIP Risk Weight** - source country vs. ModemINC's regional threat index
- **ASN Reputation** - cross-referenced against bulletproof hosters, VPN exits, Tor exits
- **Port Behavior Analysis** - scan velocity, port patterns, connection timing
- **Behavioral ML Baseline** - per-device normal model built over 72 hours; deviations raise score
- **Live Feed Correlation** - hourly sync with abuse.ch, Emerging Threats, Spamhaus, and the Modeminc global sensor network

---

## WAN Monitoring Note

For full WAN visibility, MGuard needs access to router or firewall logs. The agent can ingest:

- **Syslog** forwarded from your router/firewall
- **Firewall logs** (pfSense, OPNsense, iptables, Windows Firewall)

Without log forwarding, MGuard still monitors traffic visible to the host machine it runs on. Full perimeter coverage requires log integration.

For more information, visit [modeminc.com/MGuard/help](https://modeminc.com/MGuard/help).

---

## Scoring Signal Sources

```
abuse.ch
GeoIP (MaxMind)
ASN Database
```

---

## Roadmap

| Symbol | Status      |
|--------|-------------|
| `+`    | Complete    |
| `~`    | In Progress |
| `-`    | Planned     |

- `+` Windows x86-64 agent
- `~` LAN ARP discovery
- `~` IP threat scoring engine
- `~` WAN log ingestion (syslog / firewall)
- `~` Alert webhooks (Discord, Slack, Json)
- `~` Web dashboard UI
- `~` LAN Agent to Agent Sync
- `-` Linux (amd64 / arm64)
- `-` macOS (Apple Silicon / Intel)

---

## Contributing

Pull requests are welcome. For major changes please open an issue first to discuss what you'd like to change.

---

## License

MIT - see [LICENSE](LICENSE) for details.

---

<div align="center">

Built by **[Modeminc](https://modeminc.com)** · [Website](https://modeminc.com/MGuard) · [Help/Docs](https://modeminc.com/MGuard/help) · [Download](https://cdn.modeminc.com/MGuard/MGuard_Agent.exe)

</div>
