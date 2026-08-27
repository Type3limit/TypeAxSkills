# 开源实践依据

仅在用户要求依据、希望迁移成熟开源实践或结论依赖当前项目政策时读取。以下资料用于提炼框架，不要求机械复制其具体工具或组织结构。

- [Kubernetes 社区角色与 OWNERS](https://github.com/kubernetes/community/blob/main/community-membership.md)：把代码质量评审与整体接受批准分开，并按代码区域授予责任。
- [Kubernetes Production Readiness Review](https://github.com/kubernetes/community/blob/main/sig-architecture/production-readiness.md)：从反馈、规模、支持、禁用和恢复角度进行独立阻断评审。
- [Linux 补丁生命周期](https://docs.kernel.org/process/2.Process.html)：设计、早期评审、子系统树、`-next` 集成、主线、稳定版与长期维护形成连续阶段。
- [Linux 维护者职责](https://docs.kernel.org/maintainer/feature-and-driver-maintainers.html)：维护者是持续响应和处理问题的角色，而不是荣誉头衔。
- [Rust 评审政策](https://forge.rust-lang.org/compiler/reviews.html)：要求理解相关代码的人评审，检查大局、性能、平台和下游影响，明显回归优先回滚。
- [Rust CI 与 bors](https://rustc-dev-guide.rust-lang.org/tests/ci.html)：对准备合并的结果运行完整测试，并按需执行性能与生态验证。
- [Rust LLM 使用政策](https://forge.rust-lang.org/policies/llm-usage.html)：LLM 评审只能作为建议，不能替代作者自审或人类判断。
- [CPython Buildbots](https://devguide.python.org/testing/buildbots/) 与 [核心成员责任](https://devguide.python.org/core-team/responsibilities/)：跨平台持续验证，合并者负责修复或回滚后续问题。
- [CPython AI 工具指南](https://devguide.python.org/contrib/project/generative-ai/)：贡献者对 AI 辅助内容负责，应详细自审、能够解释并保持改动聚焦。
- [Chromium 测试基础设施](https://www.chromium.org/developers/testing/)：贡献者写测试，评审者要求测试，try servers 承担本地无法覆盖的平台验证。
- [PostgreSQL CommitFest](https://wiki.postgresql.org/wiki/Commitfest)：为评审和测试保留专门节奏，避免补丁在发布前集中堆积。
- [Google Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html)：一个变更聚焦一件事，把相关测试放在同一变更中，并分离重构与行为修改。
- [OpenSSF Scorecard](https://scorecard.dev/)：将分支保护、代码评审、持续验证、模糊测试、静态分析、依赖和发布安全变成可检查项目。
- [SLSA Build Provenance](https://slsa.dev/spec/v1.2/build-provenance)：记录制品由何种源码、依赖和构建环境产生，以支持验证和追溯。
- [smell-check（原 pragmatic-clean-code-reviewer）](https://github.com/Zhen-Bo/smell-check)：以明确范围、证据类型、例外排除、降级说明和部分结果提高 AI 静态审计的可复现性；这里借鉴其审计协议，不移植固定异味规则或阈值。

上述链接最后核验于 2026-08-27。若结论依赖当前政策或工具能力，应重新访问官方来源；无法访问时标注日期和未核实范围，不要把历史资料表述为当前事实。
