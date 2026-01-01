# Mice-Tailor-Infra Organization / Mice-Tailor-Infra 组织

[English](#english) | [中文](#中文)

---

<a name="english"></a>

## English

### 🎯 Organization Overview

Welcome to **Mice-Tailor-Infra**, a collection of infrastructure projects focused on network proxy solutions, Android system customization, and automated build systems. Our projects emphasize automation, cloud synchronization, and cross-platform compatibility.

This organization maintains several interconnected projects that form a complete ecosystem for network proxy management, particularly focused on the **Sing-box** proxy platform and Android system enhancements.

### 📚 Repository Portfolio

#### 🔧 Core Proxy Infrastructure

##### [sing-box-ksu-module](https://github.com/Mice-Tailor-Infra/sing-box-ksu-module)
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

##### [sing-box-config-templates](https://github.com/Mice-Tailor-Infra/sing-box-config-templates)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/sing-box-config-templates/blob/main/LICENSE)

Infrastructure as Code (IaC) approach to managing Sing-box configurations across multiple platforms.

**Key Features:**
- Decoupled secrets architecture (no credentials in Git)
- Multi-branch environment isolation (main/mobile/win11)
- Dynamic configuration rendering via `envsubst`
- Optimized routing logic for different platforms
- VoLTE/VoNR physical isolation for Android

**Languages:** JSON, Shell | **Homepage:** [Config Templates](https://miceworld.top/sing-box-config-templates/main/config.template.json)

##### [sing-box-auto-build-ci](https://github.com/Mice-Tailor-Infra/sing-box-auto-build-ci)
[![CI Status](https://img.shields.io/badge/Build-Automated-orange)](https://github.com/Mice-Tailor-Infra/sing-box-auto-build-ci/actions)

Automated CI/CD pipeline for building [reF1nd/sing-box](https://github.com/reF1nd/sing-box) binaries across multiple platforms.

**Supported Platforms:**
- Android (arm64)
- Linux (amd64: v1/v3/v4, arm64)
- Windows (amd64: v1/v3/v4, arm64)
- macOS (amd64, arm64)

**Features:** Includes `with_gvisor`, `with_quic`, `with_dhcp`, `with_wireguard`, `with_utls`, `with_clash_api`, `with_tailscale`, `with_acme`

**Languages:** Shell | **Homepage:** [Build CI](https://miceworld.top/sing-box-auto-build-ci/)

#### 📦 Package Distribution

##### [cagedbird-pacman-repo](https://github.com/Mice-Tailor-Infra/cagedbird-pacman-repo)
[![Arch](https://img.shields.io/badge/Arch-x86__64%20%7C%20aarch64-blue?logo=arch-linux)](https://miceworld.top/cagedbird-pacman-repo/)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/cagedbird-pacman-repo/blob/main/LICENSE)

Private Pacman repository hosting CI/CD auto-built **sing-box-ref1nd** packages, distributed globally via Tencent Cloud EdgeOne (Anycast).

**Features:**
- Automated package builds from CI/CD pipeline
- Global CDN acceleration via Tencent EdgeOne
- Micro-architecture optimizations (x86_64 v3, aarch64)
- Support for Arch Linux x86_64 and aarch64

**Languages:** Package Repository | **Homepage:** [Pacman Repo](https://miceworld.top/cagedbird-pacman-repo/)

#### 🌐 Network Optimization

##### [fcm-hosts-ksu](https://github.com/Mice-Tailor-Infra/fcm-hosts-ksu)

KernelSU/Magisk module for systemless hosts management with auto-sync capability.

**Key Features:**
- Soft link strategy (`/system/etc/hosts` → `/data/adb/fcm-hosts/hosts`)
- Cloud sync with FCM dual IP pool
- Scheduled updates every 3 hours
- Localhost protection and SELinux compatibility

**Languages:** Shell | **Homepage:** [FCM Hosts KSU](https://miceworld.top/fcm-hosts-ksu/)

##### [fcm-hosts-next](https://github.com/Mice-Tailor-Infra/fcm-hosts-next)
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

#### 🌍 Organization Website

##### [mice-tailor-infra.github.io](https://github.com/Mice-Tailor-Infra/mice-tailor-infra.github.io)

GitHub Pages site for the organization.

**Languages:** CSS, HTML

---

### 🏗️ Architecture Overview

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

### 🚀 Quick Start

#### For Android Users (KernelSU/Magisk)

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

#### For Arch Linux Users

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

#### For Configuration Template Users

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

### 🌟 Key Technologies

- **Sing-box:** High-performance universal proxy platform
- **KernelSU:** Android root solution
- **GitHub Actions:** Automated CI/CD pipelines
- **Tencent EdgeOne:** Global CDN acceleration
- **EDNS Client Subnet:** Geographic DNS optimization
- **Infrastructure as Code:** Configuration management

### 🔗 Important Links

- **CDN Distribution:** [miceworld.top](https://miceworld.top)
- **Build Status:** Check individual repository Actions tabs
- **Documentation:** Available in each repository's README

### 📊 Repository Statistics

- **Total Repositories:** 8
- **Primary Languages:** Shell, Python, CSS, JSON
- **Active Projects:** 7 (excluding this meta repository)
- **License:** Most projects use MIT License

### 🤝 Contributing

Each repository has its own contribution guidelines. Generally:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

Please refer to individual repository documentation for specific guidelines.

### ⚠️ Disclaimer

These projects are for technical research and system engineering experiments only. Users should comply with local laws and regulations.

### 📄 License

Individual projects are licensed separately. Most use the MIT License. See each repository for details.

### 🙏 Acknowledgments

- [Sing-box](https://github.com/SagerNet/sing-box) - Universal proxy platform
- [reF1nd/sing-box](https://github.com/reF1nd/sing-box) - Android adaptation fork
- [KernelSU](https://github.com/KernelSU/KernelSU) - Android root solution
- [Magisk](https://github.com/topjohnwu/Magisk) - Android systemless interface

---

<a name="中文"></a>

## 中文

### 🎯 组织概述

欢迎来到 **Mice-Tailor-Infra**，这是一个专注于网络代理解决方案、Android 系统定制和自动化构建系统的基础设施项目集合。我们的项目强调自动化、云同步和跨平台兼容性。

本组织维护多个相互关联的项目，形成一个完整的网络代理管理生态系统，特别专注于 **Sing-box** 代理平台和 Android 系统增强。

### 📚 仓库目录

#### 🔧 核心代理基础设施

##### [sing-box-ksu-module](https://github.com/Mice-Tailor-Infra/sing-box-ksu-module)
[![CI Build](https://img.shields.io/badge/CI-Passing-brightgreen)](https://github.com/Mice-Tailor-Infra/sing-box-ksu-module/actions)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/sing-box-ksu-module/blob/main/LICENSE)

为 Android 设备深度定制的高性能 Sing-box 运行时环境，支持 KernelSU 模块化部署。

**核心特性：**
- 云端配置同步
- 二进制文件集中管理
- 系统级符号链接实现全局命令
- 支持通过 `sbc update` 热更新
- 凭证隔离（使用 `.env` 文件）

**语言：** Shell | **主页：** [文档](https://miceworld.top/sing-box-ksu-module/)

##### [sing-box-config-templates](https://github.com/Mice-Tailor-Infra/sing-box-config-templates)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/sing-box-config-templates/blob/main/LICENSE)

采用基础设施即代码（IaC）方法管理跨平台 Sing-box 配置。

**核心特性：**
- 解耦的密钥架构（Git 中不包含凭证）
- 多分支环境隔离（main/mobile/win11）
- 通过 `envsubst` 动态渲染配置
- 针对不同平台优化的路由逻辑
- Android 端 VoLTE/VoNR 物理隔离

**语言：** JSON, Shell | **主页：** [配置模板](https://miceworld.top/sing-box-config-templates/main/config.template.json)

##### [sing-box-auto-build-ci](https://github.com/Mice-Tailor-Infra/sing-box-auto-build-ci)
[![CI Status](https://img.shields.io/badge/Build-Automated-orange)](https://github.com/Mice-Tailor-Infra/sing-box-auto-build-ci/actions)

自动化 CI/CD 流水线，用于构建跨多平台的 [reF1nd/sing-box](https://github.com/reF1nd/sing-box) 二进制文件。

**支持平台：**
- Android (arm64)
- Linux (amd64: v1/v3/v4, arm64)
- Windows (amd64: v1/v3/v4, arm64)
- macOS (amd64, arm64)

**特性：** 包含 `with_gvisor`、`with_quic`、`with_dhcp`、`with_wireguard`、`with_utls`、`with_clash_api`、`with_tailscale`、`with_acme`

**语言：** Shell | **主页：** [构建 CI](https://miceworld.top/sing-box-auto-build-ci/)

#### 📦 软件包分发

##### [cagedbird-pacman-repo](https://github.com/Mice-Tailor-Infra/cagedbird-pacman-repo)
[![Arch](https://img.shields.io/badge/Arch-x86__64%20%7C%20aarch64-blue?logo=arch-linux)](https://miceworld.top/cagedbird-pacman-repo/)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/cagedbird-pacman-repo/blob/main/LICENSE)

私有 Pacman 仓库，托管 CI/CD 自动构建的 **sing-box-ref1nd** 软件包，通过腾讯云 EdgeOne (Anycast) 全球加速分发。

**特性：**
- CI/CD 流水线自动构建软件包
- 腾讯云 EdgeOne 全球 CDN 加速
- 微架构优化（x86_64 v3, aarch64）
- 支持 Arch Linux x86_64 和 aarch64

**语言：** 软件包仓库 | **主页：** [Pacman 仓库](https://miceworld.top/cagedbird-pacman-repo/)

#### 🌐 网络优化

##### [fcm-hosts-ksu](https://github.com/Mice-Tailor-Infra/fcm-hosts-ksu)

KernelSU/Magisk 模块，用于无系统化 hosts 管理，支持自动同步。

**核心特性：**
- 软链接策略（`/system/etc/hosts` → `/data/adb/fcm-hosts/hosts`）
- 与 FCM 双栈 IP 池云端同步
- 每 3 小时自动更新
- 保护本地主机定义并兼容 SELinux

**语言：** Shell | **主页：** [FCM Hosts KSU](https://miceworld.top/fcm-hosts-ksu/)

##### [fcm-hosts-next](https://github.com/Mice-Tailor-Infra/fcm-hosts-next)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/Mice-Tailor-Infra/fcm-hosts-next/blob/main/LICENSE)

自动化的 Google Firebase Cloud Messaging (FCM) 优选 hosts 项目，采用分布式边缘探测。

**架构：**
- **数据采集：** GitHub Actions (美国) 配合 EDNS Client Subnet (ECS)
- **真机校验：** 阿里云自托管 Runner
- **负载均衡：** Top 12 IP 采用 Round-Robin + Shuffle

**可用文件：**
- `fcm_dual.hosts` - 双栈负载均衡版（推荐）
- `fcm_ipv6.hosts` - 纯 IPv6 版本
- `fcm_ipv4.hosts` - 纯 IPv4 版本

**语言：** Python | **主页：** [FCM Hosts Next](https://miceworld.top/fcm-hosts-next/)

#### 🌍 组织网站

##### [mice-tailor-infra.github.io](https://github.com/Mice-Tailor-Infra/mice-tailor-infra.github.io)

组织的 GitHub Pages 网站。

**语言：** CSS, HTML

---

### 🏗️ 架构概览

```
┌─────────────────────────────────────────────────────────────┐
│                    Mice-Tailor-Infra                        │
│                    基础设施生态系统                          │
└─────────────────────────────────────────────────────────────┘
                              │
                 ┌────────────┼────────────┐
                 │            │            │
         ┌───────▼──────┐ ┌──▼────────┐ ┌▼──────────────┐
         │   构建 CI    │ │  配置模板  │ │     分发      │
         │              │ │           │ │               │
         └───────┬──────┘ └──┬────────┘ └┬──────────────┘
                 │            │           │
         ┌───────▼────────────▼───────────▼──────┐
         │   sing-box-ksu-module (Android)      │
         └───────────────────────────────────────┘
                 │
         ┌───────▼───────┐
         │  CDN (EdgeOne)│
         │  miceworld.top │
         └───────────────┘
```

### 🚀 快速开始

#### Android 用户（KernelSU/Magisk）

1. **安装 sing-box-ksu-module：**
   ```bash
   # 从以下地址下载最新版本
   # https://github.com/Mice-Tailor-Infra/sing-box-ksu-module/releases
   # 通过 Magisk/KernelSU Manager 安装
   # 重启设备
   ```

2. **配置订阅：**
   ```bash
   sbc edit
   # 添加你的订阅链接
   sbc start
   ```

3. **可选：安装 FCM hosts 优化：**
   ```bash
   # 下载 fcm-hosts-ksu 模块
   # 通过 Magisk/KernelSU Manager 安装
   # 重启设备
   ```

#### Arch Linux 用户

1. **添加 CagedBird 仓库：**
   ```bash
   # 编辑 /etc/pacman.conf，在顶部添加：
   [cagedbird-repo]
   SigLevel = Optional TrustAll
   Server = https://miceworld.top/cagedbird-pacman-repo/$arch
   ```

2. **安装 sing-box：**
   ```bash
   sudo pacman -Syy
   sudo pacman -S sing-box-ref1nd
   ```

#### 配置模板用户

1. **克隆模板仓库：**
   ```bash
   git clone https://github.com/Mice-Tailor-Infra/sing-box-config-templates.git
   cd sing-box-config-templates
   ```

2. **设置环境：**
   ```bash
   cp .env.example .env
   # 使用你的订阅链接编辑 .env
   vim .env
   ```

3. **生成并运行：**
   ```bash
   set -a && source .env && set +a
   envsubst < config.template.json > config.json
   sing-box run -c config.json
   ```

### 🌟 关键技术

- **Sing-box：** 高性能通用代理平台
- **KernelSU：** Android root 解决方案
- **GitHub Actions：** 自动化 CI/CD 流水线
- **腾讯云 EdgeOne：** 全球 CDN 加速
- **EDNS Client Subnet：** 地理 DNS 优化
- **基础设施即代码：** 配置管理

### 🔗 重要链接

- **CDN 分发：** [miceworld.top](https://miceworld.top)
- **构建状态：** 查看各个仓库的 Actions 标签页
- **文档：** 各仓库的 README 中提供

### 📊 仓库统计

- **仓库总数：** 8
- **主要语言：** Shell、Python、CSS、JSON
- **活跃项目：** 7 个（不含本元仓库）
- **许可证：** 大多数项目使用 MIT 许可证

### 🤝 贡献

每个仓库都有自己的贡献指南。一般流程：

1. Fork 仓库
2. 创建功能分支
3. 进行修改
4. 提交 Pull Request

具体指南请参考各仓库文档。

### ⚠️ 免责声明

这些项目仅供技术研究和系统工程实验使用。用户应遵守当地法律法规。

### 📄 许可证

各项目独立授权。大多数使用 MIT 许可证。详情请查看各仓库。

### 🙏 致谢

- [Sing-box](https://github.com/SagerNet/sing-box) - 通用代理平台
- [reF1nd/sing-box](https://github.com/reF1nd/sing-box) - Android 适配分支
- [KernelSU](https://github.com/KernelSU/KernelSU) - Android root 解决方案
- [Magisk](https://github.com/topjohnwu/Magisk) - Android 无系统化接口

---

**Last Updated / 最后更新：** 2026-01-01

For questions or support, please open an issue in the relevant repository.  
如有问题或需要支持，请在相关仓库中提交 issue。
