# AI Search Hub

<div align="center">

# AI Search Hub

### One Query. All Search.

**一次查询，同时搜索多个平台。**  
**No crawlers. No anti-bot pain. No keyword tuning.**

![GitHub stars](https://img.shields.io/github/stars/your-org/ai-search-hub?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/your-org/ai-search-hub?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Skill](https://img.shields.io/badge/type-open--source%20skill-black?style=flat-square)

**AI Search Hub** is an open-source skill that aggregates **platform-native AI search** into one unified interface.

Instead of building fragile crawlers, debugging browser automation, fighting anti-scraping systems, or endlessly tuning keywords,  
**AI Search Hub** lets your agent directly reuse the search capabilities that major AI platforms have already optimized.

</div>

---

## Why AI Search Hub

很多“全网搜索”方案最后都会变成：

- 自己写爬虫
- 自己养浏览器自动化
- 自己处理登录态、验证码、限流、封禁
- 自己一个个平台调搜索入口
- 自己不断修改关键词和提示词
- 自己从碎片结果里再做信息整理

这条路不是不能走，  
但它非常重、非常脆，而且维护成本极高。

**AI Search Hub 选择另一条路：**

> **直接接住各大厂商已经优化好的搜索能力。**

平台已经把搜索产品、排序逻辑、数据接入和交互体验打磨得很强了。  
你不需要再辛苦调试浏览器搜索、绕反爬、调关键词。  
**只要一次查询，就可以同时调用多个平台的原生搜索能力。**

---

## What It Does

AI Search Hub 的核心能力只有一句话：

# **One Query. All Search.**

给它一个问题，它可以把同一个查询同时发送到多个平台：

- Gemini
- Grok
- 豆包
- 元宝
- 文心一言
- 通义千问
- More providers in the future

每个平台负责搜索自己最擅长的数据世界：

- **Gemini** → Google / Web Search
- **Grok** → X / Twitter Search
- **豆包** → 抖音 / 中文内容生态
- **元宝** → 微信公众号 / 中文内容补充
- **文心一言 / 通义千问** → 更多中文互联网能力

最后统一返回给你的 Agent、Workflow 或 AI Assistant 使用。

---

## Highlights

- **One query, multiple platforms**
- **Parallel search across providers**
- **Reuse optimized platform-native search**
- **No crawler maintenance**
- **No anti-scraping headaches**
- **No browser-search debugging**
- **No repetitive keyword tuning**
- **Out of the box for agents**
- **Easy to extend with more providers**

---

## Architecture

AI Search Hub 不是重型搜索引擎，也不是大型爬虫框架。  
它本质上是一个 **AI 搜索能力聚合层**。

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
   用户或 Agent 只输入一次问题。

2. **Dispatch in parallel**  
   AI Search Hub 把同一个查询同时发送到多个平台。

3. **Let each provider search where it is strongest**  
   不同平台负责搜索不同内容生态中它们最有优势的部分。

4. **Aggregate results**  
   把多个平台返回的内容统一整理成标准输出。

5. **Return to your workflow**  
   最终供 Agent、研究系统、监控系统或自动化流程直接使用。

---

## Supported / Target Providers

| Provider | Strength |
|---|---|
| Gemini | Google / Web Search |
| Grok | X / Twitter Search |
| 豆包 | 抖音 / 中文内容生态 |
| 元宝 | 微信公众号 / 中文内容补充 |
| 文心一言 | 中文互联网搜索扩展 |
| 通义千问 | 中文互联网搜索扩展 |
| More | Easy to extend |

---

## Search Coverage

借助不同平台已经优化好的原生搜索能力，  
AI Search Hub 可以间接覆盖多种主流信息来源，例如：

- Google
- 微博
- 抖音
- Twitter / X
- Reddit
- 微信公众号
- 各类公开网页内容
- 海外社交媒体
- 中文互联网内容生态

重点不是你自己一个个平台去爬，  
而是：

> **借助平台本身已经连接好的数据世界，直接完成多平台搜索。**

---

## Why Not Crawlers?

因为问题往往不是“能不能爬”，而是“值不值得一直维护”。

传统方案通常要长期面对：

- 爬虫失效
- 浏览器流程变动
- 页面结构变化
- 验证码 / 风控 / 封号
- 搜索入口频繁调整
- 每个平台都要单独适配
- 关键词策略持续调试
- 最终还要自己整理输出

而 AI Search Hub 更像是：

> **借用平台已经打磨好的搜索系统，为你的 AI 直接服务。**

这意味着你可以少做很多重复建设，把精力留给真正重要的事情：

- Agent orchestration
- workflow design
- result fusion
- insight generation
- product experience

---

## Example

### Input

```json
{
  "query": "最近 AI 编程产品在不同平台的用户反馈",
  "providers": ["gemini", "grok", "doubao", "yuanbao"],
  "mode": "parallel"
}
```

### Output

```json
{
  "query": "最近 AI 编程产品在不同平台的用户反馈",
  "results": [
    {
      "provider": "gemini",
      "summary": "Google / Web search result summary"
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

## Use Cases

### Agent Search Skill
给你的 Agent 增加多平台并行搜索能力。

### Product Research
同时观察 Google、社交媒体、中文内容平台上的真实讨论和反馈。

### Social Listening
监听不同平台上的热点、趋势与用户声音。

### Intelligence Collection
为研究、分析与情报场景提供多平台统一搜索入口。

### Workflow Automation
把多平台搜索能力作为自动化流程里的标准模块。

---

## Philosophy

AI Search Hub 相信：

未来更强的搜索，  
不是一个更大的爬虫系统，  
而是一个更聪明的搜索聚合层。

不是重新造一遍平台已经做好的能力，  
而是把这些成熟能力连接起来。

> **让 AI 知道去哪里搜，  
> 比让你自己重新造一遍搜索系统更重要。**

---

## FAQ

### Is this a crawler framework?
No. It is a search capability aggregation skill.

### Do I need to maintain browser automation for every platform?
No. That is exactly the pain AI Search Hub tries to reduce.

### Do I need to keep tuning search keywords for each provider?
Usually much less. AI Search Hub is designed to reuse the optimized search ability platforms already have.

### Why is this useful for agents?
Because agents need search as a capability, not a pile of fragile browser scripts.

### Can I add more providers?
Yes. The design is intentionally lightweight and extensible.

---

## Roadmap

- [x] Multi-provider search aggregation
- [x] One-query parallel dispatch
- [x] Unified result output
- [ ] More provider integrations
- [ ] Better routing strategies
- [ ] Result ranking / fusion
- [ ] Evidence / source view
- [ ] Plug-and-play templates for agent frameworks

---

## Contributing

Issues and PRs are welcome.

If you also believe the future of search is not **one more crawler**, but **one smarter way to use all existing AI search surfaces together**, feel free to contribute.

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
