<div align="center">

<img src="https://github.com/decloud-ai/.github/raw/main/assets/logo.png" width="56" alt="deCloud">

### deCloud

**一个 API Key 调用全球顶级 AI 模型**<br>
<sub>One API key to every frontier AI model</sub>

[![Website][b-web]][l-web] [![Quickstart][b-qs]][l-qs] [![Docs][b-docs]][l-docs] [![TG][b-tg]][l-tg]

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

[b-web]: https://img.shields.io/badge/Website-macdecloud.com-245e43?style=for-the-badge&logo=googlechrome
[l-web]: https://macdecloud.com/?utm_source=gh
[b-qs]: https://img.shields.io/badge/Quickstart-5m-245e43?style=for-the-badge&logo=github
[l-qs]: https://github.com/decloud-ai/quickstart
[b-docs]: https://img.shields.io/badge/Docs-macdecloud.com%2Fdocs-245e43?style=for-the-badge&logo=readthedocs
[l-docs]: https://macdecloud.com/docs?utm_source=gh
[b-tg]: https://img.shields.io/badge/TG-SUPPORT-192b25?style=for-the-badge&logo=telegram
[l-tg]: https://t.me/DeCloud_CS
[s-1]: https://img.shields.io/badge/OpenAI-compatible-192b25?style=flat-square
[s-2]: https://img.shields.io/badge/Anthropic-Messages-192b25?style=flat-square
[s-3]: https://img.shields.io/badge/OpenAI-Responses-192b25?style=flat-square
[d-1]: https://macdecloud.com/docs/access?utm_source=gh
[d-2]: https://macdecloud.com/docs/models?utm_source=gh
[d-3]: https://macdecloud.com/docs/clients?utm_source=gh
[d-4]: https://macdecloud.com/docs/billing?utm_source=gh
[d-5]: https://macdecloud.com/docs/errors?utm_source=gh

### 开始使用

[![Get started][b-go]][l-go] [![All docs][b-index]][l-index]

注册 → 拿一把 Key → 改两处地址 → 跑通第一次调用。

<div align="center"><sub><a href="https://macdecloud.com/?utm_source=gh">macdecloud.com</a> · <a href="https://github.com/decloud-ai/.github/blob/main/DOCS.md">文档总目录</a></sub></div>

[b-go]: https://img.shields.io/badge/Get%20started-macdecloud.com-245e43?style=for-the-badge
[l-go]: https://macdecloud.com/?utm_source=gh
[b-index]: https://img.shields.io/badge/Docs-All%20pages-192b25?style=for-the-badge&logo=github
[l-index]: https://github.com/decloud-ai/.github/blob/main/DOCS.md
