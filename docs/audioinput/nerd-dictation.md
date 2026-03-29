# Nerd-Dictation

> 面向 Linux 极客的可脚本化离线语音输入工具，基于 Vosk，深度集成 Linux 工作流。

## 基本信息

| 项目 | 详情 |
|------|------|
| GitHub | https://github.com/ideasman42/nerd-dictation |
| 开发语言 | Python |
| 开源协议 | GPL-2.0 |
| 最新状态 | 维护中（稳定版本） |

## 支持平台

| 操作系统 | 支持情况 | 说明 |
|---------|:-------:|------|
| Linux | ✅ | 主要目标平台，X11 和 Wayland 均支持 |
| Windows | ❌ | 不支持 |
| macOS | ❌ | 不支持 |

### Linux 系统版本要求

- Python 3.7+
- 主流 Linux 发行版均可（Ubuntu 18.04+、Arch、Fedora 等）
- X11：需要 `xdotool`
- Wayland：需要 `ydotool` 或 `wtype`

## 核心特性

- **高度可脚本化**：纯 Python 实现，所有行为均可通过脚本自定义
- **完全离线**：基于 Vosk ASR 引擎，本地处理，隐私保护
- **极简设计**：命令行工具，无 GUI，适合自动化集成
- **自定义词典**：支持添加专业术语、首字母缩写词
- **文本后处理**：可用 Python 脚本对识别结果进行格式化（大写、标点等）
- **热键集成**：可配合 `sxhkd`、`xbindkeys` 等工具绑定快捷键
- **低资源占用**：Vosk 相比 Whisper 轻量，适合低配硬件

## 输入法框架依赖

| 环境 | 依赖工具 |
|------|---------|
| X11 | `xdotool`（模拟键盘输入） |
| Wayland | `ydotool` 或 `wtype` |
| 无 GUI | 可直接输出到 stdout，由脚本处理 |

**不依赖 Fcitx、IBus 等输入法框架**，直接通过工具模拟键盘事件。

## 语音引擎

- **Vosk**：轻量级流式 ASR 引擎，支持 50+ 种语言
- 模型需手动下载并指定路径
- 相比 Whisper 精度稍低，但延迟更低、资源占用更少

```bash
# 下载 Vosk 模型示例（英文小型模型）
wget https://alphacephei.com/vosk/models/vosk-model-small-en-us-0.15.zip
unzip vosk-model-small-en-us-0.15.zip
```

## 语言支持

- Vosk 支持 **50+ 种语言**，含英文、中文、法文、德文、俄文等
- 需要手动下载对应语言的 Vosk 模型

## 费用与授权

| 项目 | 说明 |
|------|------|
| 是否免费 | ✅ 完全免费 |
| 是否开源 | ✅ GPL-2.0 |
| 商业使用 | ⚠️ GPL-2.0 有传染性，衍生产品需同样开源 |
| 有无广告 | ❌ 无广告 |

## 安装方式

```bash
# 1. 安装依赖
pip install vosk
sudo apt install xdotool   # X11 用户
# sudo apt install ydotool  # Wayland 用户

# 2. 克隆仓库
git clone https://github.com/ideasman42/nerd-dictation.git
cd nerd-dictation

# 3. 下载 Vosk 模型（以英文为例）
# 放到 ~/.config/nerd-dictation/model/

# 4. 测试运行
./nerd-dictation begin &
sleep 5
./nerd-dictation end
```

## 输入速度参考

- Vosk 流式识别，延迟约 **200–500 ms**（小型模型 + 现代 CPU）
- 比 Whisper 本地推理更快，适合实时听写场景

## 优缺点

### 优点
- 极致可定制，适合喜欢折腾的开发者
- Vosk 轻量，低配硬件也能流畅运行
- 完全离线，零隐私风险
- 与 Linux 工具链（sxhkd、shell 脚本）深度集成

### 缺点
- **仅支持 Linux**，不跨平台
- 无 GUI，配置有一定门槛
- Vosk 识别精度低于 Whisper（尤其对口音、复杂语境）
- GPL-2.0 对商业项目有约束
- 中文识别效果不如专门的中文模型

## 适用场景

- Linux 高级用户、开发者
- 需要将语音输入集成到自动化工作流的场景
- 低配硬件（无 GPU）用户
- 喜欢命令行工具、自定义程度要求高的用户

---

*参考：[Nerd-Dictation GitHub](https://github.com/ideasman42/nerd-dictation)*
