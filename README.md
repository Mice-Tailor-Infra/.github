# Mice-Tailor-Infra Organization

Welcome to **Mice-Tailor-Infra**, a collection of infrastructure projects focused on network proxy solutions, Android system customization, and automated build systems. Our projects emphasize automation, cloud synchronization, and cross-platform compatibility.

## 🎯 Organization Overview

This organization maintains several interconnected projects that form a complete ecosystem for network proxy management, particularly focused on the **Sing-box** proxy platform and Android system enhancements.

## 📚 Repository Portfolio

### 🔧 Core Proxy Infrastructure

#### [sing-box-ksu-module](https://github.com/Mice-Tailor-Infra/sing-box-ksu-module)
[![CI Build](https://img.shields.io/badge/CI-Passing-brightgreen)](https://github.com/Mice-Tailor-Infra/sing-box-ksu-module/actions)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/sing-box-ksu-module/blob/main/LICENSE)

High-performance Sing-box runtime environment for Android with KernelSU module support.

**Key Features:**
- Cloud-based configuration synchronization
- Binary consolidation in centralized workspace
- System-level symbolic links for global commands
- Hot update support via `sbc update`
- Credential isolation with `.env` files

**Languages:** Shell | **Homepage:** [Documentation](https://miceworld.top/sing-box-ksu-module/)

#### [sing-box-config-templates](https://github.com/Mice-Tailor-Infra/sing-box-config-templates)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/sing-box-config-templates/blob/main/LICENSE)

Infrastructure as Code (IaC) approach to managing Sing-box configurations across multiple platforms.

**Key Features:**
- Decoupled secrets architecture (no credentials in Git)
- Multi-branch environment isolation (main/mobile/win11)
- Dynamic configuration rendering via `envsubst`
- Optimized routing logic for different platforms
- VoLTE/VoNR physical isolation for Android

**Languages:** JSON, Shell | **Homepage:** [Config Templates](https://miceworld.top/sing-box-config-templates/main/config.template.json)

#### [sing-box-auto-build-ci](https://github.com/Mice-Tailor-Infra/sing-box-auto-build-ci)
[![CI Status](https://img.shields.io/badge/Build-Automated-orange)](https://github.com/Mice-Tailor-Infra/sing-box-auto-build-ci/actions)

Automated CI/CD pipeline for building [reF1nd/sing-box](https://github.com/reF1nd/sing-box) binaries across multiple platforms.

**Supported Platforms:**
- Android (arm64)
- Linux (amd64: v1/v3/v4, arm64)
- Windows (amd64: v1/v3/v4, arm64)
- macOS (amd64, arm64)

**Features:** Includes `with_gvisor`, `with_quic`, `with_dhcp`, `with_wireguard`, `with_utls`, `with_clash_api`, `with_tailscale`, `with_acme`

**Languages:** Shell | **Homepage:** [Build CI](https://miceworld.top/sing-box-auto-build-ci/)

### 📦 Package Distribution

#### [cagedbird-pacman-repo](https://github.com/Mice-Tailor-Infra/cagedbird-pacman-repo)
[![Arch](https://img.shields.io/badge/Arch-x86__64%20%7C%20aarch64-blue?logo=arch-linux)](https://miceworld.top/cagedbird-pacman-repo/)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/cagedbird-pacman-repo/blob/main/LICENSE)

Private Pacman repository hosting CI/CD auto-built **sing-box-ref1nd** packages, distributed globally via Tencent Cloud EdgeOne (Anycast).

**Features:**
- Automated package builds from CI/CD pipeline
- Global CDN acceleration via Tencent EdgeOne
- Micro-architecture optimizations (x86_64 v3, aarch64)
- Support for Arch Linux x86_64 and aarch64

**Languages:** Package Repository | **Homepage:** [Pacman Repo](https://miceworld.top/cagedbird-pacman-repo/)

### 🌐 Network Optimization

#### [fcm-hosts-ksu](https://github.com/Mice-Tailor-Infra/fcm-hosts-ksu)

KernelSU/Magisk module for systemless hosts management with auto-sync capability.

**Key Features:**
- Soft link strategy (`/system/etc/hosts` → `/data/adb/fcm-hosts/hosts`)
- Cloud sync with FCM dual IP pool
- Scheduled updates every 3 hours
- Localhost protection and SELinux compatibility

**Languages:** Shell | **Homepage:** [FCM Hosts KSU](https://miceworld.top/fcm-hosts-ksu/)

#### [fcm-hosts-next](https://github.com/Mice-Tailor-Infra/fcm-hosts-next)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/fcm-hosts-next/blob/main/LICENSE)

Automated Google Firebase Cloud Messaging (FCM) optimized hosts project with distributed edge probing.

**Architecture:**
- **Data Collection:** GitHub Actions (US) with EDNS Client Subnet (ECS)
- **Real-device Verification:** Self-hosted Runner on Alibaba Cloud
- **Load Balancing:** Top 12 IPs with Round-Robin + Shuffle

**Available Files:**
- `fcm_dual.hosts` - Dual-stack load-balanced (recommended)
- `fcm_ipv6.hosts` - Pure IPv6 version
- `fcm_ipv4.hosts` - Pure IPv4 version

**Languages:** Python | **Homepage:** [FCM Hosts Next](https://miceworld.top/fcm-hosts-next/)

### 🌍 Organization Website

#### [mice-tailor-infra.github.io](https://github.com/Mice-Tailor-Infra/mice-tailor-infra.github.io)

GitHub Pages site for the organization.

**Languages:** CSS, HTML

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    Mice-Tailor-Infra                        │
│                  Infrastructure Ecosystem                    │
└─────────────────────────────────────────────────────────────┘
                              │
                 ┌────────────┼────────────┐
                 │            │            │
         ┌───────▼──────┐ ┌──▼────────┐ ┌▼──────────────┐
         │   Build CI   │ │  Config   │ │  Distribution │
         │              │ │ Templates │ │               │
         └───────┬──────┘ └──┬────────┘ └┬──────────────┘
                 │            │           │
         ┌───────▼────────────▼───────────▼──────┐
         │      sing-box-ksu-module (Android)    │
         └───────────────────────────────────────┘
                 │
         ┌───────▼───────┐
         │  CDN (EdgeOne)│
         │  miceworld.top │
         └───────────────┘
```

## 🚀 Quick Start

### For Android Users (KernelSU/Magisk)

1. **Install sing-box-ksu-module:**
   ```bash
   # Download latest release from
   # https://github.com/Mice-Tailor-Infra/sing-box-ksu-module/releases
   # Install via Magisk/KernelSU Manager
   # Reboot device
   ```

2. **Configure subscription:**
   ```bash
   sbc edit
   # Add your subscription URLs
   sbc start
   ```

3. **Optional: Install FCM hosts optimization:**
   ```bash
   # Download fcm-hosts-ksu module
   # Install via Magisk/KernelSU Manager
   # Reboot device
   ```

### For Arch Linux Users

1. **Add CagedBird repository:**
   ```bash
   # Edit /etc/pacman.conf, add at the top:
   [cagedbird-repo]
   SigLevel = Optional TrustAll
   Server = https://miceworld.top/cagedbird-pacman-repo/$arch
   ```

2. **Install sing-box:**
   ```bash
   sudo pacman -Syy
   sudo pacman -S sing-box-ref1nd
   ```

### For Configuration Template Users

1. **Clone the template repository:**
   ```bash
   git clone https://github.com/Mice-Tailor-Infra/sing-box-config-templates.git
   cd sing-box-config-templates
   ```

2. **Setup environment:**
   ```bash
   cp .env.example .env
   # Edit .env with your subscription URLs
   vim .env
   ```

3. **Generate and run:**
   ```bash
   set -a && source .env && set +a
   envsubst < config.template.json > config.json
   sing-box run -c config.json
   ```

## 🌟 Key Technologies

- **Sing-box:** High-performance universal proxy platform
- **KernelSU:** Android root solution
- **GitHub Actions:** Automated CI/CD pipelines
- **Tencent EdgeOne:** Global CDN acceleration
- **EDNS Client Subnet:** Geographic DNS optimization
- **Infrastructure as Code:** Configuration management

## 🔗 Important Links

- **CDN Distribution:** [miceworld.top](https://miceworld.top)
- **Build Status:** Check individual repository Actions tabs
- **Documentation:** Available in each repository's README

## 📊 Repository Statistics

- **Total Repositories:** 8
- **Primary Languages:** Shell, Python, CSS, JSON
- **Active Projects:** 7 (excluding this meta repository)
- **License:** Most projects use MIT License

## 🤝 Contributing

Each repository has its own contribution guidelines. Generally:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

Please refer to individual repository documentation for specific guidelines.

## ⚠️ Disclaimer

These projects are for technical research and system engineering experiments only. Users should comply with local laws and regulations.

## 📄 License

Individual projects are licensed separately. Most use the MIT License. See each repository for details.

## 🙏 Acknowledgments

- [Sing-box](https://github.com/SagerNet/sing-box) - Universal proxy platform
- [reF1nd/sing-box](https://github.com/reF1nd/sing-box) - Android adaptation fork
- [KernelSU](https://github.com/KernelSU/KernelSU) - Android root solution
- [Magisk](https://github.com/topjohnwu/Magisk) - Android systemless interface

---

**Last Updated:** 2026-01-01

For questions or support, please open an issue in the relevant repository.