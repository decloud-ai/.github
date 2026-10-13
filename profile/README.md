<p align="right"><b>中文</b> · <a href="https://github.com/decloud-ai/.github/blob/main/profile/README.en.md">English</a></p>

<div align="center">

<img src="https://github.com/decloud-ai/.github/raw/main/assets/logo.png" width="56" alt="deCloud">

## deCloud

**一个 API Key 调用全球顶级 AI 模型**<br>
<sub>One API key to every frontier AI model</sub>

[![Website][b-web]][l-web] [![Quickstart][b-qs]][l-qs] [![Docs][b-docs]][l-docs] [![YouTube][b-yt]][l-yt] [![Email][b-mail]][l-mail] [![Support][b-tg]][l-tg]

![OpenAI compatible][s-1] ![Anthropic Messages][s-2] ![OpenAI Responses][s-3]

</div>

---

### `01` 为什么选择 deCloud

接入多家模型,通常绕不开这几件事:每接一家就多一把 Key、换个模型就要重测、账单散在几个后台、出错了看不出是哪一层的问题。deCloud 把这些收在中间一层里:

- `一个 Key 覆盖七类模型` <sub>不用逐家开户、逐家管 Key</sub>
- `接入只写一次` <sub>换模型不用改代码</sub>
- `客户端不用换` <sub>Claude Code、Codex、Cursor、Cherry Studio 能改地址就能接</sub>
- `上游逐个标注` <sub>每个模型的来源在<a href="https://macdecloud.com/models?utm_source=gh">模型页</a>看得见</sub>
- `失败不计费` <sub>上游出错导致的失败不扣余额,用量可导出</sub>
- `报错有据可查` <sub>每个状态码一页文档,中英文都有</sub>

`能用哪些模型` <sub><a href="https://macdecloud.com/models?utm_source=gh">打开模型页</a></sub>

---

### `02` 五分钟跑通

1. `连接即登录` <sub>不用注册、不用邮箱;MetaMask / OKX Wallet / TokenPocket / imToken 都能用,签名不转账、不花手续费</sub>
2. `充值` <sub>充一次余额,按 token 用量扣:<a href="https://macdecloud.com/docs/billing?utm_source=gh">计费说明</a></sub>
3. `创建 API Key` <sub>在控制台创建一把属于自己的,以 dcld-sk- 开头</sub>
4. `填进工具` <sub>只改两处:地址和 Key</sub>

```python
client = OpenAI(
    base_url="https://macdecloud.com/v1",   # 地址
    api_key="dcld-sk-...",                  # Key
)
```

---

### `03` 代码示例

<sub>先设好 Key:`export DECLOUD_API_KEY='dcld-sk-...'`</sub>

#### `03.1` 先用 cURL 跑通

```bash
export DECLOUD_API_KEY='dcld-sk-...'

curl https://macdecloud.com/v1/chat/completions \
  -H "Authorization: Bearer $DECLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "model": "deepseek/deepseek-chat",
  "messages": [
    {
      "role": "user",
      "content": "Hello"
    }
  ]
}' 
```

---

#### `03.2` Python

<sub>先装依赖(装一次就行):下面的代码用 OpenAI 官方 SDK 发请求,Python 用 pip 装。</sub>

```bash
pip install openai
```

```python
import os
from openai import OpenAI

client = OpenAI(
    base_url="https://macdecloud.com/v1",
    api_key=os.environ["DECLOUD_API_KEY"],
)
r = client.chat.completions.create(
    model="deepseek/deepseek-chat",
    messages=[{"role": "user", "content": "Hello"}],
)
print(r.choices[0].message.content)
```

---

#### `03.3` Node.js

<sub>先装依赖(装一次就行):下面的代码用 OpenAI 官方 SDK 发请求,Node.js 用 npm 装。</sub>

```bash
npm install openai
```

```javascript
import OpenAI from "openai";

const client = new OpenAI({
  baseURL: "https://macdecloud.com/v1",
  apiKey: process.env.DECLOUD_API_KEY,
});
const r = await client.chat.completions.create({
  model: "deepseek/deepseek-chat",
  messages: [{ role: "user", content: "Hello" }],
});
console.log(r.choices[0].message.content);
```

---

#### `03.4` 流式输出(SSE)

请求体里加 `"stream": true`:

```bash
curl https://macdecloud.com/v1/chat/completions \
  -H "Authorization: Bearer $DECLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "model": "deepseek/deepseek-chat",
  "stream": true,
  "messages": [
    {
      "role": "user",
      "content": "Hello"
    }
  ]
}' 
```

---

### `04` 常见客户端

