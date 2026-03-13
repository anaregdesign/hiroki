# 人格保存のための Skill Hierarchy

## Summary

この specification の目的は、repository の人格を保存することにある。
そのために、Skill は directory structure 自体から人格と役割が読み取れるように整理する。

## Core Rule

- Skill は `/<persona>/<workstream>/<task>/<skill-name>/` の形で配置する
- top-level directory は `persona` を表す
- `workstream`、`task`、`skill-name` はその `persona` 配下で順に責務を表す
- 新しい Skill を追加するときも、同じ hierarchy に従って整理する
