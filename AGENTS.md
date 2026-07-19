## dmSlogAnalyzer

go语言编写一个达梦数据库SQL跟踪日志文件解析/分析命令行CLI工具



### 功能

- 高性能的达梦数据库 SQL 日志解析器，支持流式处理
- 



### 技术栈

- 4层**DDD 架构（领域驱动设计）**和**TDD（测试驱动开发）**设计思想
- go 1.25.10+
- Cobra 
- SQLite 数据持久化（modernc.org/sqlite）【WAL 模式】
- [按需可选]中文字体内嵌（SIL 协议，无版权风险）：Noto Sans SC + 系统默认字体（保底策略）
- [按需可选]统一入口运行配置文件：`application.yml`. 参数优先级: 命令行参数 > 环境变量 > application.yml 配置文件 > 默认值






### 日志系统

支持多日志级别（DEBUG、INFO、ERROR），并提供文件输出和日志轮转功能。

- 日志级别：支持 DEBUG、INFO、ERROR 三个级别，可通过配置文件指定日志级别，默认 INFO 级别
- 日志格式：`[YYYY-MM-DD HH:MM:SS.SSS] [级别] [线程ID|进程ID] [模块:行号] - 日志内容`
- 日志输出：支持文件输出和终端输出，文件输出路径默认 `logs/`，日志文件按日期轮转（每日一个文件），保留 32 天日志，自动清理过期日志
- 日志内容：统一使用中文，清晰记录操作行为、执行结果、错误信息，便于问题排查和审计
- 日志内容不能记录敏感信息，必须严格遵循脱敏策略，禁止记录：密码、完整身份证号、手机号
- 文件命名格式：`项目名-YYYYMMDD.log`，例如 `dma-20231225.log`

- 时间戳格式：YYYY-MM-DD HH:MM:SS.SSS  本地时间，不含时区



### 文档和注释

- 项目文档统一存储 `docs/` 目录，按顺序标号命名中文文档
- 注释、日志内容统一使用中文
- 统一错误处理，所有错误信息都必须使用中文，禁止打印明文密码等敏感信息



### 真实测试数据

- `D:\19-Training\Rust\dmdb\sqllog`  sql跟踪日志文件路径



### 约束和禁止条件

- 禁用 npm 包管理，可用pnpm，bun
- 禁用Maven，可用gradle
- 使用uv管理python 软件包，禁止使用pip/venv/pipenv/poetry
- 必须编译配置优化，从源头减小体积
- 



### 参考

- https://github.com/guangl/dm-database-sqllog2db  # 已下载本地路径： `D:\19-Training\Rust\dmdb\dm-database-parser-sqllog`
- https://github.com/guangl/dm-database-parser-sqllog # `D:\19-Training\Rust\dmdb\dm-database-parser-sqllog`
- https://crates.io/crates/dm-database-parser-sqllog

- `D:\19-Training\java\dmlogAnalysis-V3.0.0`





---

# AI Assistant Guidelines (Karpathy Standard)

## Core Principles

1. **Clarify first, don't assume**
   If the request is ambiguous, unclear, or underspecified, ask brief clarifying questions before writing code or proceeding. Do not guess intent.

2. **Simplicity over cleverness**
   Prefer simple, readable, minimal code. Avoid over-engineering, unnecessary abstractions, fancy patterns, or premature optimization. Keep solutions straightforward.

3. **Minimal changes only**
   Make only the smallest necessary edits to solve the problem. Do not refactor unrelated code, do not reformat entire files, do not change coding style arbitrarily. Stay within the scope of the request.

4. **Goal-driven work**
   Stay focused on the immediate task. Do not add extra features, improvements, or "helpful" additions that were not requested. Solve exactly what is asked.

## Code Style

- Write clean, standard, idiomatic code for the language.
- No overly verbose comments; code should speak for itself.
- Keep functions and logic concise.



## 语言强制规则（必须严格遵守）

1. 所有回复、解释、对话、说明必须**全程使用中文**，禁止出现任何英文。
2. 不允许切换语言，全程保持纯中文交互。
3. 解释、说明、思考过程、总结、步骤描述，全部使用中文。