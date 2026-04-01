# 工作方法论 (Methodology)

> 记录从实践中总结的最佳实践和工作原则。持续更新。

## 核心理念

**瓶颈不是 AI 的能力，而是信息的可达性。**

让 AI 去找信息，你做决策者，不是搬运工。

## 工作原则

### 1. 记忆外化

把项目记忆写成文件放在仓库里，而不是依赖 AI 平台的内置记忆：
- 文件可见、可编辑、可版本控制
- 每个新会话通过读取文件获得上下文
- 重要决策立即写入 `memory/decisions.md`

### 2. 小闭环优先

不要一开始就追求完整架构。先做最小闭环：
1. 提一个具体任务
2. AI 执行并交付
3. 审查结果，确认或修改
4. 记录经验和决策

验证通过后再扩展到更复杂的任务。

### 3. 资产积累

每次会话产生的有价值内容都应存入仓库：
- 数据 → `assets/data/`
- 分析报告 → `deliverables/`
- 决策 → `memory/decisions.md`
- 新的工作方法 → `memory/methodology.md`

### 5. 记忆更新需用户确认

每次更新以下文件前，必须先向用户展示变更内容并获得明确确认：
- `memory/decisions.md` — 决策日志
- `memory/context.md` — 项目上下文
- `memory/status.md` — 项目状态
- `memory/methodology.md` — 工作方法论
- `deliverables/` 下的认知报告和分析文档

**确认格式：**

```
确认更新项目记忆
即将修改：
- memory/decisions.md — 新增 X 条决策
- memory/status.md — 更新进度
- deliverables/XXX — 更新内容摘要
是否确认？
```

用户确认后才执行写入和 git 推送。

## 常见问题处理

### 新会话开始时
1. 读取 `CLAUDE.md` 了解项目背景
2. 读取 `memory/context.md` 了解用户信息
3. 读取 `memory/status.md` 了解当前进度
4. 读取 `memory/decisions.md` 了解已有决策

### 完成任务后
1. 将交付物放入 `deliverables/`
2. 更新 `memory/status.md` 的进度
3. 如有新决策，追加到 `memory/decisions.md`
4. 如有新经验，更新 `memory/methodology.md`
