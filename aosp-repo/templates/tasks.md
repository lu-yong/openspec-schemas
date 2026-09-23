# Tasks

## 1. 实施

- [ ] 1.1 <任务描述> 并验证 <测试、命令或可观察行为>
- [ ] 1.2 <任务描述> 并验证 <测试、命令或可观察行为>

## 2. 长期文档回写

- [ ] 2.1 把 `specs/<路径>/spec.md` 的 Delta 合入 `docs/<对应主体目录>/spec.md` 并验证标题与 ID 一致
- [ ] 2.2 按受影响情况更新 `docs/<对应主体目录>/` 其余八文件并运行 `python3 tools/validate_docs.py repository <repo>`

## 3. 收尾

- [ ] 3.1 执行 `openspec archive <change-id> --skip-specs` 冻结工作区并确认 `openspec/specs/` 仍为空
