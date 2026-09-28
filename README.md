# openspec-schemas

Custom OpenSpec schemas.

## Schemas

| Schema | 用途 |
| ------ | ---- |
| [`aosp-repo`](aosp-repo/) | AOSP owning repository 的实施工作区：proposal → specs → design → tasks 四件齐全，配套 AOSP 文档模型的三段变更工作流（前置概要设计 → 实施工作区 → 定稿） |
| [`tdd-spec`](tdd-spec/) | 以 TDD 为核心的全流程 schema：（可选 grill）→ proposal → specs → design（含架构）→ interface → tasks（垂直切片）→ apply（red-green-refactor），每个 spec 场景对应至少一个测试 |

安装到目标仓库用 `install-openspec-aosp-repo` skill，或见各 schema 目录内的 README。
