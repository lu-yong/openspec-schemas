# aosp-repo schema

AOSP owning repository 的**实施工作区** schema（OpenSpec 自定义，不 fork 内置 schema）。

## 用途

按 AOSP 文档模型的三段变更工作流（ADR-0100：前置概要设计 → 实施工作区 → 定稿），
本 schema 定义第二段：各 owning repository 在 `openspec/changes/<change-id>/` 的
开发期工作区，四件 artifact 齐全：

| Artifact | 内容 |
| -------- | ---- |
| `proposal.md` | 范围、受影响主体、上游前置概要设计指针 |
| `specs/**/spec.md` | Delta：记录开发过程的事实，`## 归属` + ADDED/MODIFIED/REMOVED |
| `design.md` | 实施方案细化（与上游设计的差异 + 落地决策） |
| `tasks.md` | 共享执行清单（Codex/Qoder 走 `/opsx-apply`，Pi 回填勾选） |

## 关键纪律

- 完成动作：先把 Delta 合入本仓库 `docs/` 八文件，再
  `openspec archive <change-id> --skip-specs` 冻结工作区；
  `openspec/specs/` 保持为空，八文件是唯一权威。
- 需求正文规范性句式用 SHALL（中文叙述、英文关键词）。
- 实施与前置概要设计不一致时，以本工作区的 Delta 为准，不回改上游。

## 安装

用 `install-openspec-aosp-repo` skill 安装到目标仓库的 `openspec/schemas/aosp-repo/`，
或手工：

```bash
git clone --depth 1 https://github.com/lu-yong/openspec-schemas /tmp/os-schemas
cp -R /tmp/os-schemas/aosp-repo <repo>/openspec/schemas/aosp-repo
openspec schema validate aosp-repo
```

然后在目标仓库 `openspec/config.yaml` 里设置 `schema: aosp-repo`。
