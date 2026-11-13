# GPT-6 Astra 指令审计与优化

2026-09-11 执行，09-12 补核归档。授权范围为数学 Skill 与仓库维护指令的本地优化。

## 依据与改动

- 官方指导支持明确授权后的持续执行、按需加载规则及具体的验收条件。历史审计通过官方 HTML 核验，所给短链接未作为证据。[Astra 模型指导](https://developers.openai.com/api/docs/guides/latest-model) · [Codex 最佳实践](https://learn.chatgpt.com/guides/best-practices) · [Build skills](https://learn.chatgpt.com/docs/build-skills) · [AGENTS 发现机制](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- AGENTS 聚焦授权和长期边界，检查点与恢复集中到 workflow，胶囊仅保留持久背景。TST-REG-004 和 TST-EVID-001 明确验证范围和实际输出证据。
- Skill 合并题干复述与输出路由，补同题追问分支；职责状态描述验收依赖与回退。RUN-R8-001 与 P-CORRECT-1 对齐，仅定位过程错误时索取过程；OUT-CH-001 及输出列表统一先分析选项再给答案。三份参考仍由入口直接路由。
- 数学方法、考纲快照及未见题资产沿用原版本。按当时基线，AGENTS、Skill、胶囊与新增 workflow 合计由 18,025 降至 8,833 个 Unicode 字符（−51.0%）。没有 token、延迟或质量 A/B 数据。

## 历史验收

- 首轮 24 个公开用例中，SYN-TRG-N-02 生成学习规划，属阻断；补范围外服务分流后复测失败与同类场景，再跑全量。SYN-REL-03 仅要求核实来源，修正了无条件求值断言，并新增 SOURCE-01 验证同时求值与核实来源的请求。保留两轮实际输出。[初始输出](../../evals/dxsm-math/results/astra-forward-initial.json) · [最终输出](../../evals/dxsm-math/results/astra-forward-final.json)
- 最终 24 个公开场景、5 个补充场景通过。SYN-REL-02 有一条非阻断措辞问题，“交换行列”应写为“交换两行或两列”。[行为验证](../../evals/dxsm-math/results/astra-validation.md)
- 全部原固定题重跑。纠正 3 处旧题型或定位，补线代覆盖后 37/37 通过。独立解决 4 处答案册差异，旧报告保留原记录并附勘误。恢复时临时报告已不可读，最后一题补核后归档。12 道历史未见题未重跑，也未用于调优。[固定回归](../../evals/dxsm-math/results/astra-fixed-regression.md)
- 当时通过 Markdown 链接、一层引用、24/37/12 YAML（73 个唯一 ID）、310 个唯一规范定义、37 条固定题映射、53 条实际输出及快照哈希、资源边界和 diff 检查。官方 quick validator 缺 PyYAML 退出 1，Ruby 等价校验通过；当时 PATH 无 `skills-ref`。[静态校验](../../evals/dxsm-math/results/static-validation.md)

该次审计未安装依赖或执行提交、push、tag、发布、reset。文件清单与完整前版说明见 Git 历史。
