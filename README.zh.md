# WorkBuddy 行为指南

> LLM Agent 编码行为准则。灵感源自 [Andrej Karpathy](https://github.com/karpathy) 的 LLM 编码哲学。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

---

## 要解决的问题

正如 Andrej Karpathy 指出的，LLM 编码 Agent 存在共同的失败模式：

- **沉默假设** — Agent 自己假设而不提问，隐藏困惑，不呈现备选方案
- **过度设计** — 臃肿的抽象层，死代码残留，100 行能解决的问题写成 1000 行
- **副作用修改** — 改动或删除自己不懂的代码，塞进无关的"优化"
- **无验证闭环** — 写完就当完成，不测试，没有可衡量的成功标准

这些问题在**中文开发环境**中更容易放大：编码乱码、Windows 路径坑、PowerShell 对中文的不友好……

---

## 解决方案

一份文件，**6 条原则**，逐一对应解决：

| 原则 | 解决的问题 |
|------|-----------|
| **先想后做** | 沉默假设、隐藏困惑、缺少权衡 |
| **简洁优先** | 过度设计、臃肿抽象、死代码 |
| **精准改动** | 无关编辑、乱碰他人代码 |
| **目标驱动** | 无验证、写完不管 |
| **安全** | 凭据泄露、不可逆文件操作 |
| **交付** | 编码混乱、非标准输出、重复踩坑 |

---

## 文件说明

| 文件 | 语言 | 用途 |
|------|------|------|
| [`GUIDELINES.md`](./GUIDELINES.md) | EN | 6 条规则 — 复制到 Agent 的 system prompt 中使用 |
| [`GUIDELINES.zh.md`](./GUIDELINES.zh.md) | 中文 | 同上，中文版 — 复制到 Agent 的 system prompt 中使用 |

> **注意**：README 是项目说明，**指南正文在 `GUIDELINES.zh.md` / `GUIDELINES.md` 里**。

---

## 安装使用

### WorkBuddy

把指南复制到 Codex 自定义指令中：

```
1. 打开 WorkBuddy → Codex → Custom Instructions
2. 粘贴 GUIDELINES.zh.md 的全部内容
3. 保存，即生效
```

### 其他 Agent（Claude Code、Cursor、Copilot 等）

同理 — 把 `GUIDELINES.zh.md` 的内容粘贴到对应工具的 "system prompt" 或 "rules" 配置中即可。

---

## 核心洞察

> *"LLM 在循环执行直到满足特定目标方面异常出色……不要告诉它做什么，给它成功标准，然后看它运行。"*
> — Andrej Karpathy

这就是第 4 条原则（目标驱动）的底层逻辑。Agent 不需要保姆式指令——它需要一个清晰、可验证的终点线。

---

## 生效标志

几个信号说明指南起作用了：

- **diff 最小化** — 只有该改的那几行变了
- **不因过度设计返工** — 不会写着写着越写越复杂
- **问题问在犯错前** — Agent 先确认再动手，而不是做完了才发现不对
- **PR 干净聚焦** — 审查者一眼看清改了什么

---

## 权衡说明

本指南偏向**谨慎而非速度**。对于简单任务（比如改个拼写、明显的单行修复），自行判断，不用走完整流程。目标是减少非平凡任务上的代价高昂的错误——**不是制造官僚主义**。

---

## 致谢

本文档的核心理念受 [Andrej Karpathy](https://github.com/karpathy) 对 LLM 编码行为的观察启发，由 [multica-ai/karpathy-guidelines](https://github.com/multica-ai/andrej-karpathy-skills) 社区实践推动。

---

## 许可证

MIT — 详见 [LICENSE](./LICENSE)。
