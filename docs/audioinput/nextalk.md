# NexTalk

> Linux 平台缺失的语音输入体验——美观、私密、离线，深度集成 Fcitx5。

## 基本信息

| 项目 | 详情 |
|------|------|
| GitHub | https://github.com/gonewx/nextalk |
| 官网 | https://nextalk.gonewx.com |
| 开发语言 | Dart（Flutter UI）+ Rust/C++ 后端 |
| 开源协议 | MIT |
| 最新状态 | 积极维护（2024） |

## 支持平台

| 操作系统 | 支持情况 | 说明 |
|---------|:-------:|------|
| Linux | ✅ | 主要目标平台，X11 和 Wayland 均支持 |
| Windows | ❌ | 不支持 |
| macOS | ❌ | 不支持 |

### Linux 系统版本要求

- Ubuntu 20.04+、Debian 11+、Arch Linux、Fedora 36+ 等主流发行版
- 需要 Fcitx5 已安装并运行（核心集成点）
- Wayland 或 X11 桌面环境均可

## 核心特性

- **极低延迟**：端到端延迟 < 20 毫秒，实时流式转录，文字近乎同步出现
- **Fcitx5 原生集成**：通过 Unix Domain Socket 直接注入文字，无剪贴板污染，适用于终端、IDE、所有 Fcitx5 支持的应用
- **完全离线**：基于 Sherpa-ONNX 流式 ASR，数据不出本机
- **悬浮胶囊 UI**：Flutter 构建的无边框半透明浮层，录音时显示，停止后自动消失
- **全局快捷键**：默认 `Alt+Space` 触发，无需切换应用
- **多麦克风支持**：可选择音频输入设备
- **剪贴板回退**：若 Fcitx5 不可用，自动回退到系统剪贴板模式

## 输入法框架依赖

| 框架 | 要求程度 |
|------|---------|
| **Fcitx5** | **强烈推荐/核心功能依赖**，无 Fcitx5 则退化为剪贴板模式 |
| Fcitx4 | ❌ 不支持 |
| IBus | ❌ 不支持 |
| ibus/RIME | ❌ 不支持 |

> NexTalk 的核心竞争力正是 Fcitx5 的直接集成，可绕过 xdotool/ydotool 等不稳定工具。

## 语音引擎

- **Sherpa-ONNX**（k2-fsa 项目，高性能 ONNX Runtime 推理）
- 支持语言：英文、普通话中文（可扩展）
- 模型在本地加载，完全离线

## 费用与授权

| 项目 | 说明 |
|------|------|
| 是否免费 | ✅ 完全免费 |
| 是否开源 | ✅ MIT 许可 |
| 商业使用 | ✅ MIT 可商用 |
| 有无广告 | ❌ 无广告 |

## 安装方式

```bash
# 方式一：下载预编译包
# 前往 GitHub Releases 下载对应发行版包
# https://github.com/gonewx/nextalk/releases

# 方式二：从源码构建
git clone https://github.com/gonewx/nextalk.git
cd nextalk
# 需要 Flutter SDK 和 Rust 工具链
flutter pub get
cargo build --release
```

**前提条件**：
```bash
# Ubuntu/Debian
sudo apt install fcitx5

# Arch Linux
sudo pacman -S fcitx5
```

## 优缺点

### 优点
- 目前 Linux 上延迟最低的语音输入工具之一（<20ms）
- Fcitx5 原生集成，支持 Wayland 下的终端和 IDE
- UI 优雅，不干扰工作流
- 完全开源且隐私安全

### 缺点
- **仅支持 Linux**，不跨平台
- **强依赖 Fcitx5**，非 Fcitx5 用户体验大打折扣
- 语言支持目前限于英文和普通话
- 社区相对较小

## 适用场景

- Linux 桌面用户（尤其是 Fcitx5 用户）
- 开发者在终端/IDE 中的语音输入
- 对延迟极度敏感的用户
- 注重隐私、拒绝联网的用户

---

*参考：[NexTalk GitHub](https://github.com/gonewx/nextalk) | [官网](https://nextalk.gonewx.com)*
