# GPT-6 Astra 指令审计与优化

2026-09-11 执行，09-12 补核归档。授权范围为数学 Skill 与仓库维护指令的本地优化。

## 依据与改动

- 官方指导支持明确授权后的持续执行、按需加载规则及具体的验收条件。历史审计通过官方 HTML 核验，所给短链接未作为证据。[Astra 模型指导](https://developers.openai.com/api/docs/guides/latest-model) · [Codex 最佳实践](https://learn.chatgpt.com/guides/best-practices) · [Build skills](https://learn.chatgpt.com/docs/build-skills) · [AGENTS 发现机制](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- AGENTS 聚焦授权和长期边界，检查点与恢复集中到 workflow，胶囊仅保留持久背景。
- Skill 合并题干复述与输出路由，补同题追问分支；职责状态描述推理依赖与回退。RUN-R8-001 与 P-CORRECT-1 对齐，仅定位过程错误时索取过程；OUT-CH-001 及输出列表统一先分析选项再给答案。三份参考仍由入口直接路由。
- 数学方法与考纲快照沿用原版本。按当时基线，AGENTS、Skill、胶囊与新增 workflow 合计由 18,025 降至 8,833 个 Unicode 字符（−51.0%）。没有 token、延迟或质量 A/B 数据。
