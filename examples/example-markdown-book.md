# Example: Studying a Local Markdown Book

This example shows how `socratic-mentor` initializes a study workspace for a multi-chapter Markdown book without modifying any existing files.

## Workspace Before Setup

```text
systems-networking-handbook/
├── 00 - Reading Log.md          # Existing user note (preserved untouched)
├── Chapter 01 - OSI and TCP-IP Basics.md
├── Chapter 02 - Routing, NAT, and Firewalls.md
├── Chapter 03 - DNS and HTTP Internals.md
├── Chapter 04 - TLS and Certificates.md
├── Chapter 05 - Load Balancing.md
├── Chapter 06 - Linux Sockets and Tuning.md
├── Chapter 07 - Containers and Virtual Networks.md
├── Chapter 08 - Packet Capture and Analysis.md
├── Chapter 09 - BGP and Autonomous Systems.md
└── Chapter 10 - Incident Response Runbooks.md
```

## Phase 1 Calibration Summary

- **Book:** *Systems & Networking Handbook* (10 chapters)
- **User's Goal 1:** Trace and troubleshoot a web request across local routing, NAT, firewall rules, DNS, and HTTP.
- **Chapters selected for Goal 1:** `Chapter 01` through `Chapter 03`.
- **Prior knowledge:** `basic` — the learner already knows OSI layers, IPv4 subnets, and TCP vs. UDP, so `Chapter 01` is skipped and placed in `Optional`.
- **Sub-level split:** `Chapter 02` covers three dense mechanisms (routing tables, NAT translation, and stateful firewalls), so the mentor splits it into `Level 2.1` and `Level 2.2`.
- **Non-destructive rule:** `00 - Reading Log.md` remains untouched. The mentor only creates `STUDY_PLAN.md` and `CURRICULUM.md`.

---

## Generated `STUDY_PLAN.md`

```markdown
---
title: "Systems & Networking Handbook"
source_type: "local-book"
current_level: "2.1"
prior_level: "basic"
mode: "mentor"
lab_env: "cli-terminal"
goal_1_completed: false
---

# Study Plan: Systems & Networking Handbook

## Current Status

- **Progress:** `0 / 3 levels completed`
- **Current Level:** `Level 2.1`
- **Prior Level:** `basic`
- **Mode:** `mentor`
- **Lab Environment:** `cli-terminal`
- **Active Goal:** `Goal 1`

## Goal 1: Trace and Troubleshoot an End-to-End Web Request

Complete the active levels below to diagnose routing, NAT, firewall, DNS, and HTTP failures.

- [ ] **Level 2.1: Routing Tables and Packet Forwarding** — [Chapter 02](./Chapter%2002%20-%20Routing,%20NAT,%20and%20Firewalls.md)
- [ ] **Level 2.2: NAT Translation and Stateful Firewalls** — [Chapter 02](./Chapter%2002%20-%20Routing,%20NAT,%20and%20Firewalls.md)
- [ ] **Level 3: DNS Resolution and HTTP Request Lifecycle** — [Chapter 03](./Chapter%2003%20-%20DNS%20and%20HTTP%20Internals.md)

> [!note]- Optional (Skipped & Deferred Topics — unlockable anytime)
> Existing personal notes such as [00 - Reading Log.md](./00%20-%20Reading%20Log.md) are preserved untouched.
>
> - [ ] **Skipped:** Chapter 01 — OSI and TCP/IP Basics — [Chapter 01](./Chapter%2001%20-%20OSI%20and%20TCP-IP%20Basics.md) *(skipped during calibration: basic prior knowledge)*
> - [ ] **Deferred:** Chapter 04 — TLS and Certificates — [Chapter 04](./Chapter%2004%20-%20TLS%20and%20Certificates.md)
> - [ ] **Deferred:** Chapter 05 — Load Balancing — [Chapter 05](./Chapter%2005%20-%20Load%20Balancing.md)
> - [ ] **Deferred:** Chapter 06 — Linux Sockets and Tuning — [Chapter 06](./Chapter%2006%20-%20Linux%20Sockets%20and%20Tuning.md)
> - [ ] **Deferred:** Chapter 07 — Containers and Virtual Networks — [Chapter 07](./Chapter%2007%20-%20Containers%20and%20Virtual%20Networks.md)
> - [ ] **Deferred:** Chapter 08 — Packet Capture and Analysis — [Chapter 08](./Chapter%2008%20-%20Packet%20Capture%20and%20Analysis.md)
> - [ ] **Deferred:** Chapter 09 — BGP and Autonomous Systems — [Chapter 09](./Chapter%2009%20-%20BGP%20and%20Autonomous%20Systems.md)
> - [ ] **Deferred:** Chapter 10 — Incident Response Runbooks — [Chapter 10](./Chapter%2010%20-%20Incident%20Response%20Runbooks.md)

## Session Log

| Date | Level | Status | Key Notes |
| --- | --- | --- | --- |
| 2026-04-01 | Setup | Completed | Selected Chapters 1–3 for Goal 1, skipped Chapter 01, split Chapter 02 into 2.1 and 2.2, kept `00 - Reading Log.md` untouched. |
```

