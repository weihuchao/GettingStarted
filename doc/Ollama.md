# 多工具对比

| 工具          | 定位                   | 核心特点                                                     | 适用人群                                                | 平台支持                      | 上手难度                  |
| ------------- | ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------- | ----------------------------- | ------------------------- |
| **llama.cpp** | 底层推理引擎           | 纯 C/C++ 实现，极致轻量化，支持 CPU/Metal/CUDA，是很多工具的底层依赖 | 开发者、极客、需要二次封装的人                          | 全平台（Linux/macOS/Windows） | 高（命令行 + 编译配置）   |
| **Ollama**    | 模型管理 + 运行工具    | 封装了 llama.cpp 等引擎，一键拉取 / 运行模型，支持 API 调用，生态丰富 | 普通用户、开发者、想快速跑模型的人                      | 全平台                        | 低（一行命令启动）        |
| **LM Studio** | 可视化桌面客户端       | 图形界面，一键下载 / 运行 / 调试模型，支持 OpenAI 兼容 API，适合本地调试 | 非技术用户、产品经理、快速原型开发                      | macOS/Windows/Linux           | 极低（拖拽 + 点击）       |
| **MLX LM**    | Apple Silicon 专属框架 | 基于 Apple MLX 框架，专为 M 系列芯片优化，利用 Metal 加速，性能在 Mac 上极强 | Mac 用户、Apple 生态开发者、需要在 Mac 上高效跑模型的人 | 仅 macOS（Apple Silicon）     | 中（Python API + 命令行） |



# Ollama

- https://ollama.com/
- https://docs.ollama.com/
- [模型库](https://ollama.com/library)

## 基本使用

### 安装

```bash
# MacOS
curl -fsSL https://ollama.com/install.sh | sh
# Windows
irm https://ollama.com/install.ps1 | iex

curl http://localhost:11434/
```

### 启动大模型

```bash
# https://ollama.com/library/llama3.1
ollama run llama3.1
ollama run llama3.1 --verbose
# https://ollama.com/library/deepseek-r1
ollama run deepseek-r1
ollama run deepseek-r1 --verbose

--think
--think=false
```

### 会话中的命令

总结下来有:

```bash
/clear              # 清除对话并新建一个对话
/set verbose        # 启动状态信息可以看到一些数据统计, 可以很好的查看 TOKEN 的生成数量
# https://ollama.com/blog/thinking
/set think          # 开启思考
/set nothink        # 关闭思考
```


```bash
>>> /?
Available Commands:
  /set            Set session variables
  /show           Show model information
  /load <model>   Load a session or model
  /save <model>   Save your current session
  /clear          Clear session context
  /bye            Exit
  /?, /help       Help for a command
  /? shortcuts    Help for keyboard shortcuts

Use """ to begin a multi-line message.

$ ollama run deepseek-r1
>>> /set
Available Commands:
  /set parameter ...     Set a parameter
  /set system <string>   Set system message
  /set history           Enable history
  /set nohistory         Disable history
  /set wordwrap          Enable wordwrap
  /set nowordwrap        Disable wordwrap
  /set format json       Enable JSON mode
  /set noformat          Disable formatting
  /set verbose           Show LLM stats
  /set quiet             Disable LLM stats

# 不确定是否有效
# https://www.reddit.com/r/ollama/comments/1jym9jq/num_gpu_parameter_clearly_underrated/
# num_gpu 实际上是“上传到显存的层数”，而不是“GPU数量”。适用于模型大于显存时分层加载。
# 设置为 -1 会尝试将所有层都放入显存，若显存不足则可能崩溃或回退。
# 设置过低会很慢，过高会导致崩溃。建议根据显存使用率调整，目标是显卡90%左右显存利用率。
/set parameter num_gpu 0
/set parameter num_gpu 1
```


### 环境变量的设置

```bash
# https://docs.ollama.com/faq#how-can-i-enable-flash-attention
# 启用 Flash Attention 技术，显著减少大上下文窗口下的显存占用，提高推理效率
set OLLAMA_FLASH_ATTENTION=1

# https://docs.ollama.com/troubleshooting
# 开启 Ollama 的调试日志，输出更多详细信息，便于排查 GPU 发现、驱动、模型加载等问题。
$env:OLLAMA_DEBUG="1"
```



## Modelfile

https://docs.ollama.com/modelfile#valid-parameters-and-values

Modelfile 是 Ollama 用于创建和定制模型的配置文件。

它定义了基础模型、运行参数（如上下文长度、采样温度、停止词等）、系统消息、提示模板、对话历史、微调适配器和许可证等。

Modelfile 主要用于自定义模型行为和部署新模型，适用于需要调整模型参数、添加系统提示或集成微调适配器的场景。

类似于 Dockefile。

## Windows 使用 GPU

- 安装 CUDA: https://developer.nvidia.cn/cuda-downloads?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exe_local
- 使用 GPU: https://docs.ollama.com/gpu#gpu-selection

```bash
> nvidia-smi -L
GPU 0: NVIDIA GeForce RTX 3060 Laptop GPU (UUID: GPU-6ed55e4b-da9b-e21b-2f80-48dd4a87b039)

# 启动 GPU 0
set CUDA_VISIBLE_DEVICES=0
set CUDA_VISIBLE_DEVICES=GPU-6ed55e4b-da9b-e21b-2f80-48dd4a87b039
# 关闭 GPU
set CUDA_VISIBLE_DEVICES=-1

echo %CUDA_VISIBLE_DEVICES%

# 验证
set OLLAMA_DEBUG=1
ollama serve
# 查看日志中是否出现 llama_model_load: n_gpu_layers = ... 以及 detecting GPUs 的信息
```

# 其他知识

## Windows 上环境变量的设置

### 临时设置（窗口级别）

只在当前命令行窗口或 PowerShell 会话中有效，关闭窗口后失效


```bash
# 命令提示符（cmd）：
set OLLAMA_DEBUG=1
set OLLAMA_DEBUG="1"   // 加不加引号都可以，效果一致

# PowerShell：
$env:OLLAMA_DEBUG=1
$env:OLLAMA_DEBUG="1"  // 加不加引号都可以，效果一致

```

### 永久设置（系统/用户级别）

- 通过图形界面：

  1. 按下 Win + S，搜索“编辑系统环境变量”。
  2. 点击“环境变量”按钮。
  3. 在“用户变量”或“系统变量”栏添加或编辑变量。
  4. 修改 Path 时，点击“编辑”，添加新路径（如 `C:\Users\weihc\AppData\Local\Programs\Ollama`）。

- 通过命令行：

```bash
# 用户变量：
setx OLLAMA_DEBUG 1
setx Path "%Path%;C:\Users\weihc\AppData\Local\Programs\Ollama"

# 系统变量【需管理员权限】：
setx Path "%Path%;C:\Users\weihc\AppData\Local\Programs\Ollama" /M

# PowerShell 设置用户变量：
$oldPath = [Environment]::GetEnvironmentVariable("Path", "User")
$oldPath		# 查看具体的值
$newPath = "$oldPath;C:\Users\weihc\AppData\Local\Programs\Ollama"
[Environment]::SetEnvironmentVariable("Path", $newPath, "User")

# PowerShell 设置系统变量【需管理员权限】：
# "User" → "Machine"
$oldPath = [Environment]::GetEnvironmentVariable("Path", "Machine")
[Environment]::SetEnvironmentVariable("Path", $newPath, "Machine")
```
