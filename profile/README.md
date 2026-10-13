<div align="center">

<img src="https://github.com/decloud-ai/.github/raw/main/assets/logo.png" width="40" alt="deCloud"> **deCloud**

**一个 API Key 调用全球顶级 AI 模型**

<sub>One API key to every frontier AI model</sub>

对话 · 图像 · 视频 · 语音 · 转写 · 嵌入 · 重排 —— 七类模型,一套 OpenAI 兼容协议。

<br>

[![Quickstart][b-qs]][l-qs] [![Docs][b-docs]][l-docs] [![Telegram][b-tg]][l-tg]

![OpenAI compatible][s-1] ![Anthropic Messages][s-2] ![OpenAI Responses][s-3]

</div>

---

### 能做什么

| 好处 | 说明 |
|---|---|
| 一把 Key 接多类模型 | 对话、图像、视频、语音、转写、嵌入、重排,不用为每家模型单独开户、单独管 Key |
| 换模型不用改代码 | 接入只写一次,之后模型换代跟你没关系 |
| 手上的客户端直接用 | Claude Code、Codex、Cursor、Cherry Studio 这类,能改接口地址就能接 |
| 报错看得懂 | `401` `402` `403` `404` `429` 各有说明和文档,中文英文都给了 |
| 失败不白花钱 | 上游出错导致的失败不计费;用量逐笔可查,能导出表格 |
| 模型来源看得见 | 每个模型的上游在模型页逐个标注 |

### 第一次跑通

1. 到 [macdecloud.com](https://macdecloud.com/?utm_source=gh) 注册,拿一把 `dcld-sk-…` 开头的 Key
2. 写代码接入时只改两处 —— 地址和 Key:

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://macdecloud.com/v1",
    api_key="dcld-sk-...",
)
```

3. 调用一次:返回里带 `content` 就说明通了

> 用图形客户端、Claude Code、Codex 的接法见 [quickstart][l-qs] —— 那三种填的字段不一样,别只改两处。

### 视频教程

| [![deCloud 接入教程](https://img.youtube.com/vi/Kh9MC5De2vI/maxresdefault.jpg)](https://www.youtube.com/watch?v=Kh9MC5De2vI) |
|---|
| 3 分钟 —— 从注册到第一次调用,完整走一遍。 |

### 关于 deCloud

deCloud 是一个 AI 模型接入层。一个 API Key 覆盖对话、图像、视频、语音、转写、嵌入、重排七类模型;对外统一 OpenAI 兼容协议,另提供 Anthropic Messages 与 OpenAI Responses 两个端点,原有代码只改「地址 + Key」两处。目录同时收录直连厂商与聚合目录来源,每个模型的上游在模型页逐个标注。按 token 计费,输入输出分列;上游出错导致的失败不扣余额;可申请免费额度。

### 遇到问题

- Telegram 客服 [t.me/DeCloud_CS](https://t.me/DeCloud_CS) —— 接入排障、用量答疑
- 在 [quickstart 提 Issue](https://github.com/decloud-ai/quickstart/issues) —— 报错、建议、文档问题

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
[d-1]: https://macdecloud.com/docs/access?utm_source=gh
[d-2]: https://macdecloud.com/docs/models?utm_source=gh
[d-3]: https://macdecloud.com/docs/clients?utm_source=gh
[d-4]: https://macdecloud.com/docs/billing?utm_source=gh
[d-5]: https://macdecloud.com/docs/errors?utm_source=gh

### 文档地图

- 开始
  - [五分钟跑通](https://macdecloud.com/docs?utm_source=gh)

- 接入
  - [接入方式](https://macdecloud.com/docs/access?utm_source=gh)
  - [地址到底填什么](https://macdecloud.com/docs/access/base-url?utm_source=gh)
  - [API Key 怎么用](https://macdecloud.com/docs/access/auth?utm_source=gh)
  - [协议与端点](https://macdecloud.com/docs/access/protocol?utm_source=gh)
  - [代码示例](https://macdecloud.com/docs/access/sdk?utm_source=gh)
  - [Key 的作用范围](https://macdecloud.com/docs/access/key-scope?utm_source=gh)

- 模型
  - [模型](https://macdecloud.com/docs/models?utm_source=gh)
  - [模型名怎么写](https://macdecloud.com/docs/models/how-to-find?utm_source=gh)
  - [能力标签怎么看](https://macdecloud.com/docs/models/capabilities?utm_source=gh)
  - [模型别名](https://macdecloud.com/docs/models/aliases?utm_source=gh)
  - [模型目录](https://macdecloud.com/docs/models/catalog?utm_source=gh)

- 客户端
  - [在客户端里使用](https://macdecloud.com/docs/clients?utm_source=gh)
  - [opencode](https://macdecloud.com/docs/clients/opencode?utm_source=gh)
  - [Cursor](https://macdecloud.com/docs/clients/cursor?utm_source=gh)
  - [Chatbox](https://macdecloud.com/docs/clients/chatbox?utm_source=gh)
  - [Claude Code](https://macdecloud.com/docs/clients/claude-code?utm_source=gh)
  - [Codex](https://macdecloud.com/docs/clients/codex?utm_source=gh)

- 计费
  - [计费](https://macdecloud.com/docs/billing?utm_source=gh)
  - [怎么计费](https://macdecloud.com/docs/billing/how-it-works?utm_source=gh)
  - [余额与 402](https://macdecloud.com/docs/billing/balance?utm_source=gh)
  - [失败与计费边界](https://macdecloud.com/docs/billing/failed?utm_source=gh)
  - [缓存字段](https://macdecloud.com/docs/billing/caching?utm_source=gh)
  - [用量与对账](https://macdecloud.com/docs/billing/usage?utm_source=gh)

- 排障
  - [错误码与排障](https://macdecloud.com/docs/errors?utm_source=gh)
  - [401 · Key 无效](https://macdecloud.com/docs/errors/401-invalid-key?utm_source=gh)
  - [402 · 余额不足](https://macdecloud.com/docs/errors/402-insufficient-balance?utm_source=gh)
  - [403 · 模型未授权](https://macdecloud.com/docs/errors/403-model-not-allowed?utm_source=gh)
  - [403 · Key 额度用完](https://macdecloud.com/docs/errors/403-quota-exhausted?utm_source=gh)
  - [404 · 找不到模型](https://macdecloud.com/docs/errors/404-model-not-found?utm_source=gh)
  - [405 · 请求方法不对](https://macdecloud.com/docs/errors/405-method-not-allowed?utm_source=gh)
  - [排查 Author anthropic is banned](https://macdecloud.com/docs/errors/author-anthropic-is-banned?utm_source=gh)
  - [429 · 被限流](https://macdecloud.com/docs/errors/429-rate-limited?utm_source=gh)
  - [502 · 上游没有这个模型](https://macdecloud.com/docs/errors/502-upstream-model-missing?utm_source=gh)
  - [504 · 上游超时](https://macdecloud.com/docs/errors/504-upstream-timeout?utm_source=gh)
  - [400 · 工具调用排查](https://macdecloud.com/docs/errors/400-tools-not-supported?utm_source=gh)
  - [400 · 模型与端点不匹配](https://macdecloud.com/docs/errors/400-model-endpoint-mismatch?utm_source=gh)
  - [200 · 返回成功但没有文本](https://macdecloud.com/docs/errors/200-empty-content?utm_source=gh)
