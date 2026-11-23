

# LocalOCR v6.0

**轻量、开源透明、纯离线的 Windows 双引擎多语言 OCR 桌面工具**  
**Lightweight, Transparent, 100% Offline Dual-Engine Multilingual OCR Tool for Windows**

![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0078D6?style=flat-square&logo=windows)
![Version](https://img.shields.io/badge/Version-v6.0-blueviolet?style=flat-square)
![Size](https://img.shields.io/badge/Package%20Size-~27KB-success?style=flat-square)
![Offline](https://img.shields.io/badge/Mode-100%25%20Offline-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

[🇨🇳 中文文档](#chinese-doc) | [🇺🇸 English Documentation](#english-doc)

</div>

---

<a id="chinese-doc"></a>
## 🇨🇳 中文文档

### 📖 项目简介

**LocalOCR v6.0** 是一款专为 Windows 10 / 11 设计的**纯离线、免登录、无次数限制**的多语言图片与 PDF 文字识别桌面工具。整个发布包仅约 **27KB**，全部由明文脚本（PowerShell / Batch / Python）构成，无任何捆绑与隐私上传风险。

软件采用**双引擎架构**：开箱即用 Windows 原生 OCR 引擎，同时支持一键部署基于 RapidOCR (PaddleOCR ONNX) 的本地深度学习专业引擎。针对**台版竖排书籍、繁体文献、影印版 PDF、数据表格**及**多语种学习资料**进行了深度优化。

> 📸 *提示：你可以在此处插入软件主界面及竖排/表格识别效果截图，例如 `![screenshot](docs/screenshot.png)`。*

---

### ✨ 核心特性

- **🔒 纯离线与完全透明**
  - 识别过程 100% 在本地运行，无需登录、无试用限制、不上传任何文件到云端。
  - 仅在首次按需安装系统语言包或部署专业引擎时需要联网，配置完成后即可永久断网使用。
  - 源码完全明文可见，安全放心。
- **⚙️ 双引擎自由切换**
  - **Windows 原生引擎**：直接调用系统内置 OCR，零依赖、解压即用。
  - **RapidOCR 专业引擎**：基于 PaddleOCR ONNX 深度学习模型，自带独立环境一键部署脚本（支持国内镜像加速），预缓存简中、繁中、英语及意/法/西/德多语种模型，高精度应对复杂排版。
- **📚 台版竖排书 & 繁体字自由组合**
  - **独立排版模式**：支持「横排」「竖排（右→左，适用于台版书/古籍）」「竖排（左→右）」，自动进行竖列聚类并按正确阅读顺序重组段落，告别行序错乱。
  - **独立繁体开关**：一键切换繁体模型，横排港台文献、表格或竖排书籍均可按需自由搭配。
- **📄 影印版 PDF 与智能表格识别**
  - **PDF 分页识别**：直接打开或拖入影印版 PDF，支持自定义页码范围（如 `1-5` 或 `1,3,8-10`），识别过程中可随时暂停或停止。
  - **智能表格提取**：支持「图文+表格分区」「纯表格模式」「普通纯文本」三种模式；输出支持 **TSV（直接粘贴进 Excel）**、**Markdown 表格**及对齐纯文本，并可一键导出为 `CSV` 或 UTF-8 `TXT`。
- **⚡ 顺手的交互与图像增强**
  - **局部框选识别**：直接在预览图上按住鼠标左键拉框，精准识别局部区域，无需反复裁剪。
  - **内置图像预处理**：支持一键去底色（优化发黄扫描件）、自动放大、智能去除中文字符间多余空格（同时保留英文及欧语词间空格）。
  - **多样化输入**：支持拖放图片/PDF、`Win + Shift + S` 截图后 `Ctrl + V` 秒识别，以及一键**批量识别整个文件夹**。

---

### ⚖️ 双引擎对比

| 特性 | Windows 原生引擎 | RapidOCR 专业引擎 |
| :--- | :--- | :--- |
| **安装需求** | 免安装、零依赖、解压即用 | 首次需运行一键部署脚本创建独立环境 |
| **离线运行** | 100% 离线 | 部署并缓存模型后 100% 离线 |
| **识别精度** | 清晰印刷体表现优秀 | 深度学习模型，复杂背景/古籍/表格精度更高 |
| **语言支持** | 取决于系统已安装的 Windows OCR 语言包（含简/繁中、英、意、法、西、德，亦可在系统设置添加日、韩等） | 内置预缓存简中、繁中、英语、意/法/西/德四套模型 |
| **适用场景** | 日常截图、快速轻量化提取 | 影印版 PDF、台版竖排书、复杂表格、高准确度需求 |

---

### 🚀 快速上手

#### 1. 环境要求
- **操作系统**：Windows 10 / Windows 11（支持 64 位 / 32 位）

#### 2. 安装与启动
1. 从本仓库的 [Releases](../../releases) 下载 `LocalOCR_Windows_v6.zip`（或克隆本仓库）。
2. **完整解压**压缩包到任意目录（⚠️ 请勿直接在压缩软件预览窗口中双击运行）。
3. 双击根目录下的 **`Start_LocalOCR.bat`** 即可启动软件，默认可直接使用 Windows 原生离线引擎。

#### 3. 按需扩展功能（可选）
- **安装多语言系统包**：在软件界面点击安装按钮，或右键以管理员身份运行 **`Install_Languages_Admin.bat`**，可一键补齐繁中（`zh-TW`/`zh-HK`）、英语、意大利语、法语、西班牙语、德语等微软官方 OCR 语言包。安装完成后在软件内点击「刷新」即可离线切换。
- **部署 RapidOCR 专业引擎**：在软件界面点击「安装专业引擎」，或双击运行 **`Install_ProEngine.bat`**。脚本将自动创建独立运行环境并下载缓存所需离线模型，完成后即可在界面顶部自由切换双引擎。

---

### 📂 项目结构

```text
LocalOCR_Win_v6/
├── Start_LocalOCR.bat            # 主程序启动入口（推荐日常使用）
├── Debug_Start.bat               # 调试模式启动入口（保留终端日志以便排查问题）
├── Install_Languages_Admin.bat   # Windows 官方 OCR 语言包一键安装入口（需管理员权限）
├── Install_ProEngine.bat         # RapidOCR 专业深度学习引擎一键部署入口
├── README.txt                    # 本地简易说明文档
└── app/
    ├── LocalOCR.ps1              # 主界面与核心 OCR / 排版 / 表格处理逻辑 (PowerShell)
    ├── InstallLanguages.ps1      # 系统语言包安装脚本
    ├── InstallProEngine.ps1      # RapidOCR 独立环境与模型缓存部署脚本
    └── pro_ocr_worker.py         # RapidOCR 本地推理工作进程 (Python)
```

---

### ❓ 常见问题 (FAQ)

- **双击 `Start_LocalOCR.bat` 闪退或没有反应？**
  - 请确认已将压缩包**完整解压**，而非在压缩包内直接双击。
  - 请尝试双击 **`Debug_Start.bat`** 运行，终端窗口会保留详细报错信息，方便你排查或在 [Issues](../../issues) 中反馈。
- **系统提示安全警告（Windows SmartScreen）怎么办？**
  - 由于脚本文件未进行商业数字签名，Windows 首次运行时可能会弹出提示。点击「更多信息」→「仍要运行」即可，所有脚本均为明文，运行前可随时用记事本审查。
- **如何添加日语、韩语等其他识别语言？**
  - 使用 Windows 原生引擎时，只需打开「Windows 设置 → 时间和语言 → 语言和区域」，添加对应语言并下载其“基本输入/光学字符识别”组件，回到软件点击「刷新」即可离线识别。

---

### 📄 开源协议

本项目基于 [MIT License](LICENSE) 开源，欢迎免费使用、分享或提交 PR / Issue 一起改进。

---
---

<a id="english-doc"></a>
## 🇺🇸 English Documentation

### 📖 Overview

**LocalOCR v6.0** is a **100% offline, login-free, and unlimited** multilingual OCR desktop application for Windows 10 / 11. Weighing in at only **~27KB**, the entire tool consists of transparent, plain-text scripts (PowerShell, Batch, and Python) with zero bloatware and zero cloud uploads—keeping your private documents strictly on your machine.

Built with a **Dual-Engine Architecture**, it works out of the box using the native Windows OCR engine, while also offering a one-click installer for a local **RapidOCR (PaddleOCR ONNX)** deep-learning engine. Version 6.0 brings major enhancements for **vertical books (Right-to-Left), Traditional Chinese, scanned PDFs, and structured tables**.

> 📸 *Tip: Add screenshots of the UI, vertical text recognition, and table extraction here, e.g., `![screenshot](docs/screenshot.png)`.*

---

### ✨ Key Features

- **🔒 100% Offline & Transparent**
  - All recognition runs locally—no account login, no daily quotas, and no cloud uploads.
  - Internet access is only needed optionally during initial language pack or Pro Engine setup; afterward, it works completely air-gapped.
  - Plain-text scripts allow you to inspect every line of code before running.
- **⚙️ Dual-Engine Flexibility**
  - **Windows Native Engine**: Zero dependencies, no installation required—just unzip and run.
  - **RapidOCR Pro Engine**: Powered by PaddleOCR ONNX models. Features a one-click setup script that creates an isolated environment and pre-caches offline models for Simplified Chinese, Traditional Chinese, English, and major European languages (IT/FR/ES/DE).
- **📚 Vertical Layout & Traditional Chinese (Independent Controls)**
  - **Flexible Reading Order**: Supports Horizontal, Vertical (Right-to-Left for traditional/Taiwanese books & historical texts), and Vertical (Left-to-Right). Automatically clusters vertical columns and reconstructs text in the proper reading order.
  - **Independent Traditional Chinese Toggle**: Freely combine Traditional Chinese recognition with either horizontal documents/tables or vertical books.
- **📄 Scanned PDF & Smart Table Recognition**
  - **Scanned PDF Support**: Open or drag-and-drop PDFs directly. Supports custom page ranges (e.g., `1-5` or `1,3,8-10`) with pause/stop controls during batch processing.
  - **Smart Table Extraction**: Choose between *Mixed (Text + Table)*, *Table Only*, and *Plain Text* modes. Format results as **TSV (paste directly into Excel)**, **Markdown Tables**, or aligned plain text, and export to `CSV` or UTF-8 `TXT` in one click.
- **⚡ Productivity & Image Preprocessing**
  - **Region Selection (Crop-to-OCR)**: Click and drag directly on the image preview to OCR a specific area without cropping files manually.
  - **Built-in Image Enhancement**: One-click background removal (great for yellowed/noisy scans), auto-upscaling, and smart CJK spacing cleanup (removes extra spaces between Chinese characters while preserving word spacing in English/European text).
  - **Multiple Input Methods**: Drag & drop images/PDFs, paste screenshots via `Win + Shift + S` → `Ctrl + V`, or **batch process an entire folder**.

---

### ⚖️ Engine Comparison

| Feature | Windows Native Engine | RapidOCR Pro Engine |
| :--- | :--- | :--- |
| **Setup** | Zero dependencies, ready out of the box | One-click script sets up an isolated environment |
| **Offline Capability** | 100% Offline | 100% Offline once models are cached |
| **Accuracy** | Great for clean printed text | Deep-learning models for complex layouts, scans & tables |
| **Languages** | Any installed Windows OCR language pack (CN/TW/HK, EN, IT, FR, ES, DE; plus JA/KO/etc. via Windows Settings) | Pre-cached models for Simplified CN, Traditional CN, EN, IT/FR/ES/DE |
| **Best For** | Quick screenshots & lightweight daily OCR | Scanned PDFs, vertical books, complex tables & high accuracy |

---

### 🚀 Quick Start

#### 1. System Requirements
- **OS**: Windows 10 / Windows 11 (64-bit & 32-bit supported)

#### 2. Installation & Launch
1. Download `LocalOCR_Windows_v6.zip` from [Releases](../../releases) (or clone this repository).
2. **Extract the entire archive** to a local folder (⚠️ Do not run scripts directly from inside the ZIP viewer).
3. Double-click **`Start_LocalOCR.bat`** to launch the GUI and start using the Windows Native OCR engine immediately.

#### 3. Optional Upgrades
- **Install Additional System Languages**: Click the language install button in the app or run **`Install_Languages_Admin.bat`** (requires Administrator privileges) to install official Microsoft OCR language packs (Traditional Chinese `zh-TW`/`zh-HK`, English, Italian, French, Spanish, German). Click **Refresh** in the app when finished.
- **Deploy RapidOCR Pro Engine**: Click the Pro Engine install button in the app or run **`Install_ProEngine.bat`**. The script automatically builds an isolated environment and caches the offline models so you can toggle between both engines anytime.

---

### 📂 Project Structure

```text
LocalOCR_Win_v6/
├── Start_LocalOCR.bat            # Main GUI launcher
├── Debug_Start.bat               # Debug launcher (keeps console output visible for troubleshooting)
├── Install_Languages_Admin.bat   # Installs Windows OCR language packs (Admin required)
├── Install_ProEngine.bat         # One-click installer for RapidOCR Pro Engine
├── README.txt                    # Bundled quick-reference readme
└── app/
    ├── LocalOCR.ps1              # Core GUI, OCR orchestration, layout & table logic (PowerShell)
    ├── InstallLanguages.ps1      # Windows language pack installation script
    ├── InstallProEngine.ps1      # RapidOCR environment & model caching script
    └── pro_ocr_worker.py         # RapidOCR local inference worker (Python)
```

---

### ❓ FAQ & Troubleshooting

- **Nothing happens or the window closes immediately when clicking `Start_LocalOCR.bat`?**
  - Make sure you have **fully extracted** the ZIP file first.
  - Run **`Debug_Start.bat`** instead to view detailed console logs, which can help diagnose the issue or be attached when opening an [Issue](../../issues).
- **Windows SmartScreen warning appears on first launch?**
  - Because these are unsigned local scripts, Windows may show a standard warning. Click **More info → Run anyway**. Since all files are plain text, feel free to review the source code beforehand.
- **Can I add Japanese, Korean, or other languages?**
  - Yes! For the Windows Native Engine, go to **Windows Settings → Time & language → Language & region**, add your desired language along with its OCR feature, then click **Refresh** inside LocalOCR.

---

### 📄 License

This project is open-sourced under the [MIT License](LICENSE). Contributions, issues, and feature requests are always welcome!
