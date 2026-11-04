<div align="center">

# 🔥 Wild Kernels for OnePlus (Oppo/Realme)

[![KernelSU-Next](https://img.shields.io/badge/KernelSU_Next-Supported-green)](https://kernelsu-next.github.io/webpage/)
[![KernelSU](https://img.shields.io/badge/KernelSU-Supported-green)](https://kernelsu.org/)
[![Wild KSU](https://img.shields.io/badge/Wild_KSU-Not%20Supported-cb2431)](https://github.com/WildKernels/Wild_KSU/)
[![SUSFS](https://img.shields.io/badge/SUSFS-Integrated-orange?logo=gitlab)](https://gitlab.com/simonpunk/susfs4ksu)
[![OnePlusOSS Tracking Status](https://img.shields.io/badge/OnePlusOSS--Tracker-active-green)](https://github.com/WildKernels/OnePlus_KernelSU_SUSFS/blob/status-page/README.md)

</div>

---

## ⚠️ Disclaimer

Flashing this kernel will not void your warranty, but there is always a risk of bricking your device. Please make sure to:
- 💾 Back up your data
- 🧠 Understand the risks before proceeding

- I am **not responsible** for bricked devices, damaged hardware, or any issues that arise from using this kernel.

- **Please** do thorough research and fully understand the features added in this kernel before flashing it!

- By flashing this kernel, **YOU** are choosing to make these modifications. If something goes wrong, **do not blame me**!

<div align="center">
  
# **🚨 Proceed at your own risk!**

</div>

---

## 🔧 Available Kernels

<div align="center">

| Kernel | Repository | Status |
|--------|------------|--------|
| 🏗️ **GKI** | [GKI_KernelSU_SUSFS](https://github.com/WildKernels/GKI_KernelSU_SUSFS) | ✅ Active |
| 👑 **Sultan** | [Sultan_KernelSU_SUSFS](https://github.com/WildKernels/Sultan_KernelSU_SUSFS) | ✅ Active |
| 📱 **OnePlus/Oppo/Realme** | [OnePlus_KernelSU_SUSFS](https://github.com/WildKernels/OnePlus_KernelSU_SUSFS) | ✅ Active |
| 📱 **Samsung** | [Samsung_KernelSU_SUSFS](https://github.com/WildKernels/Samsung_KernelSU_SUSFS) | ✅ Active |
</div>

---

## 🔗 Additional Resources

- 🩹 [Kernel Patches](https://github.com/WildKernels/kernel_patches)
- ⚡ [Kernel Flasher](https://github.com/fatalcoder524/KernelFlasher)

---

## 📱 Device Compatibility

- Please verify the device compatibility before flashing here: [Compatibility_Info](https://github.com/WildKernels/OnePlus_KernelSU_SUSFS/blob/main/compatibility.md). 

---

## 📱 OnePlusOSS Repositories Tracking

- 📊 **Live Dashboard**: [OnePlus Repos Tracking & Changes](https://github.com/WildKernels/OnePlus_KernelSU_SUSFS/blob/status-page/README.md)
- ⏱️ **Update Frequency**: Every 2 hours (Automated)
---

## ✨ Features

- 🔐 **KernelSU / KernelSU-Next**: A root solution for Android GKI devices that works in kernel mode and grants root permission to userspace applications directly in kernel space
- 🔥 **WildKSU Manager Support**: Support for the Root Manager developed by our team with lots of customisations
- 🥷 **SUSFS**: An addon root hiding kernel patches and userspace module for KernelSU
- 🛡️ **BBG**: LSM-based Baseband Guard security to protect critical device partitions. abl/efisp can be added to whitelist for efisp exploit devices.
- 🛠️ **HMBIRD SCX**: Scheduler extensions for SM8750/MT6991 devices
- 🖧 **BBRv1**: Improved TCP congestion control
- 🖧 **BBRv3**: Improved TCP congestion control
- 🚦 **CAKE and PIE qdisc Support**: Better Net Schedulers
- ✅ **LTO**: Link Time Optimisation enabled
- 🚀 **Optimisation patches**: Memory, I/O, CPU scheduler, network and other general tunings
- 🌐 **TTL Target Support**: Network packet manipulation
- 🧱 **IP Set & IPv6 NAT Support**: Advanced firewall capabilities and IPv6 NAT Support
- ⚡️ **TMPFS XATTR / POSIX ACL**: Extended TMPFS support for meta modules and Mountify
- </> **Unicode Bypass Fix**: Prevent path traversal and other detections using non-printable Unicode codepoints [Experimental]
- 🖥️ **Droidspaces Support**: Support Portable Linux containers to run full Linux environments.
- 🔃 **NTSync**: Provide high-performance, low-latency synchronization primitives compatible with the Windows NT kernel API

---

## 🍴 This Fork (softpyscho) — OnePlus 12R build

Everything above comes from upstream WildKernels. This fork adds the following on branch [`op12r-5.15.197`](https://github.com/softpyscho/OnePlus_KernelSU_SUSFS/tree/op12r-5.15.197), building only the **OnePlus 12R (OP12r), Android 16, kernel 5.15.197**.

### ➕ Added features
- 🧠 **MGLRU on by default**: multi-gen LRU memory reclaim, fewer app reloads under memory pressure
- 🔀 **Kernel stack randomisation**: stack offset randomised on every syscall entry (`RANDOMIZE_KSTACK_OFFSET_DEFAULT`)
- 💾 **NTFS3**: read/write NTFS USB drives over OTG (exFAT, FAT and F2FS were already supported)
- 🖧 **BBRv3 as default** TCP congestion control, with **`fq`** as the default qdisc
- ⚡ **TCP Fast Open** (client + server) and **ECN** enabled by default

### 🔧 Build changes
- 📌 **Pinned versions** as workflow defaults: KernelSU-Next `b427a3f` (33405) and SUSFS android13-5.15 `f3ceb5d` (v2.3.0). KSUN `dev` has moved past the SUSFS fix patches, so unpinned builds fail.
- ✅ **Config check**: the build fails if any added setting is missing from the final kernel `.config`, or if the TCP defaults can't be patched.
- 🎯 **12R only**: every other device config is removed on this branch.

### 📦 Download
- Latest: [op12r-5.15.197-r1](https://github.com/softpyscho/OnePlus_KernelSU_SUSFS/releases/tag/op12r-5.15.197-r1). The SHA256 is in the release notes.
- Flash only if `uname -r` on your phone shows **5.15.197**, and back up your stock `boot.img` first.

### 🔁 Rebuild
Run **Build and Release OnePlus Kernels** on branch `op12r-5.15.197` with `op_model=A16`. The defaults already carry the pinned versions.

### ✔️ Check after flashing
```
cat /proc/sys/net/ipv4/tcp_congestion_control   # bbr3
cat /proc/sys/net/ipv4/tcp_fastopen             # 3
cat /sys/kernel/mm/lru_gen/enabled              # not 0x0000
```

---

## 📋 Installation Instructions

For GKI installation, please follow the official guide:

📖 **[KernelSU Installation Guide](https://kernelsu.org/guide/installation.html)**

You can also find Installation instructions in the release notes.

---

## 🌟 Special Thanks

**These amazing people help make this project possible! ❤️**

<div align="center">


| 🔧 **Project** | 👨‍💻 **Developer** | 🔗 **Link** |
|:---------------:|:----------------:|:-----------:|
| **KernelSU** | tiann | [![GitHub](https://img.shields.io/badge/GitHub-tiann-blue?style=flat-square&logo=github)](https://github.com/tiann/KernelSU) |
| **KernelSU-Next** | rifsxd | [![GitHub](https://img.shields.io/badge/GitHub-rifsxd-blue?style=flat-square&logo=github)](https://github.com/KernelSU-Next/KernelSU-Next) |
| **Magic-KSU** | 5ec1cff | [![GitHub](https://img.shields.io/badge/GitHub-5ec1cff-blue?style=flat-square&logo=github)](https://github.com/5ec1cff/KernelSU) |
| **SUSFS** | simonpunk | [![GitLab](https://img.shields.io/badge/GitLab-simonpunk-orange?style=flat-square&logo=gitlab)](https://gitlab.com/simonpunk/susfs4ksu.git) |
| **SUSFS Module** | sidex15 | [![GitHub](https://img.shields.io/badge/GitHub-sidex15-blue?style=flat-square&logo=github)](https://github.com/sidex15) |
| **Sultan Kernels** | kerneltoast | [![GitHub](https://img.shields.io/badge/GitHub-kerneltoast-blue?style=flat-square&logo=github)](https://github.com/kerneltoast) |
| **Baseband Guard** | vc-teahouse | [![GitHub](https://img.shields.io/badge/GitHub-vc--teahouse-blue?style=flat-square&logo=github)](https://github.com/vc-teahouse/Baseband-guard.git) |
| **Droidspaces** | ravindu644 | [![GitHub](https://img.shields.io/badge/GitHub-ravindu644-blue?style=flat-square&logo=github)](https://github.com/ravindu644/Droidspaces-OSS.git) |

</div>

*If you have contributed and are not listed here, please remind me!* 🙏

---

## 💬 Support

If you encounter any issues or need help, feel free to:
- 🐛 Open an issue in this repository
- 💬 Reach out to me directly

---

## 📱 Connect With Us

<div align="center">
  
[![Telegram](https://img.shields.io/badge/Telegram-fatalcoder524-blue?logo=telegram)](https://t.me/anonymous_yolo)
[![Telegram Group](https://img.shields.io/badge/Telegram-WildKernels-blue?logo=telegram)](https://t.me/WildKernelsTG)

</div>

---

## 💝 Donations

Any and all donations are appreciated!

PayPal: [paypal.me/fatalcoder524](https://paypal.me/fatalcoder524)

DM on Telegram for UPI donations!

