# csharp-agent-lab
“AI 智能体已从最初的代码辅助工具，演变为能够自主规划、执行、调试甚至部署复杂任务的‘数字协作伙伴’。” “未来的软件工程师将不再仅仅是‘代码的编写者’，而更像是‘AI 系统的架构师、编排者与守护者’。”

周期：4 周（28 天）
每日时长：≤ 30 分钟
目标：在 4 周内通过每日小步快跑掌握 Agentic Workflows、Tool Use、Advanced RAG 的核心概念与可运行最小实现（C# 优先）。
产出形式：每日小文件或代码片段；每周小 Demo + README；最终整合项目 final-project/README.md。
仓库结构建议:
README.md
LEARNING_PLAN.md
src/
tests/
docs/
demo/
final-project/

第 1 周 合并任务（单 Agent 原型）
周目标：理解 Agent 概念并完成单 Agent 最小可运行原型（需求分析 → 代码生成 → 日志与测试）。
每日时长上限：≤ 30 分钟。

| 日 | 任务要点 | 产出 |
| --- | --- | --- |
| Day1 | 阅读白皮书要点并写 150 字笔记 | ``docs/day1.md`` |
| Day2 | 在 C# 中发起一次 ChatCompletion 请求并打印响应 | ``src/day2/LLMCall.cs`` |
| Day3 | 设计 prompt 模板，将自然语言需求转为结构化 JSON 任务清单 | ``src/day3/ReqAgent.cs`` |
| Day4 | 用 LLM 生成代码片段并写入临时文件，保存示例 | ``src/day4/CodeGen.cs`` |
| Day5 | 为关键函数添加 Serilog 日志并写 1 个 xUnit 单元测试 | ``tests/day5`` |
| Day6 | 周复盘：列出 3 个改进点并写 200 字复盘 | ``docs/week1-retro.md`` |
| Day7 | 缓冲：补未完成项或阅读扩展资料 | — |

第 2 周 合并任务（多 Agent 与 Orchestrator）
周目标：实现多 Agent 协作与轻量 Orchestrator，加入仲裁与回滚机制。
| 日 | 任务要点 | 产出 |
| --- | --- | --- |
| Day8 | 设计任务分解规则与分配伪代码 | ``docs/day8-task-decomposition.md`` |
| Day9 | 实现并发调用 Agents 的轻量 Orchestrator（超时/重试） | ``src/Orchestrator/Orchestrator.cs`` |
| Day10 | 实现仲裁 Agent（基于置信度或投票）并写示例 | ``src/Arbiter/Arbiter.cs`` |
| Day11 | 定义 ``ITool`` 接口并实现 Git 模拟工具适配器 | ``src/Tools/GitToolAdapter.cs`` |
| Day12 | 在 Orchestrator 中加入回滚点与人工确认钩子 | ``tests/integration/orchestrator-rollback.test`` |
| Day13 | 周复盘：准备多 Agent demo 的 README 与运行脚本 | ``demo/week2-demo.md`` |
| Day14 | 缓冲：补未完成项 | — |

第 3 周 合并任务（Tool Use 深入）
周目标：把外部服务封装为安全工具，支持 LLM 函数调用、沙箱执行与审计。
| 日 | 任务要点 | 产出 |
| --- | --- | --- |
| Day15 | 编写工具安全检查清单（最小权限、输入校验） | ``docs/tool-security-checklist.md`` |
| Day16 | 实现工具适配器模板（Adapter Pattern） | ``src/Tools/AdapterTemplate.cs`` |
| Day17 | 实现函数调用解析器：解析 LLM 的 function_call 并映射到本地方法 | ``src/Runtime/FunctionCallExecutor.cs`` |
| Day18 | 为工具执行添加超时、资源限制与异常捕获（沙箱） | ``src/Sandbox/SandboxExecutor.cs`` |
| Day19 | 实现审计日志格式并记录示例条目 | ``logs/audit-sample.log`` |
| Day20 | 周复盘：运行安全检查并修复高优先项 | ``docs/week3-retro.md`` |
| Day21 | 缓冲：补未完成项 | — |

第 4 周 合并任务（Advanced RAG 与最终整合）
周目标：实现 Embeddings 与混合检索，构建 Code-QA Agent，并将 Orchestrator、Tools、RAG 整合为可运行流水线 demo。
| 日 | 任务要点 | 产出 |
| --- | --- | --- |
| Day22 | 用 C# 调用 Embedding API 并上传向量到向量 DB 或模拟 | ``src/RAG/EmbeddingUploader.cs`` |
| Day23 | 实现文档分片（chunking）与关键词+向量混合检索逻辑 | ``src/RAG/HybridRetriever.cs`` |
| Day24 | 用内存图或轻量图 DB 实现实体关系并做基于实体的检索示例 | ``src/RAG/GraphRetriever.cs`` |
| Day25 | 实现 Code-QA Agent：问题→检索→生成答案并引用来源 | ``src/Agents/CodeQAAgent.cs`` |
| Day26 | 设计并记录检索评估指标，比较不同策略效果 | ``docs/rag-evaluation.md`` |
| Day27 | 最终整合：Orchestrator + Tools + RAG 整合成可运行流水线 demo | ``final-project/`` |
| Day28 | 总结与演示：准备最终演示文档并列出后续学习路线 | ``final-project/demo-notes.md`` |

每日提交模板
标题：WeekX-DayY [短目标]  
内容：
今日目标：一句话
完成情况：已完成 / 部分完成 / 未完成 + 说明
产物路径：path/to/file
遇到的问题：1-3 条
明日计划：一句话
