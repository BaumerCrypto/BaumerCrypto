# Hey, I'm BaumerCrypto (AKA: BaumerCrypto2.0) 👋

I'm a telecom fiber optic technician in Canada. I've been mining and running all types of cryptocurrency infrastructure since 2017 - GPUs, full nodes, masternodes, staking nodes, ASIC mining, and Oracle nodes.

## What I'm Working On

🔷 **DigiDollar Oracle Operator** - I run Oracle Slot 17 (digibyte-maxi) for DigiByte's DigiDollar stablecoin system. I build and maintain the monitoring tools, hardening guides, and deployment scripts that keep my oracle node running 24/7 on a hardened Linux VPS. DigiDollar activated on mainnet on 2026-07-17 at block 23,869,440, and my Oracle Slot 17 is now a live signing oracle in the 7-of-35 MuSig2 quorum. I run two systemd-managed daemons (mainnet on v9.26.5, testnet26 on v9.26.4), and `oracle.dgbmaxi.com` is baked into DigiByte Core's mainnet chain parameters as a seed node (v9.26.2+). Along the way I've contributed to launch-strategy and oracle-roster discussions with the core developers.

⛏️ **Crypto Mining Infrastructure** - Solo mining DGB and BTC using [GSS/GSSM by MMFP Solutions](https://www.mmfpsolutions.io/), Start9/DATUM Gateway, custom ASIC monitoring scripts and Discord webhook alerting, which I originally developed for my personal setup over the years and have now shared with fellow crypto hobbyists.

🛠️ **Open Source Tooling** - Everything I build for my own infrastructure gets published so other operators can use it. If it's useful to me, it's probably useful to someone else.

## Repos

| Repo | What It Is |
|------|-----------|
| [digidollar-oracle-tools](https://github.com/BaumerCrypto/digidollar-oracle-tools) | Monitoring scripts, hardening guides, and setup docs for DigiDollar oracle operators. My main project. |
| [crypto-mining-tools](https://github.com/BaumerCrypto/crypto-mining-tools) | ASIC temperature monitoring with auto-switching for CGMiner ASICs, and Start9/DATUM Gateway health probes. Discord webhook alerting. |

## What I've Built

- **oracle-monitor.sh** (v2.10.1) - ~2,400-line health monitoring system with 13 automated checks: external config file, `--dry-run` mode, `--config` flag for dual-instance monitoring (testnet + mainnet from one script), Discord webhook and email alerting (SMTP/Brevo relay), a daily self-update check against the published release, anti-flap engineering (cooldown timer + hysteresis buffer), quorum-margin tracking with heartbeat-based oracle counting, swap-pressure detection, MuSig2 session monitoring, degraded-consensus detection, a debug.log watchdog with safe log auto-rotation and disk-usage warnings, an inbound/outbound peer split, a DigiDollar economy line on the health summary, and a chain-vs-label misconfiguration check. A network label is stamped on every alert so testnet and mainnet cards are never confused. Runs on cron every 5 minutes on my oracle VPS.
- **Cross-platform oracle monitor** - Native Windows PowerShell port (`oracle-monitor.ps1`, zero dependencies) and macOS port (`oracle-monitor-macos.sh`, stock bash 3.2). Full logic parity with the Linux version. Both include a live watch-mode dashboard. Setup guide and config templates for each platform.
- **oracle-network-status.sh** (v1.8.1) - Gitter network status bot that posts automated oracle health summaries to the DigiDollar community channel once per day via the Matrix API. Reports quorum health, consensus price, MuSig2 signing status, software-version adoption, and stale/inactive operators with @ mention notifications. Dual-instance support for testnet + mainnet. Community-requested feature by shenger.
- **ORACLE_HARDENING_GUIDE.md** - Full VPS security hardening guide (1,000+ lines) covering SSH, UFW, Fail2Ban, kernel hardening, systemd, resource isolation, and OOM protection. Based on my live oracle setup, reboot-verified, soak-tested with 3 concurrent daemons.
- **HOME_ORACLE_HARDENING_GUIDE.md** - Home network security hardening guide (1,331 lines) for Linux, Windows, and macOS. Three tiers from essential to advanced - covers firewall, port forwarding, NTP time sync, router hardening, UPS, VLANs, and WireGuard. Community-requested by Aussie Epic.
- **Oracle VPS automation** - systemd services for auto-start on reboot (2 daemons: mainnet on v9.26.5, testnet26 on v9.26.4), simplified startup scripts (unencrypted oracle wallet, no manual unlock needed), cron-based monitoring with 12-hour health summaries, swap + systemd-oomd OOM protection, and VPS snapshot management for disaster recovery.
- **Mainnet seed peer** - I own the `dgbmaxi.com` domain with DNS pointed at my oracle VPS; `oracle.dgbmaxi.com:12024` is baked into DigiByte Core's mainnet chain parameters as a seed node (v9.26.2+).

## Tech I Work With

- **Blockchains:** Bitcoin of course, there is no second best! Well... besides DigiByte 😄
- **Node History:** Full nodes, masternodes, and staking nodes across DigiByte, PIVX, ChainFlip, SESH/Session/Oxen, and sooo many others over the years.
- **Community Governance:** Helium Network MCC (Manufacturer Compliance Committee): reviewed and approved IoT hotspot manufacturers for the HNT network.
- **Infrastructure:** Linux Ubuntu VPS's, systemd services, UFW firewalls, Fail2Ban, SSH hardening, sysctl tuning, systemd-oomd, cgroup resource isolation, DNS/domain management.
- **Scripting & DevOps:** Bash, PowerShell, cron automation, Discord webhook API integrations, Matrix/Gitter bot API, JSON parsing with jq, systemd service creation, health monitoring with state-machine alerting (anti-flap, cooldown, hysteresis), VPS security hardening, Linux server administration, cross-platform scripting (Linux/Windows/macOS).
- **Mining Hardware:** Started off with all types of GPU mining hardware in 2017, a variety of ASICs - Antminer S9, S17 Pro & S19, and now as 'Home Mining' has taken off and devices have advanced, I have an assorted collection of Canaan Avalon Series Miners, multiple NerdQaxe++ & NerdQx devices and a few more...
- **Mining Software:** [GSS/GSSM by MMFP Solutions](https://www.mmfpsolutions.io/), Start9 OS, DATUM Gateway, ESP-Miner-NerdQAxePlus, AxeOS, BitCoin Knots.
- **Certs:** MCSE, MCP, CompTIA A+, CompTIA Network+
- **Education:** Post-secondary Systems & Electronics Technology

## Find Me

| Platform | Link |
|----------|------|
| Gitter | digibyte-maxi in [#digidollar:gitter.im](https://app.gitter.im/#/room/#digidollar:gitter.im) |
| X / Twitter | [@BaumerCrypto2\_0](https://x.com/BaumerCrypto2_0) |
| TikTok | [@baumercrypto2.0](https://www.tiktok.com/@baumercrypto2.0) |
| YouTube | [@baumercrypto2.0](https://www.youtube.com/@baumercrypto2.0) |
