# Container Security Lab: bWAPP + Falco (eBPF syscall monitoring) + seccomp hardening

This repository contains a small, reproducible lab for a Network & Cyber Security course project.  
It demonstrates **runtime detection** of suspicious container activity using **Falco** (syscall telemetry via eBPF) and **prevention/hardening** using **seccomp** syscall filtering.

The project is intentionally designed to support a clear *before vs. after* story for the report and demo (as required in the course assignment). :contentReference[oaicite:0]{index=0}

---

## What is included

- **bWAPP** — intentionally vulnerable web application (AppSec training target).
- **Falco** — runtime security sensor that observes **syscalls** and produces alerts.
- **seccomp profile** — custom JSON policy that blocks high-risk syscalls (e.g., `mount`, namespace manipulation).
- **Falco local rules** — extra rules to increase signal for container-escape-like behavior (e.g., mount attempts).

---

## Repository structure

```text
.
├── docker-compose.yml
├── falco-rules/
│   └── falco_rules.local.yaml
├── seccomp-profiles/
│   └── bwapp-seccomp.json
