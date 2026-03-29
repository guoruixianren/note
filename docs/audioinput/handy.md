# Handy

> 免费、开源、可扩展的离线语音转文字桌面工具，支持 Windows、macOS、Linux。

## 基本信息

| 项目 | 详情 |
|------|------|
| GitHub | https://github.com/cjpais/handy |
| 官网 | https://handy.computer |
| 开发语言 | TypeScript / Electron |
| 开源协议 | MIT |
| 最新状态 | 积极维护（2024） |

## 支持平台

| 操作系统 | 支持情况 | 最低版本要求 |
|---------|:-------:|------------|
| Windows | ✅ | Windows 10 64位 |
| macOS | ✅ | macOS 12（Monterey） |
| Linux | ✅ | Ubuntu 20.04+ 等主流发行版 |

## 核心特性

- **跨平台**：真正的三平台支持，提供各平台安装包（Homebrew、Winget 均可用）
- **完全离线**：本地运行 Whisper 或 Parakeet 模型，隐私优先
- **快捷键触发**：全局快捷键录音，结束后自动粘贴文字到当前窗口
- **VAD 支持**：语音活动检测，静音自动停止录制
- **可扩展性**：插件式架构，开发者可扩展功能
- **多引擎支持**：同时支持 OpenAI Whisper 和 NVIDIA Parakeet 模型
- **剪贴板集成**：识别结果也可写入剪贴板备用

## 输入法框架依赖

**无需任何输入法框架**。Handy 通过各平台原生 API（Windows SendInput、macOS Accessibility API、Linux xdotool/ydotool）注入文字，不依赖 Fcitx、IBus 等框架。

## 语音引擎

| 引擎 | 说明 |
|------|------|
| OpenAI Whisper | 支持 tiny / base / small / medium / large 系列 |
| NVIDIA Parakeet | 更快的推理速度，需要兼容硬件 |

- 模型在首次使用时自动下载到本地
- 支持 GPU 加速（CUDA）

## 语言支持

- Whisper 支持 **99+ 种语言**，含中文、英文、日文、法文等
- 多语言混合识别能力良好

## 费用与授权

| 项目 | 说明 |
|------|------|
| 是否免费 | ✅ 完全免费 |
| 是否开源 | ✅ MIT 许可 |
| 商业使用 | ✅ MIT 可商用 |
| 有无广告 | ❌ 无广告 |

## 安装方式

```bash
# macOS（Homebrew）
brew install --cask handy

# Windows（Winget）
winget install handy

# Linux / 通用
# 前往 GitHub Releases 下载对应平台包
# https://github.com/cjpais/handy/releases
```

## 输入速度参考

- 实际延迟取决于模型大小和硬件配置
- 推荐使用 GPU 并选择 `small` 或 `base` 模型以平衡速度和准确率
- 在现代 CPU 上使用 `base` 模型，延迟约 1–3 秒

## 优缺点

### 优点
- 真正跨三平台，安装便捷（Homebrew/Winget）
- 完全开源，代码透明
- 双引擎支持（Whisper + Parakeet）
- MIT 协议，商业项目可放心使用
- 社区活跃，持续更新

### 缺点
- Electron 应用，内存占用相对较高
- 本地 Whisper 推理对 CPU 较低配置的机器速度较慢
- Linux 下的文字注入依赖 xdotool/ydotool，偶有兼容性问题

## 适用场景

- 需要跨平台一致体验的用户
- 开发者希望二次开发或扩展功能
- 注重隐私、拒绝云端服务的用户
- macOS / Windows 主力用户

---

*参考：[Handy GitHub](https://github.com/cjpais/handy) | [官网](https://handy.computer)*
