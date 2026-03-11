[Xuan酱部署](https://ycnezwebj31p.feishu.cn/docx/MVomdT4tWoeEnmxFFEAcsHGpnph)

- [方舟 Coding Plan](https://www.volcengine.com/activity/codingplan)
  - [百炼Coding Plan](https://cn.aliyun.com/benefit/scene/codingplan?from_alibabacloud=)
- [ClawHub](https://clawhub.ai/)
- 



# 初始化

```bash
curl -fsSL https://openclaw.ai/install.sh | bash

cat <<EOF >> ~/.zshrc

export PATH="/Users/huchaoclaw/.local/share/fnm/node-versions/v24.14.0/installation/bin:\$PATH"
EOF

openclaw onboard
openclaw doctor
openclaw doctor --fix

# 查看网关状态
openclaw gateway status

# 启动/停止网关
openclaw gateway start
openclaw gateway stop

# 查看当前配置的模型
openclaw models list
openclaw models status

# skills
openclaw skills

# update
openclaw update
npm update -g openclaw

# channels
openclaw channels add
openclaw channels list
openclaw channels login --channel whatsapp
# 给自己发消息就可以了


# Hook
openclaw hooks list
openclaw hooks disable boot-md
```

## 基本配置

### 模型配置

```bash
# https://docs.siliconflow.cn/cn/usercases/use-siliconcloud-in-OpenClaw
# https://docs.siliconflow.cn/cn/userguide/quickstart
https://api.siliconflow.cn/v1
# https://cloud.siliconflow.cn/me/models
deepseek-ai/DeepSeek-V3.2
◇  Endpoint ID
│  custom-api-siliconflow-cn
◇  Model alias (optional)
│  DSV32
```

### channels

```bash
openclaw channels login
https://wa.me/qr/RUIX4ZWL3KHNP1

# https://docs.openclaw.ai/tools/web
# https://docs.openclaw.ai/zh-CN/tools/web
```

### Install missing skill dependencies

```bash
◇  Install missing skill dependencies
│  🔐 1password, 📰 blogwatcher, 🧩 clawhub, 🐙 github, 🎮 gog, 📍 goplaces, 📦 mcporter, 📊 model-usage, 🎙️ openai-whisper, 🧾 summarize, 🎞️ video-frames, 📱 wacli


◇  Install failed: clawhub — spawn pnpm ENOENT
spawn pnpm ENOENT
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills
│

################################################################################################

◇  Installed goplaces
│
◇  Install failed: mcporter — spawn pnpm ENOENT
spawn pnpm ENOENT
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills

################################################################################################

◇  Install failed: model-usage (exit 1) — Error: Failed to load formula: steipete/tap/codexbar
Error: Failed to load formula: steipete/tap/codexbar
steipete/tap/codexbar: formula requires at least a URL
Warning: Treating steipete/tap/codexbar as a cask.
Error: This software does not run on macOS versions older than Sonoma.
Warning: You are using macOS 13.
We (and Apple) do not provide support for this old version.
You may have better luck with MacPorts which supports older versions of macOS:
  https://www.macports.org

This is a Tier 3 configuration:
  https://docs.brew.sh/Support-Tiers#tier-3
You can report Tier 3 unrelated issues to Homebrew/* repositories!
Read the above document before opening any issues or PRs.
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills

################################################################################################

◇  Install failed: openai-whisper (exit 1) — Error: openai-whisper: An unsatisfied requirement failed this build.
Warning: You are using macOS 13.
We (and Apple) do not provide support for this old version.
You may have better luck with MacPorts which supports older versions of macOS:
  https://www.macports.org

```

## Hooks Configured

```bash
│  ◻ 🚀 boot-md (Run BOOT.md on gateway startup)
│  ◻ 📎 bootstrap-extra-files (Inject additional workspace bootstrap files via glob/path patterns)
│  ◻ 📝 command-logger (Log all command events to a centralized audit file)
│  ◻ 💾 session-memory (Save session context to memory when /new or /reset command is issued)

◇  Hooks Configured ─────────────────────────╮
│                                            │
│  Enabled 2 hooks: boot-md, session-memory  │
│                                            │
│  You can manage hooks later with:          │
│    openclaw hooks list                     │
│    openclaw hooks enable <name>            │
│    openclaw hooks disable <name>           │
│                                            │
├────────────────────────────────────────────╯
```


# 📚 OpenClaw 2026.3.8 操作命令参考

### 🦞 核心命令概览

```bash
# 查看版本
openclaw --version

# 查看帮助（完整）
openclaw --help

# 开启聊天
openclaw tui
```


### 🚪 网关管理 (Gateway)
```bash
openclaw gateway status    # 查看状态
openclaw gateway start     # 启动
openclaw gateway stop      # 停止
openclaw gateway restart   # 重启
openclaw gateway --force   # 强制启动
openclaw health            # 健康检查
openclaw logs              # 查看日志
```

### 📡 通道管理 (Channels)
```bash
openclaw channels list                     # 列出通道
openclaw channels add                      # 添加通道
openclaw channels login --channel whatsapp # 登录WhatsApp
openclaw channels status                   # 通道状态
```

### 🤖 助手和会话管理
```bash
openclaw agent --message "查看日历"        # 直接与助手交互
openclaw sessions                         # 列出会话
openclaw agents list                      # 列出子助手
```

### ⏰ 定时任务 (Cron)
```bash
openclaw cron list                        # 列出任务
openclaw cron add --name "提醒" --schedule "0 9 * * *"
openclaw cron status                      # 任务状态
```

### 🧠 AI模型管理
```bash
openclaw models list      # 列出模型
openclaw models status    # 模型状态
openclaw models scan      # 扫描模型
```

### 🛠️ 技能管理
```bash
openclaw skills list      # 列出技能
openclaw skills check     # 检查技能
openclaw skills inspect   # 查看技能详情
```

### 🔗 钩子管理 (Hooks)
```bash
openclaw hooks list       # 列出钩子
openclaw hooks enable     # 启用钩子
openclaw hooks disable    # 禁用钩子
```

### 🗄️ 内存管理
```bash
openclaw memory search "关键词"    # 搜索记忆
openclaw memory reindex            # 重新索引
```

### 🔐 安全和配置
```bash
openclaw configure        # 交互配置
openclaw doctor           # 健康检查
openclaw doctor --fix     # 自动修复
openclaw setup            # 初始化
openclaw reset            # 重置配置
```

### ⚙️ 系统和健康
```bash
openclaw system heartbeat     # 心跳检查
openclaw update check         # 检查更新
openclaw update apply         # 手动更新
```

### 📊 监控和调试
```bash
openclaw dashboard            # Web控制面板
openclaw --log-level debug    # 调试模式
```

---

### 💡 实用示例

**日常使用工作流：**
```bash
# 1. 检查并启动服务
openclaw gateway status || openclaw gateway start

# 2. 登录WhatsApp（如果未连接）
openclaw channels login --channel whatsapp

# 3. 检查定时任务
openclaw cron list
```

**故障排除工作流：**
```bash
# 完整的健康检查
openclaw doctor
openclaw doctor --fix

# 查看详细日志
openclaw --log-level debug gateway start
```

**开发模式：**
```bash
# 以开发模式启动（隔离配置）
openclaw --dev gateway start
openclaw --dev channels login --channel whatsapp
```

---

### 📝 使用建议

1. **先检查再操作**：`openclaw gateway status` → `openclaw doctor`
2. **多通道支持**：可以同时连接WhatsApp、Telegram、Discord等
3. **定时任务**：非常适合计划性检查和提醒
4. **开发测试**：使用`--dev`避免影响生产配置
5. **命令组合**：将常用操作组合成脚本

---

### 🧩 ClawHub集成（技能市场）

```bash
# 浏览技能库
npx clawhub

# 搜索技能
npx clawhub search github

# 安装技能
npx clawhub install github

# 更新所有技能
npx clawhub update --all
```

---

### 🔗 资源链接

- 官方文档：https://docs.openclaw.ai/cli
- GitHub仓库：https://github.com/openclaw/openclaw  
- 社区Discord：https://discord.com/invite/clawd
- 技能市场：https://clawhub.com


## 其他知识

### npm VS pnpm VS Bun

1. npm (Node Package Manager)
定位：Node.js 官方默认工具，生态最稳、兼容性最好。

2. pnpm (Performant npm)
节省空间：相同版本的包在磁盘上只存一份。
速度快：比 npm 快得多，且原生支持高效的 Monorepo 工作流。 

3. Bun
定位：一个新兴的全栈 JavaScript 运行时，它不仅是包管理器，还集成了运行环境、测试工具和打包工具。
原理：使用 Zig 语言编写，针对性能进行了底层优化，并行处理任务。
极致速度：安装速度比 npm 快达 30 倍，甚至大幅超越 pnpm。