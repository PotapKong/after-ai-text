## Mode: telegram-post

Convert raw source material (ArXiv abstract, GitHub repo description, HN thread, paper summary) into a ready-to-publish Telegram channel post.

### Input

Provide one of:
- `source:` — raw text to convert (abstract, description, thread)
- `url:` — link to the source
- `draft:` — existing rough post that needs formatting

Optionally provide:
- `channel-voice:` — paste 2-3 example posts from the channel to match tone
- `lang: ru` or `lang: en` — defaults to `ru`

### Output constraints

- **Length:** 600–900 characters including spaces (Telegram sweet spot — fits preview without "Read more")
- **Structure:** one bold headline → 2–3 tight lines of context → bullet block → one closing line → one link
- **Emoji:** markers only (bullets and headline), not decoration — `⚡`, `→`, `●`, `🔗`
- **Bold:** headline only, nothing else
- **Link:** inline in the last line, never bare URL

### Workflow

1. Extract the single most important thing — what changed, what's possible now that wasn't before
2. Cut everything that is context the audience already has
3. Write the headline as a statement, not a question or a tease
4. Bullets: each one a concrete fact or number, not a feature label
5. Closing line: what to do with this — try it, read it, watch it
6. Run through `banned-phrases-ru-tech.md` — remove every hit
7. Check length — if over 900, cut from the middle, not the end

### Quality gate (feeds into Judge Skill)

Score 0–1 across four criteria. Post must reach ≥ 0.7 aggregate to publish.

| Criterion | 0 | 0.5 | 1 |
|---|---|---|---|
| **Share-worthy** | Would not repost | Maybe | Would drop in a chat immediately |
| **Concrete** | Only labels and abstractions | Some specifics | Every claim has a fact or number behind it |
| **Clean** | 3+ banned phrases | 1–2 hits | Zero hits from banned-phrases-ru-tech.md |
| **On-voice** | Sounds like ChatGPT | Close-ish | Matches channel examples |

### What this mode does NOT do

- Does not fabricate numbers or benchmark results not present in the source
- Does not add opinions not supported by the source
- Does not rewrite the source into a thread — one post only
- Does not keep "revolutionary", "cutting-edge", "leverages", "novel approach", "state-of-the-art" in any language

### Example

**Source (ArXiv abstract, 400 words):**
> We present Qwen3, a series of large language models... achieves state-of-the-art performance on reasoning benchmarks...

**Output:**
```
**Qwen3: мышление по требованию без платы за каждый токен**

Alibaba выпустила серию из 8 моделей — от 0.6B до 235B. Главное: режимы thinking/non-thinking переключаются в одном запросе.

● 235B-A22B на AIME'25 — 85.7 (лучше o1)
● Бесплатно на Hugging Face, веса открыты
● 119 языков, включая русский

Скачать и попробовать: huggingface.co/Qwen/Qwen3-235B-A22B

#qwen #llm #opensource
```
