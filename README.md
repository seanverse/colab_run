# Colab T4 Model Benchmarking

使用 Google Colab T4 GPU 测试开源小模型的基准的jupyter notebook评测项目。

## 环境

| 组件 | 说明 |
|------|------|
| **运行时** | Google Colab (云端 T4 GPU, 15GB VRAM) |
| **编辑器** | VSCode + Colab 扩展 |
| **目标** | 测试各种开源小模型的性能 |

## 前置要求

1. VSCode 安装 [Colab 扩展](https://marketplace.visualstudio.com/items?itemName=google-colab.colab)
2. Google 账号 (Colab 免费版可用 T4)
3. VSCode 中 `Ctrl+Shift+P` → `Colab: Connect to Colab` → 选择 T4 GPU 运行时

## 目录结构

```
colab_run/
├── README.md                          # 本文件
├── .claude/                           # Claude Code 项目配置
│   ├── CLAUDE.md                      # 项目指令
│   └── settings.json                  # 权限配置
├── tts_zh_en_sota_bench.ipynb         # TTS 中英文 SOTA 6模型评测
└── tts_outputs/                       # Colab 生成的音频 (gitignore)
```

## 当前任务

- [x] TTS 中英文 6模型评测 (ChatTTS, CosyVoice3, IndexTTS-1.5, OmniVoice, VoxCPM2, S1-Mini)
- [ ] ASR 语音识别模型评测
- [ ] LLM 小模型推理评测
- [ ] 图像生成模型评测

## 工作流

1. 在本项目中创建 `.ipynb` notebook
2. VSCode Colab 扩展连接到 Colab T4 运行时
3. 上传 notebook 到 Colab
4. 逐个 cell 运行，收集评测数据
5. 音频/结果文件下载回本地，notebook 提交 git

## 注意

- 本项目的 notebook **不在本地运行**，全部在 Colab T4 云端执行
- Colab 免费版约 4-6 小时超时，优先跑核心模型
- notebook中要进行相关三方包的安装，colab运行时模型权重自动从 HuggingFace/ModelScope 下载，首次运行较慢
