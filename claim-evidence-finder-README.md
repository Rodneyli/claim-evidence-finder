# 🔍 Claim Evidence Finder

> **你说一句话，AI 自动找出学术界关于这句话的所有证据。**
>
> 拆解论点 → 多轮搜索学术论文 → 评估信源 → 输出 APA 格式研究报告

[![Skill Format](https://img.shields.io/badge/skill-agentskills.io-blue)](https://agentskills.io)
[![Platform](https://img.shields.io/badge/platform-Hermes%20Agent-7c3aed)](https://hermes-agent.nousresearch.com)
[![Category](https://img.shields.io/badge/category-research-green)]()
[![Version](https://img.shields.io/badge/version-1.0.0-brightgreen)]()
[![License](https://img.shields.io/badge/license-MIT-lightgrey)]()

---

## 🤔 解决了什么问题

你在群里跟人争论一个观点，想说「有研究表明……」，但说不出具体是哪个研究。

这个 Skill 帮你做到：**输入一句你想验证的话，它自动搜遍学术数据库，找到所有相关论文，评估信源质量，输出带完整引用的证据报告。**

---

## 🚀 快速安装

```bash
hermes skills install github:Rodneyli/claim-evidence-finder
```

也可以手动复制 `SKILL.md` 到 `~/.hermes/skills/research/claim-evidence-finder/`。

---

## ⚡ 零配置，马上能用

**不需要申请任何 API**。纯靠 Web Search 就能跑通完整流程：

```
你说：「多任务处理降低工作效率」

它自动：
  1. 拆解论点 → 因果型断言，关键变量：多任务→效率，领域：认知心理学
  2. 多轮搜索 → OpenAlex（2.5亿论文） + Web Search + arXiv
  3. 评估信源 → 相关度★★★ + 权威性 + 时效性 + 反方验证
  4. 输出报告 → APA 7 格式，完整引用
```

---

## 📊 输出效果

```
📚 证据报告：多任务处理降低工作效率

## ★★★ 直接支持
1. Madore et al. (2020)
   📄 Memory failure predicted by attention lapsing and media multitasking
   🏛 Nature  |  引用 175 次
   💡 媒体多任务→注意力漂移→记忆力下降，因果路径清晰

## ★★☆ 间接支持
2. Van Der Schuur et al. (2018) — 系统综述，272次引用
3. Wammes et al. (2018) — 课堂真实场景实验

## ⚖️ 反方验证
未找到站得住脚的反方证据。

## 🧠 综合评估
该论断有坚实的学术证据支撑。从 Nature 到系统综述，
研究一致指向多任务处理损害认知表现。
```

---

## 🔧 两种模式

| 模式 | 数据源 | 精度 | 配置 |
|------|--------|------|------|
| **零配置** | Web Search | ⭐⭐⭐ | 无 |
| **学术增强** | OpenAlex + Semantic Scholar | ⭐⭐⭐⭐⭐ | 两个免费 API Key |

### 升级到学术增强模式（5分钟）

1. 注册 [OpenAlex](https://openalex.org/)（免费，100 req/s）
2. 注册 [Semantic Scholar](https://semanticscholar.org/product/api)（免费，可选）
3. 创建 `.env` 文件：

```bash
OPENALEX_API_KEY=你的key
SEMANTIC_SCHOLAR_API_KEY=你的key  # 可选
```

接入后能拿到：引用量、期刊级别、TLDR 摘要、DOI 链接。

---

## 🗂️ 文件结构

```
claim-evidence-finder/
├── SKILL.md          # Skill 主文件（加载使用）
└── README.md         # 本文件
```

---

## 🎯 适用平台

| 平台 | 支持 |
|------|------|
| Hermes Agent | ✅ 原生 |
| Claude Code | ✅ 兼容 agentskills.io |
| Codex CLI | ✅ 兼容 agentskills.io |
| ChatGPT（手动用） | ✅ 复制 Prompt 即可 |

---

## 🧪 触发方式

在对话中说以下任一关键词即可激活：

- 「帮我找证据」「这个说法有依据吗」
- 「有什么论文支持」「citation needed」
- 「帮我验证这个观点」「文献支撑」

---

## 📖 完整工作流

```
用户输入 → 拆解论点 → 搜索策略 → 多轮搜索 → 信源评估 → 输出报告
```

详见 [SKILL.md](./SKILL.md) 的「完整工作流」章节。

---

## ❓ 常见问题

**Q: 跟 Kimi/豆包的论文搜索有什么区别？**
A: Kimi 接的是自己的论文库，Claim Evidence Finder 默认接 OpenAlex（2.5 亿+论文）和 Semantic Scholar，覆盖面更广。而且它有系统化的信源评估流程（相关度+权威性+时效性+红旗标记），不只是搜论文。

**Q: 真的不需要 API Key？**
A: 零配置模式纯靠 Web Search，对所有 AI Agent 都通用。配置 API 后精度更高，但不是必须。

**Q: 会搜到假论文吗？**
A: 不会。Skill 有明确纪律：禁止编造来源。每个来源都通过实际搜索找到，并提供完整 DOI 供验证。

**Q: 怎么定制引用格式？**
A: 默认 APA 7，支持 GB/T 7714（中文期刊格式），可指定 MLA、Chicago 等。

---

## 🙋 作者

**Rodney** — AI 知识博主，运营「🦉 和Lee一起学AI」。

- 📕 小红书：和Lee一起学AI
- 🎵 抖音：和Lee一起学AI
- #分享一个宝藏skill

---

## 📄 License

MIT — 自由使用、修改、分享。欢迎 PR 改进。
