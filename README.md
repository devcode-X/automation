# 🤖 automation

> **Set it and forget it** — GitHub Actions workflows that keep your repositories fresh, consistent, and up-to-date around the clock.

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Schedule](https://img.shields.io/badge/Schedule-Daily-brightgreen?style=for-the-badge)

---

## 📖 Overview

**automation** is a GitHub Actions-powered repository that handles scheduled, automated maintenance tasks across Devansh's GitHub profile. It leverages cron-triggered workflows to run daily repository updates — keeping metadata, stats, and profile data consistently in sync without any manual intervention. Think of it as a silent DevOps assistant that never sleeps.

---

## ✨ Key Features

- ⏰ **Cron-scheduled workflows** — Runs automatically every day via GitHub Actions `schedule` trigger
- 🔄 **Automated repository updates** — Syncs repo metadata, README stats, or other profile data on a daily cadence
- 🛡️ **Zero-maintenance design** — Fully hands-off once deployed; no servers, no containers
- 📋 **Workflow transparency** — All automation steps are version-controlled and auditable in `.github/workflows/`
- 🔔 **Status badges** — Live workflow status surfaced via GitHub Actions badges

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| CI/CD Platform | GitHub Actions |
| Workflow Config | YAML |
| Trigger Mechanism | `schedule` (cron) + `workflow_dispatch` |
| Runtime | GitHub-hosted Ubuntu runners |

---

## 🚀 Quick Start

### Prerequisites
- A GitHub account with Actions enabled on this repository
- (Optional) Secrets configured in **Settings → Secrets and Variables → Actions** for any authenticated API calls

### Enable the Workflows

1. **Fork or clone** this repository to your GitHub account.
2. Navigate to the **Actions** tab and enable workflows if prompted.
3. Workflows will trigger automatically on their cron schedule. To run immediately:

```bash
# Trigger manually via GitHub CLI
gh workflow run <workflow-name>.yml
```

### Customize the Schedule

Edit the cron expression inside `.github/workflows/<workflow>.yml`:

```yaml
on:
  schedule:
    - cron: '0 0 * * *'   # Every day at midnight UTC
  workflow_dispatch:        # Also allow manual triggers
```

---

## 📁 Folder Structure

```
automation/
├── .github/
│   └── workflows/
│       ├── daily-update.yml      # Main scheduled workflow
│       └── manual-trigger.yml    # On-demand workflow
├── scripts/
│   └── update.sh                 # Helper scripts called by workflows
└── README.md
```

---

## 📊 Workflow Status

| Workflow | Status |
|---|---|
| Daily Update | ![Daily Update](https://github.com/devcode-X/automation/actions/workflows/daily-update.yml/badge.svg) |

---

## 👤 Author

**Devansh Awasthi** · [@devcode-X](https://github.com/devcode-X)
