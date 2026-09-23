# <能力名称> Delta Spec

## 归属

- 主体类型：`DEL` / `MOD`
- 主体ID：`DEL/<deliverable-id>` / `MOD/<module-id>`
- 主要实现层：`<Application|Framework|Native|HAL|Kernel>`（MOD 填写）
- 能力ID：`DEL/<deliverable-id>/<capability-id>` / `MOD/<module-id>/<capability-id>`
- Delta路径：`specs/{deliverables,modules}/<id>/<capability-id>/spec.md`
- 长期归属Spec：`<本仓库 docs/ 下对应 spec.md 的准确路径>`
- 上游前置概要设计：`AOSP/docs/changes/<upstream-change-id>/`

本文件记录**开发过程的事实**：实施结果与前置概要设计不一致时，以这里为准；完成后合入长期归属的八文件，本 Delta 随工作区冻结为开发记录。

## ADDED Requirements

### Requirement: `<DEL|MOD>-<SUBJECT>-<CAPABILITY>-REQ-001` <需求名称>

<规范性正文：用 SHALL 表达，中文叙述、英文关键词。只写本主体在自己边界上可验证的行为。>

#### Scenario: `<REQ-ID>-S01` <场景名称>

- **GIVEN** <前置条件>
- **WHEN** <触发动作>
- **THEN** <可观察结果>

## MODIFIED Requirements

### Requirement: `<REQ-ID>` <需求名称>

<复制修改后的完整需求及全部场景。>

## REMOVED Requirements

### Requirement: `<REQ-ID>` <需求名称>

**Reason**：<删除理由>
**Migration**：<迁移影响>
