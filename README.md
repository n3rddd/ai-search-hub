<div align="center">

# AI Search Hub

### 一次查询，同时搜索多个平台。

[English](README.en.md)

[![GitHub stars](https://img.shields.io/github/stars/minsight-ai-info/AI-Search-Hub?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/minsight-ai-info/AI-Search-Hub?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub/network/members)
[![GitHub issues](https://img.shields.io/github/issues/minsight-ai-info/AI-Search-Hub?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub/issues)
[![GitHub repo](https://img.shields.io/badge/repo-GitHub-181717?style=flat-square&logo=github)](https://github.com/minsight-ai-info/AI-Search-Hub)
[![Skill](https://img.shields.io/badge/type-open--source%20skill-black?style=flat-square)](https://github.com/minsight-ai-info/AI-Search-Hub)

**AI Search Hub** 是一个开源 Skill，用来把原本分散在不同 AI 平台聊天框里的搜索能力，统一成一个可复用的搜索中枢。

你不需要自己维护脆弱的爬虫，不需要反复调试浏览器自动化，不需要辛苦绕反爬，也不需要一遍遍试关键词。
**AI Search Hub 直接复用各大厂商已经优化好的搜索能力。**

</div>

---

## AI Search Hub 是什么？

- Gemini 更擅长 **Google / 网页搜索**
- Grok 更擅长 **X / Twitter 搜索**
- 豆包 更擅长 **抖音和中文内容生态**
- 元宝 可以补充 **微信公众号和中文网页内容**
- 文心一言、通义千问 还能继续扩展中文互联网覆盖

AI Search Hub 不是重新发明一个搜索引擎，
而是直接接住这些平台已经打磨好的搜索能力。

你不需要再：

- 自己维护一堆脆弱爬虫
- 为每个平台单独调试浏览器自动化
- 反复处理反爬、限流、封禁、验证码
- 为不同平台一遍遍调关键词
- 手动整理一堆碎片化搜索结果

你只需要发起 **一次查询**，
AI Search Hub 就可以帮你 **并行搜索多个平台**。

---

## 为什么做这个项目？

很多所谓“全网搜索”方案，最后都会变成一套非常重的工程系统：

- 写爬虫
- 跑浏览器
- 处理登录态
- 处理验证码和风控
- 一个个平台单独适配
- 关键词不断重调
- 结果还要手工整理

AI Search Hub 选择另一条路：

> **直接复用平台已经优化好的搜索能力。**

平台已经把搜索质量、排序逻辑、数据接入和交互体验做得很强了。
AI Search Hub 做的事，就是把这些能力统一起来，变成一个 Agent 可直接调用的 Skill。

---

## 核心价值

- **一次查询，同时搜索多个平台**
- **多 Provider 并行搜索**
- **直接复用平台原生搜索能力**
- **无需维护爬虫**
- **无需辛苦绕反爬**
- **无需调试浏览器搜索流程**
- **无需反复调关键词**
- **开箱即用，适合 Agent**
- **方便继续扩展更多 Provider**

---

## 架构说明

AI Search Hub 不是一个重型搜索引擎，
也不是一个大型爬虫框架。

它本质上是一个轻量级的 **搜索能力聚合层**。

```text
用户 / Agent
    -> 一次查询
    -> AI Search Hub
        -> Gemini
        -> Grok
        -> 豆包
        -> 元宝
        -> 文心一言
        -> 通义千问
    -> 多平台搜索结果
    -> 统一输出
```

### 工作方式

1. **接收一次查询**
   用户或 Agent 只需要输入一次问题。

2. **并行分发到多个平台**
   AI Search Hub 会把同一个问题同时发送到多个平台。

3. **让各平台搜索自己最擅长的数据世界**
   不同平台去搜索它们最有优势的内容生态。

4. **统一聚合结果**
   多个平台的返回内容会被整理成标准输出。

5. **返回给你的工作流或 Agent 使用**
   可直接接到 Agent、自动化流程、研究系统、监控系统中。

---

## 支持 / 目标接入的平台

| 平台 | 擅长方向 |
|---|---|
| Gemini | Google / 网页搜索 |
| Grok | X / Twitter 搜索 |
| 豆包 | 抖音 / 中文内容生态 |
| 元宝 | 微信公众号 / 中文内容补充 |
| 文心一言 | 中文互联网搜索扩展 |
| 通义千问 | 中文互联网搜索扩展 |
| 更多平台 | 持续扩展 |

---

## 搜索覆盖面

通过聚合不同平台已经优化好的原生搜索能力，
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

重点不是你自己去一个个平台写爬虫，
而是：

> **借助平台已经连接好的数据世界，直接完成多平台搜索。**

---

## 配置应该怎么写？

如果你现在 README 里只是想放一个 **配置示例**，建议写成下面这种形式：

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

这个配置不代表项目里现在一定已经有这样一个 YAML 文件，
它更像是一个概念示例，用来告诉用户：

- Hub 层负责并行调度
- Provider 层负责启用哪些平台
- 每个平台有自己擅长的搜索角色

如果后面真实实现用的是 JSON、Python dict 或 env，也可以再调整。

---

## 请求示例

```json
{
  "query": "最近 AI 编程产品在不同平台的用户反馈",
  "providers": ["gemini", "grok", "doubao", "yuanbao"],
  "mode": "parallel"
}
```

## 返回示例

```json
{
  "query": "最近 AI 编程产品在不同平台的用户反馈",
  "results": [
    {
      "provider": "gemini",
      "summary": "Google / 网页搜索结果摘要"
    },
    {
      "provider": "grok",
      "summary": "X / Twitter 搜索结果摘要"
    },
    {
      "provider": "doubao",
      "summary": "抖音 / 中文内容摘要"
    },
    {
      "provider": "yuanbao",
      "summary": "微信公众号 / 中文网页内容摘要"
    }
  ]
}
```

---

## FAQ

**这是一个爬虫框架吗？**
不是。它是一个搜索能力聚合 Skill。

**是不是还得自己维护每个平台的浏览器自动化？**
这正是 AI Search Hub 想减少的负担。

**是不是还得一直调关键词？**
相比传统搜索流程会少很多，因为它尽量复用平台已经优化好的搜索能力。

**为什么这对 Agent 很重要？**
因为 Agent 需要的是可调用的搜索能力，而不是一堆脆弱的浏览器脚本。

**能不能继续加新的平台？**
可以。这个设计本来就是轻量、可扩展的。

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

欢迎提交 Issues 和 PR。

如果你也认同未来的搜索不应该是 **再写一个更重的爬虫系统**，
而应该是 **更聪明地把现有 AI 搜索入口统一起来**，欢迎一起参与。

---

## Disclaimer

AI Search Hub 的目标是以务实、可持续的方式复用平台原生能力。
请遵守你接入平台对应的服务条款、平台政策和适用法律。

这个项目关注的是聚合与编排，不是绕过平台规则。

---

## Final Line

**One Query. All Search.**
不用从零重建搜索。
直接接入平台已经打磨好的搜索能力。
