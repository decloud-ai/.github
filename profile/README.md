<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.png">
  <img src="assets/logo-light.png" width="88" alt="deCloud">
</picture>

**一个 API Key 调用全球顶级 AI 模型**

<sub>One API key to every frontier AI model</sub>

对话 · 图像 · 视频 · 语音 · 转写 · 嵌入 · 重排 —— 七类模型,一套 OpenAI 兼容协议。

<br>

[![Quickstart][b-qs]][l-qs] [![Docs][b-docs]][l-docs] [![Telegram][b-tg]][l-tg]

![OpenAI compatible][s-1] ![Anthropic Messages][s-2] ![OpenAI Responses][s-3]

</div>

---

## 能做什么

- **七类模型一个 Key** —— 对话 · 图像 · 视频 · 语音 · 转写 · 嵌入 · 重排
- **三种协议原生** —— OpenAI 兼容 · Anthropic Messages · OpenAI Responses,原有代码只改「地址 + Key」两处
- **上游可核** —— 目录同时收录直连厂商与聚合目录来源,每个模型的上游在模型页逐个标注
- **账在一处** —— 权限、用量、明细逐笔可核,支持导出

## 第一次跑通

1. 到 **[macdecloud.com](https://macdecloud.com/?utm_source=gh)** 注册,拿一把 `dcld-sk-…` 开头的 Key
2. 把地址和 Key 换掉 —— **只改这两处**:

```python
from openai import OpenAI
client = OpenAI(base_url="https://macdecloud.com/v1", api_key="dcld-sk-...")
```

3. 调用一次 —— **返回里带 `content` 就说明通了**
   四种接法(写代码 / 图形客户端 / Claude Code / Codex)见 **[quickstart][l-qs]**

## 文档地图

- **接入** —— [接口地址与 Key](https://macdecloud.com/docs/access?utm_source=gh) · [协议与端点](https://macdecloud.com/docs/access/protocol?utm_source=gh) · [SDK](https://macdecloud.com/docs/access/sdk?utm_source=gh)
- **模型与单价** —— [模型目录](https://macdecloud.com/models?utm_source=gh)
- **计费与用量** —— [计费说明](https://macdecloud.com/docs/billing?utm_source=gh) · [用量明细](https://macdecloud.com/docs/billing/usage?utm_source=gh)
- **客户端** —— [全部客户端填法](https://macdecloud.com/docs/clients?utm_source=gh)(Chatbox · Claude Code · Codex · Cursor · opencode …)
- **报错对照** —— [每个状态码一页](https://macdecloud.com/docs/errors?utm_source=gh)(`401` `402` `403` `404` `429` `502` `504`)

## 遇到问题

- 💬 **[Telegram 客服](https://t.me/DeCloud_CS)** —— 接入排障 / 用量答疑(要快走这里)
- 🐛 **[提 Issue](https://github.com/decloud-ai/quickstart/issues)** —— 报错 · 建议 · 文档问题(仓库里有 4 类模板)

<details>
<summary><b>关于 deCloud（完整介绍）</b></summary>

deCloud 是一个 AI 模型接入层。一个 API Key 覆盖对话、图像、视频、语音、转写、嵌入、重排七类模型;对外统一 OpenAI 兼容协议,另提供 Anthropic Messages 与 OpenAI Responses 两个端点,原有代码只改「地址 + Key」两处。目录同时收录直连厂商与聚合目录来源,每个模型的上游在模型页逐个标注。按 token 计费,输入输出分列;上游出错导致的失败不扣余额;可申请免费额度。文档:macdecloud.com/docs

</details>

<div align="center"><sub><a href="https://macdecloud.com/?utm_source=gh">macdecloud.com</a> · <a href="https://macdecloud.com/docs?utm_source=gh">文档</a></sub></div>

[b-qs]: https://img.shields.io/badge/Quickstart-30s-245e43?style=for-the-badge&logo=github
[l-qs]: https://github.com/decloud-ai/quickstart
[b-docs]: https://img.shields.io/badge/Docs-macdecloud.com-245e43?style=for-the-badge
[l-docs]: https://macdecloud.com/docs?utm_source=gh
[b-tg]: https://img.shields.io/badge/Telegram-Support-192b25?style=for-the-badge&logo=telegram
[l-tg]: https://t.me/DeCloud_CS
[s-1]: https://img.shields.io/badge/OpenAI-compatible-192b25?style=flat-square
[s-2]: https://img.shields.io/badge/Anthropic-Messages-192b25?style=flat-square
[s-3]: https://img.shields.io/badge/OpenAI-Responses-192b25?style=flat-square
