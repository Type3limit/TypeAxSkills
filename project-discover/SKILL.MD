---
name: project-discover
description: Discover and document an unfamiliar codebase into a progressive-disclosure `.rules/` knowledge base for AI agents — a tiny always-loaded entry (CLAUDE.md/AGENTS.md) that routes to on-demand per-module docs, so agents never re-read the whole repo. Use when onboarding to a new or large repo, when the user asks to "understand / summarize / document the project", wants to stop re-explaining the codebase to every AI agent, or asks to build a `.rules/` or agent knowledge base. Cites code by symbol/method name (never line numbers), uses parallel subagents to deep-read modules, links to rather than duplicates existing docs, and verifies every citation against source.
---

# Project Discover

把对陌生/大型代码仓库的认知，归纳成一套**渐进展开的 `.rules/` 知识库**：极小的常驻入口（CLAUDE.md / AGENTS.md）→ 路由总表（`.rules/README.md`）→ 按需加载的分模块文档 → 链接到既有深度文档。一次性投入，换后续每个 agent 不必重读全仓、按任务快速定位。

## 核心原则（不可妥协）

1. **渐进展开**：L0 常驻入口极小 → L1 路由表 → L2 主题文档（按 `load_when` 命中才读）→ L3 既有 `doc/` 深度方案。
2. **符号定位，绝不写行号**：引用代码一律用 类/函数/枚举名 + 文件名，**不写行号**——行号随代码漂移、留不住，按符号名搜索即可跳转。
3. **链接不复制**：既有的深度文档、计划、schema 只**链接**，不搬运内容。
4. **准确优先**：拿不准的标「（待核实）」，**绝不编造** API/类名/流程；每条论断都应能用 grep 在源码验证。
5. **本地优先**：`.rules/`、`CLAUDE.md`、`AGENTS.md` 默认加入 `.gitignore`（除非用户明确要入库）——它们靠磁盘读取生效，与 git 跟踪无关。

## 工作流（checklist）

0. **侦察**：读 CLAUDE.md/AGENTS.md/README、`git log`/`git status`、顶层目录与构建文件；建立分层与模块的心智模型；识别进行中工作（计划文档、已改未提交文件）。
1. **对齐范围**（问用户，见 REFERENCE「决策问题」）：文档深度（骨架+逐步填充 / 一次性全量深读）；入口覆盖（CLAUDE.md / AGENTS.md / 是否镜像 `.cursor/rules`）；与既有 `doc/` 的关系（只链接 / 迁入）。
2. **建骨架**：建 `.rules/` 目录树；**先手写 `overview.md` 作为格式范本**，定下统一文档规范（见 REFERENCE「文档规范」）。
3. **派 subagent 并行深读**：按模块分簇，每个 subagent 深读源码并写自己负责的 L2 文档，严格遵循统一规范（见 REFERENCE「subagent 派发模板」）。不要一个 agent 包揽全仓。
4. **写路由与约定**：`.rules/README.md`（含「我要做 X → 读哪些」场景表 + 全量清单 + 给 agent 的使用协议 + 维护约定）、`conventions.md`、`workflows/build-verify.md`。
5. **同步入口**：给 CLAUDE.md 加「文档导航」段、新建/更新 AGENTS.md，二者都指向 `.rules/README.md`；顺手修正 subagent 在源码里查出的、入口文件里的事实错误。
6. **核对**：派 subagent（或自检）确认每个被引用的**符号在当前源码确实存在**、漂移的及时修正；跑断链 / 格式 / 残留行号 sweep（命令见 REFERENCE）。
7. **本地化**：把 `.rules/`、`CLAUDE.md`、`AGENTS.md` 加进 `.gitignore`。
8. **演练验收**：挑 2-3 个代表性任务，从 README 场景表走一遍，确认能 1-2 跳命中正确文档、并按符号名 grep 到真实代码。

## 安装 / 移植

本 skill 为 Anthropic Agent Skills 格式（`SKILL.md` + frontmatter），把本目录整个放进任一运行时的 skills 目录即可：`~/.claude/skills/`、`~/.codex/skills/`、`~/.hermes/skills/`。

详细文档规范、`.rules/` 目录模板、subagent 派发与核对话术、frontmatter 模板、`.gitignore` 片段、sweep 命令、可参考的社区范式 → 见 [REFERENCE.md](REFERENCE.md)。
