# Persona First Skill Hierarchy

## Summary

この repository の skill 配置を、`develop/skills/` 直下の flat な構成から、`職種 / 業務 / タスク / skill` の hierarchy へ移行する。現在の skill はすべて `engineer` 配下に置き、repo の分類そのものが hiroki の人格と実践を表す構造に寄せる。

## User Problem

現在の `develop/skills/` は software development の分類としては理解しやすいが、hiroki という人格を中心に残す repository という目的には寄り切れていない。skill 一覧が技術機能の flat な catalog に見えやすく、どの視点で整理されている repository なのかが伝わりにくい。

## Users and Scenarios

- hiroki が、skill を単なる tool 集ではなく自分の実践の一部として整理したいとき
- collaborator が、skill を読む前に「どの persona の、どの業務の、どの task に属するものか」を把握したいとき
- AI agent が、repository の hierarchy から skill の文脈を推測したいとき

## Scope

- 現在の mirrored skill を `engineer` 配下へ移設する
- `engineer / development / task / skill-name` の path を repository の新しい基準にする
- bootstrap document、repository foundation spec、AGENTS の mapping を新 path に合わせて更新する
- Codex Home の shared skill symlink が新 path を指すように揃える

## Non-Goals

- 新しい persona として `researcher`、`marketer`、`citizen`、`ally` の document を今回追加すること
- 各 skill の中身そのものを別の責務へ作り変えること
- skill 名そのものを変更すること
- skill 更新手順の詳細運用をこの spec に追加すること

## User-Visible Behavior

- skill source は `engineer/development/<task>/<skill-name>/` から辿れる
- `develop/skills/` は skill の canonical location ではなくなる
- repository document は新しい hierarchy を前提に path と説明が揃う
- Codex Home の shared skill は従来どおり既存の skill 名で呼べるが、repo 側の実体 path は新 hierarchy になる

## Acceptance Criteria

- 現在の 3 つの mirrored skill が `engineer/development/<task>/<skill-name>/` 配下に移設されている
- `spec-driven-workflow` は spec-first delivery を表す task 配下に置かれている
- `enforce-react-spa-architecture` は SPA application 作成 task 配下に置かれている
- `azure-spa-clean-architecture-bootstrap` は Azure 上で SPA を作る task 配下に置かれている
- repository の durable document が新 path を参照している
- Codex Home の symlink が新 path を指している

## Edge Cases

- 1 つの skill が複数 task にまたがって見える場合でも、canonical path は 1 つだけにする
- skill の leaf name を短い generic name に変えると Codex Home の skill 名や install path がぶれるため、leaf は既存 skill 名を維持する
- task slug は将来調整される可能性があるが、今回の移行では読みやすさより安定性を優先する
- relative link を持つ skill は移設後に sibling path の更新が必要になる

## Constraints and Dependencies

- mirrored skill は repo と Codex Home で同じ実体を指す構成を保つ
- relative reference が壊れないように、skill 間リンクと published GitHub path を更新する
- repository foundation spec の人格中心の整理方針と矛盾しない path にする
- bootstrap 文章は新 source path を使うが、install 先の skill 名は従来どおり維持する

## Target Hierarchy

- `engineer/development/deliver-spec-first-change/spec-driven-workflow/`
- `engineer/development/create-single-page-application/enforce-react-spa-architecture/`
- `engineer/development/create-single-page-application-on-azure/azure-spa-clean-architecture-bootstrap/`

## Links

- この変更の active plan は、作業中のあいだ `/docs/plans/plan.md` に置かれる。
