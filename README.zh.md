# autonomous-agents-md

一份面向 AI native 开发的 `AGENTS.md`：让编码 agent 自主执行，但保持谨慎。

[English](./README.md) | 简体中文

基于 [andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills) 修改。原版把 [Andrej Karpathy 关于 LLM 编码问题的观察](https://x.com/karpathy/status/2015883857489522876)总结为四条原则。本版本保留了这四条原则，并针对人工监督更少的 agent 做了调整。

## 与原版的区别

原版 `CLAUDE.md` 默认旁边随时有人可以回答问题：有疑问，agent 就停下来问。本版本默认 agent 应该继续推进，只有猜错的代价较大时才停下来。

| 方面 | 原版 `CLAUDE.md` | 本版 `AGENTS.md` |
|---|---|---|
| 遇到不确定 | 不确定就停下来问 | 按风险处理：低风险的歧义做可逆的假设并继续；理解差异重大时才问 |
| 重构 | 不重构没坏的代码 | 不重构无关代码；任务需要时可以重构 |
| 无关问题 | 指出死代码 | 指出死代码、bug 和泄露的密钥；不擅自修复 |
| 他人的工作 | 未涉及 | 保护用户和 agent 的改动；未经许可不丢弃他人的工作 |
| 测试 | 循环直到验证通过 | 另外：不为通过测试而削弱测试；卡住时停下报告 |
| 高风险操作 | 未涉及 | 默认自主；高风险或不可逆操作前先询问 |
| 密钥 | 未涉及 | 不硬编码、不提交、不输出密钥 |
| 连续性 | 未涉及 | 跨会话任务维护进度文件；并行工作各用各的文件 |
| 优先级 | “按需合并” | 项目专属指令优先 |

第 2 节（简单优先）以及第 3、4 节的主体内容与原版相同。

## 使用方法

把 `AGENTS.md` 放在项目根目录。Codex、Cursor 等大多数编码 agent 会直接读取它。Claude Code（v2.1.277 及以上）在项目中没有 `CLAUDE.md` 时会读取 `AGENTS.md`；如果你已经有 `CLAUDE.md`，在里面加一行 `@AGENTS.md` 即可。

项目专属规则优先于通用准则，所以你可以在文件末尾加一节来调整默认行为。比如做 hackathon demo 时：

```markdown
## Project

- Hackathon demo: favor speed over caution; verify by running the app; write tests only for core logic.
```

## 文件说明

- `AGENTS.md`：准则本体
- `AGENTS.zh.md`：中文译文，仅供参考

## 致谢

- forrestchang 的 [andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills)：原版准则（MIT）
- [Andrej Karpathy](https://x.com/karpathy/status/2015883857489522876)：准则背后的观察

## 许可证

[MIT](./LICENSE)
