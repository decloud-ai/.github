<p align="right"><a href="https://github.com/decloud-ai/.github/blob/main/profile/README.md">中文</a> · <b>English</b></p>

<div align="center">

<img src="https://github.com/decloud-ai/.github/raw/main/assets/logo.png" width="56" alt="deCloud">

## deCloud

**One API key to every frontier AI model**<br>
<sub>一个 API Key 调用全球顶级 AI 模型</sub>

[![Website][b-web]][l-web] [![Quickstart][b-qs]][l-qs] [![Docs][b-docs]][l-docs] [![YouTube][b-yt]][l-yt] [![Email][b-mail]][l-mail] [![Support][b-tg]][l-tg]

![OpenAI compatible][s-1] ![Anthropic Messages][s-2] ![OpenAI Responses][s-3]

</div>

---

### `01` Why deCloud

Wiring up several model vendors usually means one new key per vendor, a retest on every switch, bills scattered across consoles, and no way to tell which layer failed. deCloud puts that in one middle layer:

- `One key, seven model classes` <sub>no separate accounts or keys per vendor</sub>
- `Write the integration once` <sub>swap models without touching code</sub>
- `Keep the client you use` <sub>Claude Code, Codex, Cursor, Cherry Studio — change the address and you are in</sub>
- `Upstreams labeled` <sub>each model's source is shown on the <a href="https://macdecloud.com/models?utm_source=gh">model page</a></sub>
- `Upstream failures are not charged` <sub>and usage is itemized and exportable</sub>
- `Errors you can act on` <sub>one doc page per status code, in English and Chinese</sub>

`Which models can I use?` <sub><a href="https://macdecloud.com/models?utm_source=gh">Open the model page</a></sub>

---

### `02` 5-minute quickstart

1. `Connect to sign in` <sub>no account, no email; MetaMask / OKX Wallet / TokenPocket / imToken and browser wallets all work, and signing never moves funds or costs gas</sub>
2. `Top up` <sub>one balance, charged by token usage:<a href="https://macdecloud.com/docs/billing?utm_source=gh">how billing works</a></sub>
3. `Create an API Key` <sub>create your own in the console, starting with dcld-sk-</sub>
4. `Plug it in` <sub>two fields only: base URL and key</sub>

```python
client = OpenAI(
    base_url="https://macdecloud.com/v1",   # base URL
    api_key="dcld-sk-...",                  # your key
)
```

---

### `03` Code examples

<sub>Set your key first: `export DECLOUD_API_KEY='dcld-sk-...'`</sub>

#### `03.1` cURL

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

<sub>Install first (once is enough): the code below calls the API with OpenAI's official SDK, installed with pip.</sub>

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

<sub>Install first (once is enough): the code below calls the API with OpenAI's official SDK, installed with npm.</sub>

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

#### `03.4` Streaming (SSE)

Add `"stream": true` to the request body:

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

### `04` Common clients

<sub>Both need a model alias created in the console (API Keys → Model aliases), mapped to a tool-capable model; avoid reserved short names such as `opus`/`sonnet`/`haiku`, or set the model field to a real model ID.</sub>

#### `04.1` Claude Code

```bash
export ANTHROPIC_BASE_URL='https://macdecloud.com'
export ANTHROPIC_AUTH_TOKEN='dcld-sk-...'
export ANTHROPIC_MODEL='decloud-coder'
claude
```

<sub>Use `ANTHROPIC_AUTH_TOKEN` here (sent as a Bearer token); `ANTHROPIC_API_KEY` (sent as `x-api-key`) returns 401.</sub>

---

#### `04.2` Codex

Write this into `~/.codex/config.toml`:

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

Then:

```bash
export DECLOUD_API_KEY='dcld-sk-...'
codex
```

More setups (Cursor · opencode · Cherry Studio · tool calling · how to write a model ID) are in the [Docs · Clients](https://macdecloud.com/docs/clients?utm_source=gh) and the [quickstart][l-qs].

---

### `05` Watch it

| [![deCloud setup walkthrough](https://img.youtube.com/vi/Kh9MC5De2vI/maxresdefault.jpg)](https://www.youtube.com/watch?v=Kh9MC5De2vI) |
|---|
| <sub>3 minutes — from connecting a wallet to your first call.</sub> |

---

### `06` About deCloud

deCloud (macdecloud.com) is an OpenAI-compatible AI gateway: one API key covers seven model classes — chat, image, video, speech, transcription, embeddings and rerank. Requests use the OpenAI schema, and Anthropic Messages and OpenAI Responses endpoints are available alongside it, so existing clients change only the base URL and key. The catalog mixes first-party vendors and aggregator sources, and each model's upstream is labeled on the model page, where per-token pricing is listed. Billing is prepaid per token, input and output priced separately; requests that fail upstream are not charged, and trial credits are available on request. Docs: macdecloud.com/docs

---

### `07` Need help

- [`Telegram support`](https://t.me/DeCloud_CS) <sub>integration troubleshooting, usage questions</sub>
- [`GitHub Issue`](https://github.com/decloud-ai/quickstart/issues) <sub>errors, suggestions, documentation problems</sub>

---

### `08` Get started

<div align="center">

[![Get started][b-go]][l-go] [![All docs][b-index]][l-index] [![Email][b-mail]][l-mail]

Connect to sign in → Create an API Key → Plug it in → make your first call.

<sub><a href="https://macdecloud.com/?utm_source=gh">macdecloud.com</a> · <a href="https://github.com/decloud-ai/.github/blob/main/DOCS.md">all documentation</a></sub>

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
