# Whisper-Writer

> 基于 OpenAI Whisper 的轻量级语音听写工具，支持多种录音模式，可完全离线运行。

## 基本信息

| 项目 | 详情 |
|------|------|
| GitHub | https://github.com/savbell/whisper-writer |
| 开发语言 | Python（PyQt5 GUI） |
| 开源协议 | GPL-3.0 |
| 最新状态 | 积极维护（2024） |

## 支持平台

| 操作系统 | 支持情况 | 最低版本要求 |
|---------|:-------:|------------|
| Windows | ✅ | Windows 10 64位，Python 3.8+ |
| macOS | ⚠️ | 需自行配置，部分功能受限 |
| Linux | ✅ | Python 3.8+，xdotool（X11）/ydotool（Wayland） |

## 核心特性

- **多种录音模式**：
  - 连续录音（Continuous）
  - 语音活动检测（VAD，静音自动停止）
  - 按键切换（Press-to-toggle）
  - 按住录音（Hold-to-record）
- **本地 Whisper 推理**：默认完全离线，所有模型本地运行
- **OpenAI API 可选**：可切换到 OpenAI 云端 API 提高速度（需 Key）
- **自动注入文字**：识别完成后自动输入到当前活动窗口
- **可配置设置**：支持自定义快捷键、模型大小、语言、后处理等
- **PyQt5 GUI**：现代化配置界面，操作直观

## 输入法框架依赖

| 环境 | 依赖 |
|------|------|
| Windows | pyautogui（系统 API） |
| Linux X11 | xdotool 或 pyautogui |
| Linux Wayland | ydotool（需 root 或特殊权限） |
| macOS | pyautogui（Accessibility 权限） |

**不依赖 Fcitx、IBus** 等输入法框架。

## 语音引擎

| 模式 | 引擎 | 说明 |
|------|------|------|
| 本地离线 | OpenAI Whisper（faster-whisper） | 支持 tiny/base/small/medium/large 系列 |
| 云端 | OpenAI Whisper API | 需要 API Key，速度更快 |

```
可用模型大小（本地）：
tiny    (~39 MB)  — 最快，精度较低
base    (~74 MB)  — 平衡选择
small   (~244 MB) — 推荐日常使用
medium  (~769 MB) — 高精度
large   (~1.5 GB) — 最高精度
```

## 语言支持

- Whisper 支持 **99+ 种语言**
- 支持自动语言检测
- 中文、英文、日文等主流语言效果良好

## 费用与授权

| 项目 | 说明 |
|------|------|
| 是否免费 | ✅ 完全免费 |
| 是否开源 | ✅ GPL-3.0 |
| 商业使用 | ⚠️ GPL-3.0 有传染性，商业使用需注意 |
| 有无广告 | ❌ 无广告 |

## 安装方式

```bash
# 克隆仓库
git clone https://github.com/savbell/whisper-writer.git
cd whisper-writer

# 安装依赖
pip install -r requirements.txt

# 运行
python run.py
```

**可选（GPU 加速）**：
```bash
pip install faster-whisper
# 需要 CUDA 环境
```

## 输入速度参考

| 模型 | CPU 速度（中等配置） | GPU 速度 |
|------|:------------------:|:-------:|
| tiny | ~0.5–1 秒 | <0.5 秒 |
| base | ~1–2 秒 | ~0.5 秒 |
| small | ~2–4 秒 | ~1 秒 |
| large | ~10+ 秒 | ~2–3 秒 |

*使用 OpenAI API 模式约 0.5–1 秒*

## 优缺点

### 优点
- 多种录音模式，灵活适配不同使用习惯
- 本地 Whisper 精度高，支持复杂口音
- 可在本地/云端之间灵活切换
- 活跃社区，持续更新
- 配置界面友好（PyQt5 GUI）

### 缺点
- GPL-3.0 对商业项目有约束
- 本地 large 模型在低配 CPU 上较慢
- macOS 支持不如 Windows/Linux 完善
- Wayland 下文字注入需要额外权限配置

## 适用场景

- 希望在本地/云端之间灵活切换的用户
- 对录音触发方式有不同需求的用户（VAD、按键等）
- Windows / Linux 用户日常语音输入
- 开发者集成 Whisper 到听写工作流

---

*参考：[Whisper-Writer GitHub](https://github.com/savbell/whisper-writer)*
