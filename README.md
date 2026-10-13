# ai-writing-debug

**学术文本的 AI 写作痕迹诊断与修复**

针对**防御性写作**（替审稿人提前攻击自己）、**元语言过多**（值得注意的是 / 综上所述）、**套话与机器腔**、以及**代笔身份错配**——
逐层定位到具体句子并给出改写，而**不只是打分**。

---

## 为什么需要它

市面上的工具几乎只做一件事：**给分**。告诉作者「这段 AI 味重」——然后作者看着那句话，改不动。

**缺的是另一半：定位到句、说明成因、给出改写。**

---

## 四个轴，互不重叠

| 轴 | 问的问题 | 参考文件 |
|---|---|---|
| **叙事姿态** | 这段话是不是在替审稿人提前攻击自己？ | [`references/defensive-writing.md`](references/defensive-writing.md) |
| **表达层** | 词 / 句 / 段 / 章，哪一层有机器腔？ | [`references/four-layer-scan.md`](references/four-layer-scan.md) |
| **文体适配** | 这句话放在**这个文体**里对吗？ | [`references/medium-rules.md`](references/medium-rules.md) |
| **身份匹配** | **这个身份的人**，写得出这句吗？ | [`references/persona-match.md`](references/persona-match.md) |

⚠️ **混着查会互相误报。** 一份稿子可以同时命中多个轴，但要**分轮查**。

---

## 一条最容易搞反的原则

**口语节拍 ≠ 口语化。**

| ✅ 保留 | ❌ 清理 |
|---|---|
| 「三条原因。」——小节起拍 | 「卡在哪」——口语动词 |
| 「一共四条，先说在这里。」——回指清楚 | 「分量最重」——程度夸张 |

**判据：它在承担节奏功能，还是在偷懒？**

同一条规则的判法**随文体翻转**——「那篇综述」在讲稿里可以，在幻灯片上必须点名（听众翻不回去）。
所以工作流第 0 步是**定文体与身份**。这一步不定，后面全是误报。

---

## 🔴 铁律：只改表达，不改事实

不新增信息、事实、方法、指标、结论、落点或格式。
发现内容本身有问题——**报给用户，不要替他补**。

---

## 来源与署名

本 skill 整合自作者 2026-09 至 2026-10 的科研写作流程文档。**其中两部分改编自开源项目：**

| 文件 | 来源 | 许可 |
|---|---|---|
| `references/defensive-writing.md` | GitHub 开源 skill 仓库集群（2026-10-12 检索核实） | — |
| `references/four-layer-scan.md` | [`huangwb8/ChineseResearchLaTeX`](https://github.com/huangwb8/ChineseResearchLaTeX) 的 `nsfc-humanization` v1.2.0 | MIT |
| `references/medium-rules.md` | 作者原创（87 处口语化清理的实证归纳） | — |
| `references/persona-match.md` | 作者原创（一次真实审稿工作中发现的越界问题） | — |

**改编不是原创。** 二次分发时请保留上表。

---

## 许可

MIT。改编部分的原始署名见上表，需一并保留。
