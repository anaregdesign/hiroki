# 人格保存のための Skill Hierarchy

## Summary

この specification の目的は、repository の人格を保存することにある。
そのために、Skill は directory structure 自体から人格と役割が読み取れるように整理する。
また、`docs/` を除く Skill 関連 directory はすべて `skills/` 配下に集約する。

## Core Rule

- Skill は `/skills/<persona>/<workstream>/<task>/<skill-name>/` の形で配置する
- `skills/` 直下の directory は `persona` を表す
- `workstream`、`task`、`skill-name` はその `persona` 配下で順に責務を表す
- 新しい Skill を追加するときも、同じ hierarchy に従って整理する
