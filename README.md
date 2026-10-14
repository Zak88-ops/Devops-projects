<div align="center">

# 🚀 DevOps Projects

**Hands-on DevOps projects: Linux automation, AWS infrastructure (LocalStack), Docker, and CI/CD with GitHub Actions.**

[![CI/CD](https://github.com/Zak88-ops/Devops-projects/actions/workflows/cicd.yml/badge.svg)](https://github.com/Zak88-ops/Devops-projects/actions/workflows/cicd.yml)
[![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnu-bash&logoColor=white)](https://www.gnu.org/software/bash/)
[![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)](https://www.linux.org/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com/)
[![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)](https://aws.amazon.com/)
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)](https://github.com/features/actions)
[![roadmap.sh](https://img.shields.io/badge/roadmap.sh-DevOps-blueviolet)](https://roadmap.sh/devops)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Built while following the [roadmap.sh DevOps path](https://roadmap.sh/devops), one project at a time.
Every concept is validated through a working, documented project.

</div>

---

## 👋 About

I'm a Computer Science student at **ESI Sidi Bel Abbès** building real infrastructure projects in DevOps and Cloud Engineering.
This repository is my learning log and portfolio: each folder is a self-contained project with its own documentation.

🔗 [LinkedIn](https://www.linkedin.com/in/zakaria-djamel-eddine-benmaidi-6218b1373)

---

## 📂 Projects

### ☁️ Cloud (AWS)

| Project | Description | Docs |
|---|---|---|
| 🌐 **[aws-custom-vpc/](./aws-custom-vpc)** | Custom VPC with public/private subnets, route tables, and an Internet Gateway, built and tested on LocalStack. | [README](./aws-custom-vpc/README.md) |
| 🔐 **[iam-fundamentals/](./iam-fundamentals)** | IAM Users, Groups, Policies, and Roles structured around least privilege, built on LocalStack. | [README](./iam-fundamentals/README.md) |

### 🐳 Containers & CI/CD

| Project | Description | Docs |
|---|---|---|
| 🗳️ **[docker-voting-app/](./docker-voting-app)** | Five-service app (Python, Node.js, .NET, Redis, PostgreSQL) deployed with Docker Compose on a cloud server. Images are built and published through a GitHub Actions pipeline. | [Deployment guide](./docker-voting-app/DEPLOYMENT.md) |
| ⚙️ **[.github/workflows/](./.github/workflows)** | CI/CD pipeline: builds the service images and publishes them to GitHub Container Registry. | [cicd.yml](./.github/workflows/cicd.yml) |

### 🐧 Linux & Automation

| Project | Description | Docs |
|---|---|---|
| 🖥️ **[server-stats.sh](./server-stats.sh)** | Server health and security stats in one shot (CPU, memory, disk I/O, uptime, top processes) plus automated `fail2ban` setup. | [roadmap.sh project](https://roadmap.sh/projects/server-stats) |
| 📊 **[monitoring/](./monitoring)** | A lightweight dashboard for tracking live server metrics. | [roadmap.sh project](https://roadmap.sh/projects/simple-monitoring-dashboard) |
| 🔍 **[nginx-log-analyser/](./nginx-log-analyser)** | Parses Nginx access logs: top IPs, top paths, status codes, and basic 404 scanner detection. | [README](./nginx-log-analyser/README.md) · [roadmap.sh project](https://roadmap.sh/projects/nginx-log-analyser) |
| 🛡️ **[file-integrity-checker/](./file-integrity-checker)** | Detects unauthorized file changes on a system. | [roadmap.sh project](https://roadmap.sh/projects/file-integrity-checker) |

---

## 🛠️ Tech Stack

| Area | Tools |
|---|---|
| **OS & Scripting** | Linux, Bash, cron |
| **Containers** | Docker, Docker Compose |
| **CI/CD** | GitHub Actions, GitHub Container Registry |
| **Cloud** | AWS (VPC, IAM), LocalStack |
| **Web & Security** | Nginx, fail2ban |

---

## 🖥️ server-stats.sh

Displays key server health and security stats in one shot:

- OS info, logged-in users, and system uptime
- Disk I/O, CPU, and memory usage
- Top processes by CPU and by memory
- Installs, enables, and checks the status of `fail2ban` (SSH brute-force protection)
- Automates recurring checks via **cron**

### How fail2ban works here
It scans log files (like `/var/log/auth.log` for SSH) for failed login attempts. When an IP exceeds a set number of failures within a time window, `fail2ban` bans it, usually by adding a temporary firewall rule.

### Requirements
- `sysstat` (auto-installed by the script if missing)
- `fail2ban` (auto-installed by the script if missing)

### Usage
```bash
# Make it executable
chmod +x server-stats.sh

# (Optional) Run it every day at 8 AM via cron
crontab -e
# add this line, save, and exit:
0 8 * * * /path/to/server-stats.sh

# Run it manually
./server-stats.sh
```

> **Note:** parts of the script use `sudo` (installing/enabling `fail2ban` and `sysstat`), so you may be prompted for your password.

**Project reference:** [roadmap.sh/projects/server-stats](https://roadmap.sh/projects/server-stats)

---

## 🗺️ Roadmap

- [x] Linux & Bash automation (server-stats, monitoring, log analysis)
- [x] File integrity checker
- [x] AWS fundamentals on LocalStack (VPC, IAM)
- [x] Basic Dockerfile
- [x] Multi-service app with Docker Compose
- [x] CI/CD pipeline with GitHub Actions
- [ ] Security scanning in the pipeline (Trivy, Gitleaks)
- [ ] Terraform: rebuild the VPC as code
- [ ] Deploy on real AWS (Free Tier, with budget alerts)
- [ ] Log Archive Tool
- [ ] SSH Remote Server Setup
- [ ] Kubernetes + ArgoCD (GitOps)
- [ ] Prometheus + Grafana monitoring

Following the full [DevOps roadmap](https://roadmap.sh/devops) project by project.

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for details.

---

<div align="center">

**Author:** [@Zak88-ops](https://github.com/Zak88-ops)

⭐ If any of these projects helped you, consider giving the repo a star!

</div>
