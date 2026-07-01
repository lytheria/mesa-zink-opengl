
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Termux](https://img.shields.io/badge/Environment-Termux-alpha.svg)](https://termux.dev)
[![Platform: Android](https://img.shields.io/badge/Platform-Android-green.svg)](https://www.android.com)
[![GitHub Profile](https://img.shields.io/badge/GitHub-Profile-181717?style=flat&logo=github)](https://github.com/lytheria)

# <img src="https://github.com/user-attachments/assets/75ac34ae-e999-4b35-8f4b-95b8a3dcb9c9" width="5%"> Mesa3D Graphics Drivers for Termux</img>

A comprehensive guide and compilation toolkit for deploying, configuring, and optimizing the **Mesa 3D Graphics Library** within **Termux** environments. This project aims to bridge the gap between Android's hardware limitations and Linux desktop emulation, enabling high-performance hardware acceleration (OpenGL, Vulkan, OpenCL) for proot-distros, hardware-level wrappers, and standalone X11/Wayland applications.

---

## 📖 Table of Contents

- [Introduction](#introduction)
- [Key Features](#key-features)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Configuration & Environment Variables](#configuration--environment-variables)
- [Supported Hardware Drivers](#supported-hardware-drivers)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

---

## 📑 Introduction

**Mesa** is the backbone of open-source graphics stacks on Linux. When operating within **Termux** (and extended rootless environments like PRoot or Chroot), standard Android Vulkan or OpenGL ES drivers are often inaccessible to native Linux binaries. 

This repository provides optimized configuration patterns, build scripts, and environment setups to implement Mesa drivers—such as **Zink** (OpenGL over Vulkan), **Turnip** (Open-source Vulkan for Adreno), and **VirGL** (Virtual 3D GPU)—directly on Android devices via Termux. This enables running complex pipelines, hardware-accelerated emulators (e.g., Box64, Wine, Winlator components), and full desktop environments with optimal frame rates.

---

## 🔑 Key Features

* **Turnip + Zink Pipeline:** Unlock true desktop OpenGL 4.6 compliance on Qualcomm Snapdragon devices by layering Zink on top of the open-source Turnip Vulkan driver.
* **Software Rendering Fallbacks:** Integrated configurations for **LLVMpipe** and **Softpipe** when hardware-level drivers are unavailable or incompatible.
* **VirGL Server Support:** Streamlined configurations for virtualized GPU acceleration across host-guest translation layers.
* **Optimized Performance Tweaks:** Fine-tuned system properties and environment variables tailored for Android's unique memory and thermal management constraints.

---

## 📂 Prerequisites

Before proceeding, ensure your Termux environment is up to date and the essential repositories are subscribed to:

```bash
pkg update && pkg upgrade -y
pkg install x11-repo tur-repo -y
pkg install termux-x11 && wget https://github.com/lytheria/mesa-termux/releases/download/23.x.x/mesa-zink-opengl-23.0.4_aarch64.deb && find ~ -name "mesa-zink-opengl-23.0.4_aarch64.deb" -exec dpkg -i {} +
```
---

## 🧑‍💻 Author
Managed and maintained by ([@lytheria Celestine Velicia](https://github.com/lytheria)).

If you have questions, feature requests, or want to collaborate on optimizing Mesa for Termux, feel free to open an issue or connect via my [GitHub Profile](https://github.com/lytheria).
---
