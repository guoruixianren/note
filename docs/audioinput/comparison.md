# 流行语音输入法总对比

> 整理了 GitHub 上流行的开源/免费语音输入工具，涵盖操作系统支持、依赖框架、离线能力、商业友好度等多个维度。

## 工具一览

| 工具 | GitHub 地址 |
|------|-------------|
| VocoType | https://github.com/233stone/vocotype-cli |
| NexTalk | https://github.com/gonewx/nextalk |
| Handy | https://github.com/cjpais/handy |
| LazyTyper | https://lazytyper.com （非完全开源） |
| Nerd-Dictation | https://github.com/ideasman42/nerd-dictation |
| Whisper-Writer | https://github.com/savbell/whisper-writer |
| Buzz | https://github.com/chidiwilliams/buzz |

---

## 多维度对比表

### 操作系统支持

| 工具 | Windows | macOS | Linux |
|------|:-------:|:-----:|:-----:|
| VocoType | ✅ | ✅ | ❌（CLI 版可尝试） |
| NexTalk | ❌ | ❌ | ✅ |
| Handy | ✅ | ✅ | ✅ |
| LazyTyper | ✅ | ✅ | ❌ |
| Nerd-Dictation | ❌ | ❌ | ✅ |
| Whisper-Writer | ✅ | ⚠️（需自行配置） | ✅ |
| Buzz | ✅ | ✅（含 ARM） | ✅ |

### 系统版本要求

| 工具 | 最低系统要求 |
|------|-------------|
| VocoType | Windows 10+，macOS 11+；CLI 版需 Python 3.8+ |
| NexTalk | 主流 Linux 发行版（Ubuntu 20.04+、Arch 等） |
| Handy | Windows 10+，macOS 12+，主流 Linux 发行版 |
| LazyTyper | Windows 10+，macOS 11+ |
| Nerd-Dictation | Linux（X11 或 Wayland），xdotool（X11） |
| Whisper-Writer | Python 3.8+；Linux/Windows 均支持 |
| Buzz | Windows 10+，macOS 11+，Ubuntu 20.04+ |

### 输入法框架依赖

| 工具 | 框架依赖 |
|------|---------|
| VocoType | 无（直接注入剪贴板/模拟键盘） |
| NexTalk | **必须 Fcitx5**（原生集成，也支持剪贴板回退） |
| Handy | 无（跨平台 API 注入） |
| LazyTyper | 无（系统 API） |
| Nerd-Dictation | 无严格要求；X11 下使用 xdotool，Wayland 下使用 ydotool |
| Whisper-Writer | 无（pyautogui 模拟键盘输入） |
| Buzz | 无（文件/实时转录，结果可导出） |

### 语音识别引擎

| 工具 | 引擎 |
|------|------|
| VocoType | 本地私有引擎（Sherpa-ONNX 变体/自研） |
| NexTalk | Sherpa-ONNX（流式 ASR） |
| Handy | OpenAI Whisper / NVIDIA Parakeet |
| LazyTyper | 12 种 AI 模型（含 5 种离线：Whisper 系列等） |
| Nerd-Dictation | Vosk |
| Whisper-Writer | OpenAI Whisper（本地）/ OpenAI API（可选） |
| Buzz | Whisper / Faster-Whisper / Whisper.cpp |

### 离线/本地运行

| 工具 | 完全离线 | 本地模型 | 云端可选 |
|------|:-------:|:-------:|:-------:|
| VocoType | ✅ | ✅ | ❌ |
| NexTalk | ✅ | ✅ | ❌ |
| Handy | ✅ | ✅ | ❌ |
| LazyTyper | ✅（部分模型） | ✅（5 种） | ✅ |
| Nerd-Dictation | ✅ | ✅（Vosk） | ❌ |
| Whisper-Writer | ✅ | ✅ | ✅（OpenAI API） |
| Buzz | ✅ | ✅ | ✅ |

### 输入速度 / 延迟