---

## Generated `CURRICULUM.md` (Excerpt)

```markdown
# Curriculum: Systems & Networking Handbook

## Goal 1: Trace and Troubleshoot an End-to-End Web Request

### Level 2.1: Routing Tables and Packet Forwarding

- **Core concept:** Longest-prefix match decision flow from host routing table to default gateway and next-hop MAC resolution.
- **Source files:**
  - `./Chapter 02 - Routing, NAT, and Firewalls.md` *(Sections 2.1–2.2)*
- **Dependencies:** Basic IPv4 subnetting (verified in calibration)
- **Done check:**
  - **In chat:** Predict the chosen route and next hop for three destination IPs given a 4-row routing table.
  - **Optional hands-on lab:** Run `ip route get <target-ip>` (or `route print` on Windows) and explain which rule matched.

---

### Level 2.2: NAT Translation and Stateful Firewalls

- **Core concept:** Source NAT translation table mapping private `IP:port` pairs to public sockets alongside stateful connection tracking.
- **Source files:**
  - `./Chapter 02 - Routing, NAT, and Firewalls.md` *(Sections 2.3–2.5)*
- **Dependencies:** Level 2.1
- **Done check:**
  - **In chat:** Trace an outbound packet and its return packet through a NAT table and identify why an unsolicited inbound packet gets dropped.
  - **Optional hands-on lab:** Inspect active sockets with `ss -tunap` (or `netstat -ano`) and match local ephemeral ports to remote endpoints.

---

### Level 3: DNS Resolution and HTTP Request Lifecycle

- **Core concept:** Recursive DNS lookup chain feeding an HTTP request/response flow over TCP.
- **Source files:**
  - `./Chapter 03 - DNS and HTTP Internals.md`
- **Dependencies:** Level 2.2
- **Done check:**
  - **In chat:** Diagnose a request that resolves DNS correctly but stalls before receiving HTTP headers.
  - **Optional hands-on lab:** Run `dig +trace example.com` and `curl -v https://example.com` and map each stage to the diagram.

---

## Optional (Skipped / Deferred)

### Skipped During Calibration

- **Chapter 01 — OSI and TCP/IP Basics**
  - **Source files:** `./Chapter 01 - OSI and TCP-IP Basics.md`
  - **Reason:** Learner calibrated at `basic` level and already understands layers, IP addressing, and TCP/UDP fundamentals.

### Deferred for Future Goals

- **Chapters 04–10**
  - **Source files:** `./Chapter 04 - TLS and Certificates.md` through `./Chapter 10 - Incident Response Runbooks.md`
  - **Reason:** Deferred beyond Goal 1; unlockable on demand.
```
