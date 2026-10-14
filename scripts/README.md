# scripts/

**这里是运行版。正本在 [`research-workflow`](https://github.com/crce-ux/research-workflow) 的 `scripts/`**——开发与测试都在那边。

改脚本请改总仓，再同步过来；**不要只改这里**（改了不会回流，两边会岔开）。

| 脚本 | 干什么 | 服务于 |
|---|---|---|
| `check_language.py` | 回指 / 排他性断言 / 空泛量词 / 缩写 / 数字口径 | ② 表达层 · ⑦ 数字漂移 |
| `check_phrases.py` | 措辞九组（自我削弱 / 套话 / 抽象标签 / 演义媒体化 / 自问自答 / 伪对立 / 名词化 / 越级引用 / 连接词堆砌） | ① 叙事姿态 · ② 表达层 |
| `check_persona.py` | 身份匹配机检（只报可疑，不下判决） | ④ 身份匹配 |
| `check_ref_citations.py` | 正文 [n] ↔ 文末编号表 双向核对 | ⑤ 引用幻觉 |
| `verify_pmid_doi.py` | PMID / DOI 反查，确认文献真实存在 | ⑤ 引用幻觉 |
| `renumber_refs.py` | 参考文献重编号 | ⑤ 引用幻觉 |
| `check_metadata_leak.py` | Office / PDF 隐藏元数据体检 | 交付前 |
| `check_skill_structure.py` | 结构校验（官方 Agent Skills 规范）：name / description / 正文长度 / 深链 / **声明落地** |
| `selfcheck.py` | **一条命令自检**：结构 + 语法 + 依赖。见下 |

## 依赖

全部用标准库，无第三方依赖。`verify_pmid_doi.py` 需要联网（走 NCBI E-utilities）。

## 边界

**脚本只做能自动化的那一半。**

- `check_ref_citations.py` 只能核「正文编号 ↔ 文末表」对不对得上——**核不了「这条引文真的支持这句话吗」**
- `check_persona.py` 只报可疑，不下判决；`check_language.py` 命中 ≠ 要改

语义判断必须人工过。

## 自检

```bash
python scripts/selfcheck.py            # 结构 + 语法 + 依赖
python scripts/selfcheck.py --strict   # 结构警告也算失败（CI 用这个）
```

查三样：**结构**（官方规范）· **语法**（逐个编译 `scripts/*.py`）· **依赖**（哪些脚本要装第三方库，只报不判）。
下载本 skill 后想确认「东西是齐的、没坏的」，跑这一条就够。
