# WorkBuddy Guidelines

> 给 LLM Agent 的 6 条行为铁律。基于 Andrej Karpathy 的编码哲学，新增安全与交付原则。中英双语，即贴即用。

> AI coding behavioral guidelines for LLM agents. Based on Andrej Karpathy's philosophy. Bilingual, copy-paste ready.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Platform: WorkBuddy](https://img.shields.io/badge/Platform-WorkBuddy-6c5ce7)](https://workbuddy.ai)
[![Framework: Agent Guidelines](https://img.shields.io/badge/Framework-Agent_Guidelines-00b894)](https://agentskills.io)
[![Inspired by Andrej Karpathy](https://img.shields.io/badge/Inspired_by-Karpathy-ff6b6b)](https://github.com/karpathy)

---

## Quick Install · 快速安装

### WorkBuddy 用户

```
1. 打开 WorkBuddy → 设置 → Custom Instructions
2. 粘贴 GUIDELINES.zh.md 全部内容
3. 保存。Agent 从此不再瞎写代码。
```

Open WorkBuddy → Settings → Custom Instructions → Paste → Save. Done in 10 seconds.

### 其他 Agent（Claude / Cursor / Copilot 等）

同样操作：把 `GUIDELINES.md` 内容粘贴到你工具的 system prompt 或 rules 配置里。

---

## The Problems · 解决的问题

Andrej Karpathy 观察到 LLM 编码 Agent 的四大共性失败模式：

| 问题 | 表现 |
|---|---|
| 沉默假设 | Agent 假设而非询问，隐藏困惑，不给权衡方案 |
| 过度工程 | 臃肿抽象，死代码残留，100 行的问题产出 1000 行 |
| 副作用修改 | 改动不理解的代码，"顺手优化"引入无关变更 |
| 无验证闭环 | 声称完成但没测试，没有可衡量的成功标准 |

**额外针对的问题：** 中文开发环境的 GBK 编码、Windows 路径怪癖、CJK 字符工具兼容性。

---

## The Solution · 6 大原则

| 原则 | 对抗的失败模式 |
|---|---|
| **1. Think Before Coding** | 沉默假设、隐藏困惑、缺失权衡 |
| **2. Simplicity First** | 过度工程、臃肿抽象、死代码 |
| **3. Surgical Changes** | 无关编辑、触碰不属于你的代码 |
| **4. Goal-Driven Execution** | 无验证、"没测试就算完成" |
| **5. Security** | 凭据泄露、不可逆文件操作 |
| **6. Delivery** | 编码混乱、非标准输出、重复踩坑 |

> 原则 5（安全）和原则 6（交付）是我们基于生产环境和中文环境实战新增的。

---

## Files · 文件

| 文件 | 语言 | 用途 |
|---|---|---|
| [`GUIDELINES.md`](./GUIDELINES.md) | EN | 英文版 — 粘贴到 Agent system prompt |
| [`GUIDELINES.zh.md`](./GUIDELINES.zh.md) | 中文 | 中文版 — 原生本地化，非机翻 |

---

## Key Insight · 核心洞察

> *"LLMs are remarkably good at looping until a specific goal is met... Don't tell it what to do. Give it success criteria and let it run."*
> — Andrej Karpathy

这是原则 4（目标驱动执行）的理论基础。Agent 不需要逐步指令，需要的是**清晰、可验证的终点线**。

---

## How to Know It's Working · 生效标志

- ✅ Diff 极简——只改了真正需要的行
- ✅ 无过度工程导致的代码重写
- ✅ 澄清性问题出现在**实施之前**
- ✅ PR 干净、聚焦、易审查

---

## Tradeoff · 权衡

准则偏向**谨慎优先于速度**。琐碎任务（拼写修正、明显的单行修改）自行判断跳过完整流程。目标是减少非琐碎工作上的昂贵错误——而非增加官僚流程。

---

## Compatible Platforms · 兼容平台

| 平台 | 状态 |
|---|---|
| WorkBuddy | ✅ 原生支持 |
| Claude Code | ✅ 兼容 |
| Cursor | ✅ 兼容 |
| GitHub Copilot | ✅ 兼容 |
| 其他 Agent 工具 | ✅ 粘贴即用 |

---

## License · 许可证

MIT — 详见 [LICENSE](./LICENSE)。

---

如果这些准则让你的 Agent 变靠谱了，给个 ⭐ Star。

有问题或建议 → [GitHub Issues](https://github.com/jany22259-arch/workbuddy-guidelines/issues)