| 工具 | 延迟 / 速度描述 |
|------|----------------|
| VocoType | 极低延迟，约 0.1 秒（官方宣称） |
| NexTalk | 端到端 < 20 ms（流式实时转录） |
| Handy | 中等，取决于模型大小及硬件 |
| LazyTyper | 快速，轻量级（~10 MB），官称 90%+ 准确率 |
| Nerd-Dictation | 低延迟（Vosk 流式），适合实时打字 |
| Whisper-Writer | 中等（本地 Whisper）；API 模式更快 |
| Buzz | 实时转录中等；大文件批量较慢 |

### 支持语言

| 工具 | 支持语言 |
|------|---------|
| VocoType | 中文（普通话）为主，英文 |
| NexTalk | 英文、普通话中文（Sherpa-ONNX 模型） |
| Handy | Whisper 支持的 99+ 语言 |
| LazyTyper | 多语言（Whisper 系列），含混合语言识别 |
| Nerd-Dictation | Vosk 支持的语言（50+） |
| Whisper-Writer | 99+ 语言（Whisper） |
| Buzz | 99+ 语言（Whisper），含翻译功能 |

### 是否免费

| 工具 | 免费 | 开源协议 |
|------|:----:|---------|
| VocoType | ✅ | 部分开源（CLI 版 MIT） |
| NexTalk | ✅ | MIT |
| Handy | ✅ | MIT |
| LazyTyper | ✅（无广告） | ❌（非完全开源） |
| Nerd-Dictation | ✅ | GPL-2.0 |
| Whisper-Writer | ✅ | GPL-3.0 |
| Buzz | ✅ | MIT |

### 商业使用友好度

| 工具 | 商业使用 | 说明 |
|------|:-------:|------|
| VocoType | ✅ | CLI 版 MIT，可商用 |
| NexTalk | ✅ | MIT，可商用 |
| Handy | ✅ | MIT，可商用 |
| LazyTyper | ⚠️ | 非完全开源，需确认许可协议 |
| Nerd-Dictation | ⚠️ | GPL-2.0，需注意传染性 |
| Whisper-Writer | ⚠️ | GPL-3.0，需注意传染性 |
| Buzz | ✅ | MIT，可商用 |

### 实时听写 vs 文件转录

| 工具 | 实时听写 | 文件转录 |
|------|:-------:|:-------:|
| VocoType | ✅ | ✅ |
| NexTalk | ✅ | ❌ |
| Handy | ✅ | ❌ |
| LazyTyper | ✅ | ❌ |
| Nerd-Dictation | ✅ | ❌ |
| Whisper-Writer | ✅ | ❌ |
| Buzz | ✅ | ✅（主要功能） |

### 特色功能

| 工具 | 特色亮点 |
|------|---------|
| VocoType | 中文优化、AI 润色、SRT 字幕导出、自定义词典 |
| NexTalk | Fcitx5 原生集成、Flutter 悬浮胶囊 UI、<20ms 延迟、Wayland 支持 |
| Handy | 跨平台、Whisper/Parakeet 双引擎、快捷键触发粘贴、高扩展性 |
| LazyTyper | 12 种 AI 模型、技术词汇/代码识别、混合语言、10 MB 轻量 |
| Nerd-Dictation | 高度可脚本化、Linux 深度集成、适合极客用户 |
| Whisper-Writer | 多种录音模式（VAD/连续/按键）、配置灵活 |
| Buzz | 字幕导出（SRT/VTT）、说话人识别、GPU 加速、翻译功能 |

---

## 快速选型建议

- **Linux + Fcitx5 用户**：首选 **NexTalk**，延迟最低，Wayland 原生支持
- **中文用户（Windows/macOS）**：首选 **VocoType**，中文优化最佳
- **跨平台 + 隐私优先**：选 **Handy** 或 **Buzz**
- **极客/开发者 Linux**：选 **Nerd-Dictation**，可深度定制
- **多语言/代码混合输入**：选 **LazyTyper**
- **字幕/文件转录场景**：选 **Buzz**
- **灵活配置 + Whisper**：选 **Whisper-Writer**

---

*更新时间：2026-03-29*
