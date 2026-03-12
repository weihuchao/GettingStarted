# 多工具对比

| 工具          | 定位                   | 核心特点                                                     | 适用人群                                                | 平台支持                      | 上手难度                  |
| ------------- | ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------- | ----------------------------- | ------------------------- |
| **llama.cpp** | 底层推理引擎           | 纯 C/C++ 实现，极致轻量化，支持 CPU/Metal/CUDA，是很多工具的底层依赖 | 开发者、极客、需要二次封装的人                          | 全平台（Linux/macOS/Windows） | 高（命令行 + 编译配置）   |
| **Ollama**    | 模型管理 + 运行工具    | 封装了 llama.cpp 等引擎，一键拉取 / 运行模型，支持 API 调用，生态丰富 | 普通用户、开发者、想快速跑模型的人                      | 全平台                        | 低（一行命令启动）        |
| **LM Studio** | 可视化桌面客户端       | 图形界面，一键下载 / 运行 / 调试模型，支持 OpenAI 兼容 API，适合本地调试 | 非技术用户、产品经理、快速原型开发                      | macOS/Windows/Linux           | 极低（拖拽 + 点击）       |
| **MLX LM**    | Apple Silicon 专属框架 | 基于 Apple MLX 框架，专为 M 系列芯片优化，利用 Metal 加速，性能在 Mac 上极强 | Mac 用户、Apple 生态开发者、需要在 Mac 上高效跑模型的人 | 仅 macOS（Apple Silicon）     | 中（Python API + 命令行） |



# 基本资料和安装

- https://ollama.com/
- https://docs.ollama.com/
- [模型库](https://ollama.com/library)
- [OllaMan](https://ollaman.com/download)
  - https://ollaman.com/docs
  - https://ollaman.com/zh/docs


```bash
curl -fsSL https://ollama.com/install.sh | sh
curl http://localhost:11434/

ollama run llama3.1
```