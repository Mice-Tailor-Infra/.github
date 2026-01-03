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

##### [micetimer](https://github.com/Mice-Tailor-Infra/micetimer)

A systemd-style timer daemon for Android with WakeLock support, designed for high-reliability background task scheduling.

**Key Features:**
- Precision timing via Linux `timerfd` (CLOCK_BOOTTIME)
- Android WakeLock acquisition during task execution
- Centralized task management via `/data/adb/timers.d/`
- Lightweight Rust implementation

##### [fcm-hosts-ksu](https://github.com/Mice-Tailor-Infra/fcm-hosts-ksu)

KernelSU/Magisk module for systemless hosts management. Managed by **MiceTimer** for high-reliability updates.

**Key Features:**
- Skeleton architecture: `/system/etc/hosts` → `/data/adb/fcm-hosts/hosts`
- Managed by MiceTimer with **1-hour** sync interval
- Localhost protection and SELinux compatibility
- Installation dependency check for MiceTimer

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

#### 🎥 Multimedia & Streaming

##### [DroidV4L2](https://github.com/Mice-Tailor-Infra/DroidV4L2)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Documentation](https://img.shields.io/badge/docs-miceworld.top-green.svg)](https://miceworld.top/DroidV4L2/)

Professional tool that turns your Android device into a low-latency, high-quality wireless webcam for Linux.

**Key Features:**
- Ultra-Low Latency (< 50ms)
- Custom TinyRtspKt Engine
- High-performance Rust backend
- Codec hot-swapping

**Languages:** Kotlin, Rust | **Homepage:** [Documentation](https://miceworld.top/DroidV4L2/)

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

### 🌟 Key Technologies

- **Sing-box:** High-performance universal proxy platform
- **KernelSU:** Android root solution
- **GitHub Actions:** Automated CI/CD pipelines
- **Tencent EdgeOne:** Global CDN acceleration
- **EDNS Client Subnet:** Geographic DNS optimization
- **Infrastructure as Code:** Configuration management

### 🔗 Important Links

- **CDN Distribution:** [miceworld.top](https://miceworld.top)
- **Documentation:** See individual repository READMEs for detailed usage guides

### 📊 Repository Statistics

- **Total Repositories:** 10
- **Primary Languages:** Rust, Shell, Python, CSS, JSON, Kotlin
- **Active Projects:** 9 (excluding this meta repository)
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

##### [micetimer](https://github.com/Mice-Tailor-Infra/micetimer)

为 Android 深度定制的 Systemd 风格定时器守护进程，解决深睡计时不准问题并支持唤醒锁（WakeLock）。

**核心特性：**
- 基于 Linux `timerfd` (CLOCK_BOOTTIME) 实现精准计时
- 任务执行期间自动申请 Android 唤醒锁，防止 CPU 挂起
- 通过 `/data/adb/timers.d/` 集中管理所有模块的定时任务
- 极轻量、高性能的 Rust 原生实现

##### [fcm-hosts-ksu](https://github.com/Mice-Tailor-Infra/fcm-hosts-ksu)

KernelSU/Magisk 模块，用于无系统化 hosts 管理。现在由 **MiceTimer** 统一托管，实现高可靠同步。

**核心特性：**
- 空壳化架构：`/system/etc/hosts` → `/data/adb/fcm-hosts/hosts`
- 由 MiceTimer 驱动，同步频率提升至 **1 小时/次**
- 保护本地主机定义并兼容 SELinux
- 安装时自动检测 MiceTimer 依赖

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

#### 🎥 多媒体与流媒体

##### [DroidV4L2](https://github.com/Mice-Tailor-Infra/DroidV4L2)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Documentation](https://img.shields.io/badge/docs-miceworld.top-green.svg)](https://miceworld.top/DroidV4L2/)

专业的将 Android 设备转换为 Linux 低延迟、高质量无线网络摄像头的工具。

**核心特性：**
- 超低延迟 (< 50ms)
- 自研 TinyRtspKt 引擎
- 高性能 Rust 后端
- 编解码器热切换

**语言：** Kotlin, Rust | **主页：** [文档](https://miceworld.top/DroidV4L2/)

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

### 🌟 关键技术

- **Sing-box：** 高性能通用代理平台
- **KernelSU：** Android root 解决方案
- **GitHub Actions：** 自动化 CI/CD 流水线
- **腾讯云 EdgeOne：** 全球 CDN 加速
- **EDNS Client Subnet：** 地理 DNS 优化
- **基础设施即代码：** 配置管理

### 🔗 重要链接

- **CDN 分发：** [miceworld.top](https://miceworld.top)
- **文档：** 详细使用指南请查看各仓库的 README

### 📊 仓库统计

- **仓库总数：** 10
- **主要语言：** Rust, Shell, Python, CSS, JSON, Kotlin
- **活跃项目：** 9 个（不含本元仓库）
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

**Last Updated / 最后更新：** 2026-01-02

For questions or support, please open an issue in the relevant repository.  
如有问题或需要支持，请在相关仓库中提交 issue。