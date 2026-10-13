# deCloud

**一个 API Key 调用全球顶级 AI 模型**
*One API key to every frontier AI model*

deCloud 是一个 AI 模型接入层:一个 API Key 覆盖对话、图像、视频、语音、转写、嵌入、重排七类模型;
对外统一 OpenAI 兼容协议,另提供 Anthropic Messages 与 OpenAI Responses 两个端点,
原有代码只改「地址 + Key」两处。目录同时收录直连厂商与聚合目录来源,每个模型的上游在模型页逐个标注。
按 token 计费,失败不计费。

![OpenAI compatible](https://img.shields.io/badge/OpenAI-compatible-245e43?style=flat-square)
![Anthropic Messages](https://img.shields.io/badge/Anthropic-Messages-245e43?style=flat-square)
![OpenAI Responses](https://img.shields.io/badge/OpenAI-Responses-245e43?style=flat-square)

[![Quickstart](https://img.shields.io/badge/Quickstart-30s-245e43?style=for-the-badge&logo=github)](https://github.com/decloud-ai/quickstart)
[![Docs](https://img.shields.io/badge/Docs-macdecloud.com-192b25?style=for-the-badge)](https://macdecloud.com/docs)

### 🚀 从这里开始

| | |
|---|---|
| **[30 秒接入 →](https://github.com/decloud-ai/quickstart)** | 四种接法:写代码 · 图形客户端 · Claude Code · Codex |
| **[完整文档 →](https://macdecloud.com/docs)** | 接入 · 计费 · 客户端 · [报错对照](https://macdecloud.com/docs/errors) |
| **[官网 →](https://macdecloud.com)** | 控制台 · 模型目录与单价 |

### 它解决的四件事

| 你会遇到的 | deCloud 的做法 |
|---|---|
| 换个模型就要重测 | **接入与模型解耦** —— 接入写一次,之后模型换代与它无关 |
| 各家接口都不一样 | **统一协议** —— OpenAI 兼容 + Anthropic + Responses |
| 每接一家就多一个 Key | **目录聚合** —— 直连与聚合目录收在一处,来源逐个标注 |
| 月底对账要登多个后台 | **权限与用量合一** —— 权限、用量、明细逐笔可核 |

### 常用客户端

NextChat · Chatbox · LobeChat · Open WebUI · Cherry Studio · Cursor · opencode · Claude Code · Codex
—— 常见客户端的自定义接口地址都能接。

### 支持

| | |
|---|---|
| 💬 **Telegram 客服** | **https://t.me/DeCloud_CS** |
| 🐛 **提问 / 报错** | [提 Issue](https://github.com/decloud-ai/quickstart/issues) |
| 📖 **报错对照** | [macdecloud.com/docs/errors](https://macdecloud.com/docs/errors) |

> 提问时说清三件事最快:**用的哪个客户端 · 模型写的是哪个完整 ID · 返回的状态码与错误原文**。
