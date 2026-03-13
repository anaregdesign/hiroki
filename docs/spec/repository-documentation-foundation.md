# Repository Documentation Foundation

## Summary

この repository は、hiroki という人格を時間が経っても読み取れる形で残すための documentation hub である。単なる skill 置き場や技術メモの集積ではなく、hiroki の判断の仕方、重視する技術、繰り返し使う workflow、そしてそれらをどう整理して読めるようにするかを一貫した構造で残す。

## User Problem

この repository にはすでに skill や関連 document があるが、何を中心に記録する場所なのかが曖昧だと、技術 catalog と人格の記録が混ざってしまう。repository-level の spec がないと、どの document を追加すべきか、どこまで書けば十分か、どの階層に置けば読み手が迷わないかを判断しづらい。

## Users and Scenarios

- hiroki 自身が、自分の人格、価値観、技術、skill を時間が経っても見直せる形で残したいとき
- collaborator が、hiroki が何を得意とし、何を標準とし、どういう前提で判断する人なのかを理解したいとき
- AI agent や tooling が、この repository を hiroki に関する安定した source of truth として参照したいとき

## Scope

- この repository を「hiroki という人格を残すための repository」として定義する
- hiroki の特徴、価値観、技術、skill をどのような domain に分けて document 化していくかを定義する
- 読み手が迷わず辿れるように、repository の大まかな整理方針と document の置き方を定義する
- 将来の spec や summary document が、この foundation を起点に分岐できる状態を作る
- この repository では spec を日本語で記述する方針を明確にする

## Non-Goals

- すべての技術や skill の詳細 document をこの 1 file に書き切ること
- 各 skill の詳細な更新 operation や maintenance 手順をこの spec に含めること
- source skill file を overview document だけで置き換えること
- application architecture や cloud topology の個別判断をここで固定すること

## User-Visible Behavior

- 読み手は、この repository が hiroki の人格と技術的実践を残すための場所だと明確に理解できる
- 新しい spec や document を追加するとき、人格、技術、skill、repository 構造のどこに属する内容かを判断できる
- repository のどこに何が置かれているかが大づかみに分かり、深い運用手順を読まなくても navigation できる
- 今後 document が増えても、人格を中心にした repository であるという軸がぶれない

## Acceptance Criteria

- spec が、この repository の中心目的を「hiroki という人格を残すこと」として明記している
- spec が、技術や skill の記録が人格や判断様式の記録とどう結びつくかを説明している
- spec が、主要な読者と利用場面を示している
- spec が、現在の repository の大まかな整理方針を説明している
- spec が、詳細な更新 operation を書かずに repository の structure を理解できる粒度でまとまっている
- spec が、この repository では spec を日本語で記述する方針を示している

## Edge Cases

- 1 つの内容が、技術選好でもあり working style でもある場合がある
- 一部の domain は先に skill source だけが存在し、上位 summary が後から追加される場合がある
- 後から新しい persona や domain の整理軸を導入しても、既存 document の意味が失われないようにする必要がある
- repository の構造を整理し直しても、「hiroki を残す repository」であるという中心目的は維持される必要がある

## Constraints and Dependencies

- すでに存在する skill source や関連 document と矛盾しない high-level summary にする
- implementation 手順ではなく、読み手が repository の意味と構造を理解できる説明を優先する
- spec は日本語で記述し、必要な技術用語だけ英語を使う
- この foundation spec は high level に保ち、後続の個別 spec が具体化を担当する

## Documentation Domains

- 人格と判断様式:
  hiroki が何を大事にし、どう判断し、どう他者と協働するかを記録する。
- 技術と実践領域:
  hiroki が扱う technology、platform、framework、problem space を記録する。
- skill と再利用可能な workflow:
  どの skill が何を担い、どの場面で使われ、他の skill とどう関係するかを記録する。
- repository の整理方針:
  document、spec、plan、skill source が repository の中でどう住み分けるかを記録する。
- navigation と発見性:
  人や agent が必要な document にどう辿るかを記録する。

## Repository Organization

- `docs/spec/`:
  repository の目的、振る舞い、期待値を残す durable な spec を置く。ここにある spec は日本語を基本とする。
- `docs/plans/`:
  個別の作業単位を進めるための一時的な execution plan と、その archive を置く。ここは repository の長期的な人格記録そのものではなく、作業の履歴を補助する場所である。
- `develop/skills/`:
  hiroki の技術的実践を具体的な skill として保持する場所であり、再利用可能な workflow や guardrail の source を持つ。
- repository 全体:
  高レベルの思想は `docs/spec/`、実行中の作業管理は `docs/plans/`、具体的な skill の本体は `develop/skills/` に置き、役割を分けて整理する。

## Structure Expectations

- 1 つの file にすべてを詰め込まず、repository-level の overview から個別 domain の spec や skill source に辿れる構造を保つ
- 人格を説明する document と、技術的な skill source を混同せず、それぞれの役割が分かるように整理する
- 後から domain や hierarchy を増やしても、既存 document を大きく崩さず拡張できるようにする
- repository の整理は、見た目の分類ではなく「hiroki をどう残すか」という目的に従う

## Links

- この更新の active plan は、作業中のあいだ `/docs/plans/plan.md` に置かれる。
