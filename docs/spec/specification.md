# 人格保存を優先した Skill Hierarchy

## Summary

この specification は、repository の人格 `hiroki` を保存しながら、skill 配置を `develop/skills/` 直下の flat な構成から、`職種 / 業務 / タスク / skill` の hierarchy へ移行する方針を定義する。人格は具体的な個人言及ではなく、repository の分類原則と directory structure で保存する。

## User Problem

現在の `develop/skills/` は software development の分類としては理解しやすいが、人格を保存する repository という目的には寄り切れていない。skill 一覧が技術機能の flat な catalog に見えやすく、どの視点で整理されている repository なのかが伝わりにくい。

## Users and Scenarios

- maintainer が、skill を単なる tool 集ではなく repository の人格を表す構成として整理したいとき
- collaborator が、skill を読む前に「どの persona の、どの業務の、どの task に属するものか」を把握したいとき
- AI agent が、repository の hierarchy から skill の文脈を推測したいとき

## Scope

- 現在の mirrored skill を `engineer` 配下へ移設する
- その人格を具体的なプロフィール記述ではなく hierarchy と分類原則で保存する
- `engineer / workstream / task / skill-name` の path を repository の新しい基準にする
- bootstrap document、repository foundation spec、AGENTS の mapping を新 path に合わせて更新する
- Codex Home の shared skill symlink が新 path を指すように揃える

## Non-Goals

- 新しい persona として `researcher`、`marketer`、`citizen`、`ally` の document を今回追加すること
- 各 skill の中身そのものを別の責務へ作り変えること
- skill 名そのものを変更すること
- skill 更新手順の詳細運用をこの spec に追加すること

## User-Visible Behavior

- skill source は `engineer/<workstream>/<task>/<skill-name>/` から辿れる
- `develop/skills/` は skill の canonical location ではなくなる
- repository の人格は具体的な説明文ではなく directory structure と分類で読み取れる
- repository document は新しい hierarchy を前提に path と説明が揃う
- Codex Home の shared skill は従来どおり既存の skill 名で呼べるが、repo 側の実体 path は新 hierarchy になる

## Acceptance Criteria

- 現在の 3 つの mirrored skill が `engineer/<workstream>/<task>/<skill-name>/` 配下に移設されている
- 人格保存の方針が明記され、具体的な個人言及に依存していない
- `spec-driven-workflow` は spec-first delivery を表す task 配下に置かれている
- `enforce-react-spa-architecture` は SPA application 作成 task 配下に置かれている
- `azure-spa-clean-architecture-bootstrap` は `create-single-page-application` task 配下で `enforce-react-spa-architecture` の Azure extension として置かれている
- repository の durable document が新 path を参照している
- Codex Home の symlink が新 path を指している

## Edge Cases

- 1 つの skill が複数 task にまたがって見える場合でも、canonical path は 1 つだけにする
- skill の leaf name を短い generic name に変えると Codex Home の skill 名や install path がぶれるため、leaf は既存 skill 名を維持する
- task slug は将来調整される可能性があるが、今回の移行では読みやすさより安定性を優先する
- relative link を持つ skill は移設後に sibling path の更新が必要になる

## Constraints and Dependencies

- mirrored skill は repo と Codex Home で同じ実体を指す構成を保つ
- directory structure は人格保存の durable な表現として維持する
- relative reference が壊れないように、skill 間リンクと published GitHub path を更新する
- repository foundation spec の人格中心の整理方針と矛盾しない path にする
- bootstrap 文章は新 source path を使うが、install 先の skill 名は従来どおり維持する

## Target Hierarchy

- `engineer/planning/spec-driven-workflow/`
- `engineer/development/create-single-page-application/enforce-react-spa-architecture/`
- `engineer/development/create-single-page-application/azure-spa-clean-architecture-bootstrap/`

## Links

- この変更の active plan は、作業中のあいだ `/docs/plans/plan.md` に置かれる。
