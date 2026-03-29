# Buzz

> 功能丰富的跨平台离线音频转录与翻译应用，基于 Whisper 系列引擎，支持文件导入和实时转录。

## 基本信息

| 项目 | 详情 |
|------|------|
| GitHub | https://github.com/chidiwilliams/buzz |
| 官网 | https://buzzcaptions.com |
| 开发语言 | Python（PyQt5 GUI） |
| 开源协议 | MIT |
| 最新状态 | 积极维护（2024） |

## 支持平台

| 操作系统 | 支持情况 | 最低版本要求 |
|---------|:-------:|------------|
| Windows | ✅ | Windows 10 64位 |
| macOS | ✅ | macOS 11（含 Apple Silicon/ARM） |
| Linux | ✅ | Ubuntu 20.04+；Snap 包可用 |

## 核心特性

- **文件批量转录**：支持导入音频（MP3、WAV、M4A 等）和视频（MP4 等）文件进行转录
- **实时麦克风转录**：支持实时语音转文字
- **字幕导出**：导出 TXT、SRT（带时间戳）、VTT 等格式
- **翻译功能**：可将识别结果直接翻译为英文（Whisper 内置翻译）
- **说话人识别**：支持音频分离和说话人标注（Speaker Diarization）
- **GPU 加速**：支持 CUDA 和 Apple Metal 加速
- **转录编辑器**：内置转录文本查看、搜索、内联编辑功能
- **多引擎支持**：Whisper、Faster-Whisper、Whisper.cpp，可选 OpenAI API

## 输入法框架依赖

**无需任何输入法框架**。Buzz 主要定位为转录工具，结果以文本编辑器展示或导出文件，不依赖 Fcitx/IBus 等框架。

## 语音引擎

| 引擎 | 特点 |
|------|------|
| OpenAI Whisper | 原始 Whisper，稳定可靠 |
| Faster-Whisper | 速度提升 2–4 倍，内存更省 |
| Whisper.cpp | C++ 实现，低内存，适合嵌入 |
| OpenAI API | 云端推理，速度最快 |

```
可用模型大小：
tiny / base / small / medium / large / large-v2 / large-v3
```

## 语言支持

- Whisper 支持 **99+ 种语言**
- 自动语言检测
- 内置**翻译到英文**功能
- 中文、日文、韩文等非拉丁语系支持良好

## 费用与授权

| 项目 | 说明 |
|------|------|
| 是否免费 | ✅ 完全免费 |
| 是否开源 | ✅ MIT 许可 |
| 商业使用 | ✅ MIT 可商用 |
| 有无广告 | ❌ 无广告 |

## 安装方式

```bash
# macOS
brew install --cask buzz

# Linux（Snap）
sudo snap install buzz

# Windows
# 前往 GitHub Releases 下载 .exe 安装包
# https://github.com/chidiwilliams/buzz/releases

# Python 安装
pip install buzz-captions
```

## 输入速度参考

| 场景 | 速度说明 |
|------|---------|
| 实时麦克风 | 中等延迟（1–5 秒，取决于模型） |
| 文件转录（1 分钟音频） | base 模型：~10–30 秒（CPU） |
| GPU 加速（CUDA/Metal） | 速度提升 3–5 倍 |
| OpenAI API | 文件转录约 5–15 秒 |

## 优缺点

### 优点
- **MIT 协议**，商业友好
- 真正的三平台支持，含 Apple Silicon
- 多种 Whisper 引擎可选（性能调优灵活）
- 字幕/字幕导出功能完善（SRT/VTT）
- 说话人识别功能独特
- GPU 加速支持好（CUDA + Metal）
- Snap 包方便 Linux 安装

### 缺点
- 实时听写体验不如 NexTalk/Nerd-Dictation 流畅（有批量处理延迟）
- 主要定位是转录工具，不擅长"边说边打字"场景
- 大模型 + CPU 环境下文件转录耗时较长
- 功能较多，界面对纯粹"语音打字"用户略显复杂

## 适用场景

- **视频创作者**：会议记录、播客字幕生成
- **记者/研究者**：采访录音转文字
- **多语言用户**：需要转录后翻译
- **字幕制作**：SRT/VTT 格式输出
- 需要说话人识别的场景

---

*参考：[Buzz GitHub](https://github.com/chidiwilliams/buzz) | [官网](https://buzzcaptions.com)*
