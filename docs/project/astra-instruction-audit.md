# GPT-6 Astra 指令审计与优化

官方核验与主要执行日期：2026-09-11；恢复补核与归档：2026-09-12。范围：根 AGENTS、数学 SKILL、三份 references、全部分层规范、恢复/验收/发布流程。仓库无独立 workflow 脚本或 CI，本轮将维护流程集中到 `docs/project/workflow.md`。用户授权为本地优化；英语 v2、安装和发布不在本次授权内。

## 官方依据

已实际检索并打开官方正文，使用 GPT-6 Astra 原名，没有替换目标模型：

- [GPT-6 Astra 模型指导](https://developers.openai.com/api/docs/guides/latest-model)：针对已授权工作明确持续推进；消除 Skill/AGENTS 中歧义、冲突和无必要停顿；具体约束写作及验证范围，按实际需要配置委派。
- [Codex 最佳实践](https://learn.chatgpt.com/guides/best-practices)：AGENTS 保留实用的持久约束，长流程按任务引用；给出目标、上下文、约束与完成条件。
- [Build skills](https://learn.chatgpt.com/docs/build-skills)：利用名称/描述、入口、资源的渐进披露；入口具备精确触发边界。
- [AGENTS 发现机制](https://learn.chatgpt.com/docs/agent-configuration/agents-md)：项目指令自动加载，层级与体积会影响实际进入上下文的内容。

用户提供的短链接未作为证据依赖；通过明确的官方域名检索解析到上述模型指导。部分 `.md` 页面因网页工具不支持该响应类型读取失败，已改用成功取得的 HTML 正文。采用本机 `openai-docs` 和 `skill-creator` 指导，不复制整篇官方提示词。

以下是基于仓库证据的实施判断，不是官方为本仓库给出的性能保证。项目没有模型 API 或路由配置，不新增 API 参数、不修改本机模型/推理档位；当前宿主模型设置由用户与环境管理。

## 发现与处理

| 发现 | 已实施改进 | 保留的约束 |
|---|---|---|
| AGENTS 的允许/禁止/职责/完成定义重复表达同一门槛 | 合并为权威授权、开工、边界、执行、交付五节；已授权维护直接继续 | 新产品方案门、英语待批准、发布单独授权 |
| 每次维护套用主观 95% 理解门槛 | 改用具体未决问题与完成条件；历史英语需求事实保留 | 实质范围或正确性冲突仍需裁决 |
| 检查点流程在 AGENTS、SPEC、胶囊反复维护 | workflow 为唯一细则来源；胶囊仅保留持久背景和恢复指针 | 每个可验证步骤落盘、复读与压缩恢复保护 |
| Skill 多次复述输入规则，七步流程又重复输出目录 | 题干复述一次，按核心契约与分支路由组织 | 完整题意、教学依据、条件、双自然方法与明确答案 |
| 十职责状态模型可能被当成固定 Agent/工具流水线 | 明确它只描述验收依赖与错误回退，可合并分类/线索/规划 | 输入确认、方法合法性、最终核验先后依赖 |
| RUN-R8-001 泛称判题需过程，与 P-CORRECT-1 仅答案可判结果不同 | 统一为定位过程错误才请求过程，结果仍可独立判断 | 不编造用户过程；FOLLOW-02 实际验证 |
| 分层规范有同题追问规则，入口未明确 | 增加同题局部补充路由，区分澄清/纠错/定理/新题 | 关键数学解释完整可检查 |
| 最大输出列表与 OUT-CH-001 选项顺序不同 | 列表统一为先选项分析、后最终答案 | 全选项分析及同类干扰合并 |
| 每类修改的测试范围不够明确 | TST-REG-004 分层；TST-EVID-001 要求当前实际输出证据 | 数学阻断修复全部固定回归、首次完整 24/36/12 门槛 |
| 三份 references 已有实用细节与一层链接 | 保留正文，入口明确读取条件 | 考纲元数据、题型分类、工具/冲突规则 |

未改写数学方法、考纲快照、未见题资产、README、许可证或用户原有提交。固定回归发现旧索引与结果错误后，校正定位和分类、补足覆盖并给旧报告添加日期勘误，保留原执行记录。前向验证发现范围外规划服务仍可能输出，已补明确拒绝服务分流，并按原门槛扩大至全部固定回归。没有把数学澄清当成可随意猜测的常规实现选择；没有因通用简洁偏好删除已确认的数学教学契约。

## 可测量的变化

按 Git HEAD 与当前 UTF-8 文本的 Unicode 字符计数；不是 tokenizer 统计：

| 文本 | 原行数 → 当前 | 原字符 → 当前 |
|---|---:|---:|
| AGENTS.md | 266 → 53 | 7102 → 2477 |
| 数学 SKILL.md | 169 → 69 | 3434 → 2613 |
| 恢复胶囊 | 194 → 43 | 7489 → 1977 |

新增 workflow 为 51 行、1766 字符，计入维护场景负担；AGENTS + Skill + 胶囊 + workflow 合计从18025降至8833字符，减少51.0%（不含按需SPEC、历史与测试证据）。同一任务读取后复用，安装后的解题不加载workflow。未做旧/新版本同条件延迟、token或质量A/B，不能将字符精简量等同于性能提升。

## 当前验证

恢复后的结构验证已通过：28个Markdown、本地链接、一层引用、三份YAML的24/37/12用例及73个唯一ID、310个唯一规范定义、37条固定题报告映射、两份前向JSON的53条实际输出与Skill快照哈希均有效。无文本控制字符、行尾空白或仓库PDF，`git diff --check`通过。

官方 `python3 /Users/lyn-77/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/dxsm-math` 实际因缺 PyYAML 退出 1；未安装依赖。读取脚本后以 Ruby 标准 YAML 和对应字段/命名/占位规则做等价检查通过；`skills-ref` 不在 PATH。未把等价检查称作官方脚本运行成功。

首轮两个独立子 Agent 完成 24 个公开场景，实际输出保存在 `evals/dxsm-math/results/astra-forward-initial.json`。发现 SYN-TRG-N-02 生成学习规划，属于阻断；已修复服务范围分流并启动全量复测。失败用例、课程/刷题安排及估分请求复测已通过，随后按 TST-REG-002 启动全部 36 道固定回归。

SYN-REL-03 只请求来源核实，原断言却无条件要求数学结果。保留该实际回答，将断言明确为“若附带数学结果则必须正确”，并另用 SOURCE-01 同时请求积分计算与来源核实，检查可独立完成的数学任务。该修正不是把没有执行的求值记为通过。

修复后24个公开场景阻断断言与5个补充场景通过，保留1条非阻断措辞观察，见 [行为验证](../../evals/dxsm-math/results/astra-validation.md)。原固定题全部重跑，纠正3处旧题型/定位并补足线代覆盖后，37/37通过，见 [固定回归](../../evals/dxsm-math/results/astra-fixed-regression.md)。4处答案册差异已独立解决，旧报告已加日期勘误。12道历史未见题未重跑或用于调优，不计入本次运行。

2026-09-12恢复时临时报告不可读，只补核最后一题并归档；已将子Agent回传短结果与及时归档要求加入workflow，保留真题原文不入库的边界。没有安装、提交、push、tag或发布；用户授权的reset没有使用。

## 修改文件

- [AGENTS.md](../../AGENTS.md)
- [docs/SPEC.md](../SPEC.md)
- [docs/project/astra-instruction-audit.md](astra-instruction-audit.md)
- [docs/project/lessons.md](lessons.md)
- [docs/project/progress.md](progress.md)
- [docs/project/workflow.md](workflow.md)
- [docs/spec/00-governance.md](../spec/00-governance.md)
- [docs/spec/01-scope-trigger-input.md](../spec/01-scope-trigger-input.md)
- [docs/spec/02-runtime-responsibilities.md](../spec/02-runtime-responsibilities.md)
- [docs/spec/03-solving-teaching-correction.md](../spec/03-solving-teaching-correction.md)
- [docs/spec/04-output-contract.md](../spec/04-output-contract.md)
- [docs/spec/07-testing-acceptance.md](../spec/07-testing-acceptance.md)
- [docs/spec/08-packaging-installation.md](../spec/08-packaging-installation.md)
- [docs/spec/09-traceability.md](../spec/09-traceability.md)
- [docs/spec/99-context-capsule.md](../spec/99-context-capsule.md)
- [evals/dxsm-math/local-regression-index.yaml](../../evals/dxsm-math/local-regression-index.yaml)
- [evals/dxsm-math/results/astra-fixed-regression.md](../../evals/dxsm-math/results/astra-fixed-regression.md)
- [evals/dxsm-math/results/astra-forward-final.json](../../evals/dxsm-math/results/astra-forward-final.json)
- [evals/dxsm-math/results/astra-forward-initial.json](../../evals/dxsm-math/results/astra-forward-initial.json)
- [evals/dxsm-math/results/astra-validation.md](../../evals/dxsm-math/results/astra-validation.md)
- [evals/dxsm-math/results/fixed-regression-report.md](../../evals/dxsm-math/results/fixed-regression-report.md)
- [evals/dxsm-math/results/static-validation.md](../../evals/dxsm-math/results/static-validation.md)
- [evals/dxsm-math/synthetic-cases.yaml](../../evals/dxsm-math/synthetic-cases.yaml)
- [skills/dxsm-math/SKILL.md](../../skills/dxsm-math/SKILL.md)
