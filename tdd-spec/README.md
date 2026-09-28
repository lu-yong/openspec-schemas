# tdd-spec schema

以 TDD 为核心的 OpenSpec 自定义 schema（不 fork 内置 schema）。

## 用途

把「需求 → 规格 → 设计 → 接口 → 任务 → 实现」整条链路约束到测试先行：
每个 spec 场景都必须翻译成测试，每个任务都是一个可观察行为的 red → green → refactor 循环。

流程：**(可选 grill) → proposal → specs → design（含架构）→ interface → tasks（TDD 切片）→ apply（red-green-refactor）**

| Artifact | 内容 |
| -------- | ---- |
| `proposal.md` | 变更提案：为什么做、做什么、影响哪些能力（可选 `/grill-with-docs` 先澄清需求） |
| `specs/**/*.md` | Delta 规格：可观察行为契约，每个 Scenario 将成为至少一个测试用例 |
| `design.md` | 技术设计：架构（必填章节）、关键决策、流程、测试策略与接缝 |
| `interface.md` | 接口契约：新增/修改/移除接口的完整约定 + 契约测试 |
| `tasks.md` | 按垂直切片组织的实现任务清单，每个切片对应一个 spec 场景 |

## 关键纪律

- **垂直切片**：一个任务 = 一个可观察行为 = 一轮 red → green → refactor，
  禁止「先写全部测试再写全部实现」的水平拆分。
- **RED 有效失败**：断言失败或引用未实现公共接口导致的编译/类型错误算有效 RED，
  测试自身的拼写/语法/环境错误不算。
- **接缝纪律**：只 mock 系统边界（网络、时间、外部服务），不 mock 内部协作者、不测私有方法。
- 行为未变的场景（MODIFIED 保留 / REMOVED / RENAMED / `skip_specs: true`）写为验证任务，
  不制造失败测试。
- `## Why` 与 `## What Changes` 标题必须保持英文字面量（OpenSpec 解析器依赖），正文用中文。

## 安装

```bash
git clone --depth 1 https://github.com/lu-yong/openspec-schemas /tmp/os-schemas
cp -R /tmp/os-schemas/tdd-spec <repo>/openspec/schemas/tdd-spec
openspec schema validate tdd-spec
```

然后在目标仓库 `openspec/config.yaml` 里设置 `schema: tdd-spec`。
