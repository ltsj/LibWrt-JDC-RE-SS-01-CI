<div align="center">

# LibWrt for 京东云雅典娜 (JDCloud RE-SS-01)

基于 [LiBwrt-op/openwrt-6.x](https://github.com/LiBwrt-op/openwrt-6.x) (`main-nss` 分支) 自动化构建的纯净固件。

集成 Qualcomm IPQ6000 满血 NSS 硬件加速驱动，每周自动同步上游源码与插件源。

[![Build LiBwrt OpenWrt](https://github.com/ltsj/LibWrt-JDC-RE-SS-01-CI/actions/workflows/build-openwrt.yml/badge.svg)](https://github.com/ltsj/LibWrt-JDC-RE-SS-01-CI/actions/workflows/build-openwrt.yml)
[![GitHub release](https://img.shields.io/github/v/release/ltsj/LibWrt-JDC-RE-SS-01-CI?color=blue&label=Release)](https://github.com/ltsj/LibWrt-JDC-RE-SS-01-CI/releases)
[![License](https://img.shields.io/badge/license-GPL%20v2-green.svg)](LICENSE)

</div>

---

## 📌 硬件与固件信息

- **设备型号**：京东云无线宝 雅典娜 (JDCloud RE-SS-01)
- **处理器架构**：Qualcomm IPQ6000 (AArch64 Cortex-A53 4核)
- **加速驱动**：Qualcomm NSS ECM 满血硬件流控分载加速
- **内核版本**：Linux 6.12.x
- **包管理工具**：APK (Alpine Package Keeper)
- **默认管理 IP**：`192.168.1.1`
- **默认用户密码**：`root` / 无密码

---

## 📦 预装组件清单

### 🎨 界面与主题
- **`luci-theme-argon`**：现代质感响应式主题，支持暗黑模式自适应
- **`luci-theme-bootstrap`**：OpenWrt 经典轻量扁平主题
- **`luci-app-argon-config`**：Argon 主题自定义设置面板（背景壁纸、毛玻璃透明度、主题配色等）

### 🛡️ 网络与安全
- **`luci-app-firewall`**：NFTables 防火墙管理与端口转发
- **`luci-app-upnp`**：通用即插即用 (UPnP / NAT-PMP) 自动端口映射服务
- **`luci-app-smartdns`**：SmartDNS 本地分流与防污染 DNS 加速核心及配置面板
- **`luci-app-sqm`**：SQM 智能队列拥塞管理 (Cake / FQ-CoDel 流控)
- **`luci-app-eqos`**：基于局域网 IP / MAC 地址的智能带宽流控限速

### ⚙️ 系统与设备管理
- **`luci-app-package-manager`**：网页端可视化 APK 软件包安装与仓库管理
- **`luci-app-diskman`**：磁盘挂载与存储设备管理（集成 Btrfs 与 lsblk 驱动）
- **`luci-app-filemanager`**：Web 网页端文件浏览与管理工具
- **`luci-app-wol`**：网络唤醒 (Wake-on-LAN) 局域网主机控制
- **`luci-app-autoreboot`**：系统定时计划自动重启服务

---

## 🚀 自动化构建与发布

- **定时同步**：每周一 UTC 00:00（北京时间 08:00）全自动拉取上游主干最新代码与最新 Feeds 插件构建。
- **手动触发**：支持在 GitHub 仓库的 **Actions -> Build LiBwrt OpenWrt -> Run workflow** 页面随时手动构建。
- **构建产物**：构建成功后将自动发布至 [Releases](https://github.com/ltsj/LibWrt-JDC-RE-SS-01-CI/releases) 页面：
  - `*factory.bin`：从 U-Boot 刷入或全新重装系统使用。
  - `*sysupgrade.bin`：在 OpenWrt 网页后台直接保留配置升级使用。