<sub>两个都要先在控制台建模型别名(API Keys → Model aliases),映射到支持工具调用的模型;别用 `opus`/`sonnet`/`haiku` 这类保留短名,或直接把模型字段写成真实模型 ID。</sub>

#### `04.1` Claude Code

```bash
export ANTHROPIC_BASE_URL='https://macdecloud.com'
export ANTHROPIC_AUTH_TOKEN='dcld-sk-...'
export ANTHROPIC_MODEL='decloud-coder'
claude
```

<sub>必须用 `ANTHROPIC_AUTH_TOKEN`(按 Bearer 发送):换成 `ANTHROPIC_API_KEY`(客户端会发 `x-api-key`)会 401。</sub>

---

#### `04.2` Codex

配置写进 `~/.codex/config.toml`:

```toml
# ~/.codex/config.toml
model = "decloud-codex"
model_provider = "decloud"

[model_providers.decloud]
name = "deCloud"
base_url = "https://macdecloud.com/v1"
env_key = "DECLOUD_API_KEY"
wire_api = "responses"
```

然后:

```bash
export DECLOUD_API_KEY='dcld-sk-...'
codex
```

更多接法(Cursor · opencode · Cherry Studio · 工具调用 · 模型名怎么写)见 [文档 · 客户端](https://macdecloud.com/docs/clients?utm_source=gh) 与 [quickstart][l-qs]。

---

### `05` 视频教程

| [![deCloud 接入教程](https://img.youtube.com/vi/Kh9MC5De2vI/maxresdefault.jpg)](https://www.youtube.com/watch?v=Kh9MC5De2vI) |
|---|
| <sub>3 分钟 —— 从连接钱包到第一次调用,完整走一遍。</sub> |

---

### `06` 关于 deCloud

deCloud 是一个 AI 模型接入层。一个 API Key 覆盖对话、图像、视频、语音、转写、嵌入、重排七类模型;对外统一 OpenAI 兼容协议,另提供 Anthropic Messages 与 OpenAI Responses 两个端点,原有代码只改「地址 + Key」两处。目录同时收录直连厂商与聚合目录来源,每个模型的上游在模型页逐个标注。按 token 计费,输入输出分列;上游出错导致的失败不扣余额;可申请免费额度。

---

### `07` 遇到问题

- [`Telegram 客服`](https://t.me/DeCloud_CS) <sub>接入排障、用量答疑</sub>
- [`GitHub Issue`](https://github.com/decloud-ai/quickstart/issues) <sub>报错、建议、文档问题</sub>

---

### `08` 开始使用

<div align="center">

[![Get started][b-go]][l-go] [![All docs][b-index]][l-index] [![Email][b-mail]][l-mail]

连接即登录 → 创建 API Key → 填进工具 → 跑通第一次调用。

<sub><a href="https://macdecloud.com/?utm_source=gh">macdecloud.com</a> · <a href="https://github.com/decloud-ai/.github/blob/main/DOCS.md">文档总目录</a></sub>

</div>

[b-web]: https://img.shields.io/badge/Website-245e43?style=for-the-badge&logo=googlechrome&logoColor=white
[b-qs]: https://img.shields.io/badge/Quickstart-245e43?style=for-the-badge&logo=github&logoColor=white
[b-docs]: https://img.shields.io/badge/Docs-245e43?style=for-the-badge&logo=readthedocs&logoColor=white
[b-yt]: https://img.shields.io/badge/YouTube-a13a2c?style=for-the-badge&logo=youtube&logoColor=white
[b-mail]: https://img.shields.io/badge/Email-245e43?style=for-the-badge&logo=gmail&logoColor=white
[b-tg]: https://img.shields.io/badge/Support-26A5E4?style=for-the-badge&logo=telegram&logoColor=white
[s-1]: https://img.shields.io/badge/OpenAI-compatible-192b25?style=flat-square
[s-2]: https://img.shields.io/badge/Anthropic-Messages-192b25?style=flat-square
[s-3]: https://img.shields.io/badge/OpenAI-Responses-192b25?style=flat-square
[b-go]: https://img.shields.io/badge/Get%20started-245e43?style=for-the-badge&logo=googlechrome&logoColor=white
[b-index]: https://img.shields.io/badge/All%20docs-192b25?style=for-the-badge&logo=github&logoColor=white
[l-web]: https://macdecloud.com/?utm_source=gh
[l-qs]: https://github.com/decloud-ai/quickstart
[l-docs]: https://macdecloud.com/docs?utm_source=gh
[l-yt]: https://www.youtube.com/@decloud-AI
[l-mail]: mailto:globaldecloud@gmail.com
[l-tg]: https://t.me/DeCloud_CS
[l-go]: https://macdecloud.com/?utm_source=gh
[l-index]: https://github.com/decloud-ai/.github/blob/main/DOCS.md
