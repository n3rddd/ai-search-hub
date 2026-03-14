<div align="center">

# AI Search Hub

### One Query. All Search.

[中文](README.md)

[![GitHub stars](https://img.shields.io/github/stars/minsight-ai-info/AI-Search-Hub?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/minsight-ai-info/AI-Search-Hub?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub/network/members)
[![GitHub issues](https://img.shields.io/github/issues/minsight-ai-info/AI-Search-Hub?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub/issues)
[![GitHub repo](https://img.shields.io/badge/repo-GitHub-181717?style=flat-square&logo=github)](https://github.com/minsight-ai-info/AI-Search-Hub)
[![Skill](https://img.shields.io/badge/type-open--source%20skill-black?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub)

**AI Search Hub** is an open-source skill that aggregates **platform-native AI search** into one unified interface.

Instead of building fragile crawlers, debugging browser automation, fighting anti-scraping systems, or endlessly tuning keywords,
AI Search Hub lets your agent directly reuse the search capabilities that major AI platforms have already optimized.

</div>

---

## What is AI Search Hub?

**AI Search Hub** is an open-source skill that turns fragmented AI search surfaces into one unified search hub.

Gemini is strong at **Google / web search**.
Grok is strong at **X / Twitter search**.
Doubao is strong at **Douyin and Chinese content ecosystems**.
Yuanbao can help with **WeChat Official Accounts and Chinese web content**.
Wenxin Yiyan and Qwen can further expand Chinese internet coverage.

AI Search Hub does not try to reinvent a search engine from scratch.
It directly reuses the search power these platforms have already refined.

You do not need to:

- maintain fragile crawlers
- debug browser automation for every platform
- fight anti-scraping systems again and again
- manually tune keywords for different providers
- refine scattered search results by hand

You just send **one query**, and AI Search Hub can search across **multiple platforms in parallel**.

---

## Why AI Search Hub?

Most "all-web search" solutions eventually become the same heavy engineering story:

- custom crawlers
- browser automation
- login/session management
- captchas, rate limits, bans
- platform-specific search workflows
- endless keyword tuning
- manual result cleanup

AI Search Hub takes a different path:

> **Reuse the search power platforms have already optimized.**

Platforms already invested in search quality, ranking, data access, and interaction design.
AI Search Hub simply connects those capabilities together into one reusable skill.

---

## Core Value

- **One query, multiple platforms**
- **Parallel search across providers**
- **Reuse platform-native search**
- **No crawler maintenance**
- **No anti-bot headaches**
- **No browser-search debugging**
- **No repetitive keyword tuning**
- **Out of the box for agents**
- **Easy to extend with more providers**

---

## Architecture

AI Search Hub is not a heavyweight search engine.
It is not a giant crawler framework either.

It is a lightweight **search capability aggregation layer**.

```text
User / Agent
    -> One Query
    -> AI Search Hub
        -> Gemini
        -> Grok
        -> Doubao
        -> Yuanbao
        -> Wenxin
        -> Qwen
    -> Multi-platform Search Results
    -> Unified Output
```

### How it works

1. **Receive one query**
   A user or agent asks one question.

2. **Dispatch in parallel**
   AI Search Hub sends the same query to multiple platforms at the same time.

3. **Let each provider search where it is strongest**
   Each platform searches its best-connected content ecosystem.

4. **Aggregate results**
   Results from multiple platforms are normalized into one output.

5. **Return to your workflow**
   The output is ready for agents, workflows, research systems, or monitoring pipelines.

---

## Supported / Target Providers

| Provider | Strength |
|---|---|
| Gemini | Google / Web Search |
| Grok | X / Twitter Search |
| Doubao | Douyin / Chinese content ecosystem |
| Yuanbao | WeChat Official Accounts / Chinese web content |
| Wenxin Yiyan | Chinese internet search expansion |
| Qwen / Tongyi | Chinese internet search expansion |
| More | Easy to extend |

---

## Search Coverage

By reusing platform-native search capabilities, AI Search Hub can indirectly cover many major content sources, such as:

- Google
- Weibo
- Douyin
- Twitter / X
- Reddit
- WeChat Official Accounts
- public web pages
- overseas social media
- Chinese internet ecosystems

The point is not to crawl every platform yourself.
The point is to let platforms search the worlds they already know best.

---

## How should configuration look?

If you only want a conceptual configuration example in the README, something like this works well:

```yaml
hub:
  parallel: true
  timeout_ms: 30000
  normalize_output: true

providers:
  gemini:
    enabled: true
    role: "google-web-search"

  grok:
    enabled: true
    role: "x-twitter-search"

  doubao:
    enabled: true
    role: "douyin-chinese-content"

  yuanbao:
    enabled: true
    role: "wechat-official-accounts"

  wenxin:
    enabled: false
    role: "chinese-web-search"

  qwen:
    enabled: false
    role: "general-chinese-search"
```

This does not mean the project already ships with a YAML file in exactly this format.
It is a conceptual example that communicates:

- the hub layer is responsible for orchestration
- the provider layer controls which platforms are enabled
- each provider has a distinct search role

If the real implementation later uses JSON, Python dictionaries, or environment variables, the example can be updated.

---

## Example Request

```json
{
  "query": "What are users saying about AI coding products across different platforms recently?",
  "providers": ["gemini", "grok", "doubao", "yuanbao"],
  "mode": "parallel"
}
```

## Example Output

```json
{
  "query": "What are users saying about AI coding products across different platforms recently?",
  "results": [
    {
      "provider": "gemini",
      "summary": "Google / web search result summary"
    },
    {
      "provider": "grok",
      "summary": "X / Twitter search result summary"
    },
    {
      "provider": "doubao",
      "summary": "Douyin / Chinese content summary"
    },
    {
      "provider": "yuanbao",
      "summary": "WeChat Official Accounts / Chinese web summary"
    }
  ]
}
```

---

## FAQ

**Is this a crawler framework?**
No. It is a search capability aggregation skill.

**Do I need browser automation for every platform?**
That is exactly the burden AI Search Hub tries to reduce.

**Do I still need to tune keywords for different providers?**
Much less than traditional workflows, because AI Search Hub reuses search systems already optimized by the platforms.

**Why is this useful for agents?**
Because agents need search as a capability, not a pile of brittle browser scripts.

**Can I add more providers?**
Yes. The design is intentionally lightweight and extensible.

---

## Repository

- GitHub: https://github.com/minsight-ai-info/AI-Search-Hub

---

## Roadmap

- [ ] Multi-provider search aggregation
- [ ] One-query parallel dispatch
- [ ] Unified result output
- [x] Browser-based provider runners
- [x] Login recovery flow
- [x] Isolated browser-profile seeding
- [ ] More provider integrations
- [ ] Better routing strategies
- [ ] Result ranking / fusion
- [ ] Evidence / source view
- [ ] Plug-and-play templates for agent frameworks

---

## Contributing

Issues and PRs are welcome.

If you also believe the future of search is not **one more crawler**,
but **one smarter way to use all existing AI search surfaces together**, feel free to contribute.

---

## Disclaimer

AI Search Hub is designed to reuse platform-native capabilities in a practical and sustainable way.
Please comply with the terms of service, policies, and applicable laws of the platforms you integrate with.

This project focuses on aggregation and orchestration, not on bypassing platform rules.

---

## Final Line

**One Query. All Search.**
Stop rebuilding search from scratch.
Plug into the search power platforms already optimized.
