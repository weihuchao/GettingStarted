# GitHub Copilot CLI

官方文档：https://github.com/features/copilot/cli

简介：GitHub Copilot CLI 为命令行环境提供 AI 助手，便于在终端中生成代码片段、解释代码与完成重复性任务。

安装（macOS，使用 Homebrew）：

```bash
brew install copilot-cli
```

安装后验证：

```bash
copilot --version
copilot --help
```

## 首次配置


```bash
copilot
/login

/model sonnet-4.5           # 切换模型
/fleet Implement X across models
```

## 常用命令速查表

| 命令              | 说明                           |
|------------------|--------------------------------|
| `/login`         | 登录 GitHub 账户               |
| `/help` 或 `?`   | 查看所有可用命令               |
| `/clear`         | 清除当前对话历史               |
| `/compact`       | 压缩对话历史，释放上下文空间   |
| `/context`       | 查看当前 token 使用情况        |
| `/usage`         | 查看本次会话的 token 统计      |
| `/model`         | 切换 AI 模型                   |
| `/agent`         | 切换或调用自定义 Agent         |
| `/review`        | 对当前代码改动进行审查         |
| `/mcp add`       | 添加 MCP 服务器                |
| `/add-dir /path` | 添加信任目录                   |
| `/cwd /path`     | 切换工作目录                   |
| `/delegate <任务>`| 将任务委托给 Copilot Coding Agent |
| `/resume`        | 恢复历史会话                   |
| `/feedback`      | 提交反馈                       |


#### 查询与会话管理
```
copilot --version          # 查看版本
copilot --help             # 帮助
/session                    # 查看当前会话信息（在 Copilot CLI 输入）
/session checkpoints        # 列出检查点
/session files              # 查看临时文件
```

### 快速交互（示例）
```
# 进入交互式 Copilot 会话（在仓库根目录）
copilot

# 计划与实现
/plan Add feature X
/delegate Implement tests for feature X

# 让 Copilot 解释当前文件或代码段（在会话中）
/explain why this function throws errors
```

### 权限与工具配置

```bash
# 允许特定 shell 命令或拒绝
copilot --allow-tool='shell(git:*)' --deny-tool='shell(git push)'

# 重置已批准的工具
/reset-allowed-tools
```
## 命令行参数速查

| 参数                           | 说明                       |
|--------------------------------|----------------------------|
| `copilot`                      | 启动交互会话               |
| `copilot -p "查询"`            | 单次查询后退出             |
| `copilot --continue`           | 继续最近一次会话           |
| `copilot --resume`             | 从历史会话中选择恢复       |
| `copilot --autopilot`          | 以自动驾驶模式启动         |
| `copilot --yolo`               | 允许所有工具权限（谨慎）   |
| `copilot --allow-all`          | 同上                       |
| `copilot help`                 | 查看完整帮助               |
