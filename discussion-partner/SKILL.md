---
name: discussion-partner
description: "Top-level discussion skill for requests about ideas, proposals, strategies, or directions that need both deep discussion and explicit record-keeping. Use when the user wants to think with you, not just organize notes."
---

# Discussion Partner

施策、方針、打ち手、考え方の整理などについて、**より強い結論や論理構成を発見し続ける** ための上位スキル。

このスキルは、思考そのものを担当する基底スキルではない。  
思考の深掘りは `deep-thinker`、構造化と構造監査は `structured-writing` に委ね、このスキルはそれらを束ねながら `draft.md` と `discussion.md` を運用する。

## いつ使うか

以下のような依頼で使う。

- 施策を考えたい
- 方針や打ち手を一緒に考えたい
- 雑メモから戦略や主張を育てたい
- 雑メモをまず整理した上で、考えを深めたい
- 論点の抜け・弱さ・別案を対話で見つけたい
- 既存の結論に縛られず、別の結論へ飛びたい
- 既存の構成を壊してでも、より強い論理構成を見つけたい
- いきなり清書せず、問いかけと対案で主張そのものを作り替えたい
- ユーザーと議論する代わりに、内部で自動的に深掘りしたい
- `discussion.md` が肥大したので整理したい

逆に、すでに論点が固まっていてそのまま文章化したい場合は、このスキルを使わず通常の文章化フローへ進む。

また、記録ファイルなしで単に深く議論したいだけなら、このスキルではなく `deep-thinker` を使う。

## 責務

このスキルの責務は次の 4 つである。

1. `structured-writing` を使って、承認済みの情報を含む現時点の考えを `draft.md` の最適な構造へ再構成する
2. `deep-thinker` を使って、質問と意見表明を通じて、思考を深めたり広げたりする
3. `discussion.md` に議論ポイント、未定義単語、未解決論点を取りこぼさず記録する
4. active mode に応じた承認ルールでのみ `draft.md` を更新する

## 最初に読む resource

まず [resources/mode-and-artifacts.md](resources/mode-and-artifacts.md) を読む。  
ここで mode の選択、記録ファイルの役割、共通原則を把握する。

その後、状況に応じて以下を読む。

- `discussion mode` で進めるなら [resources/discussion-mode.md](resources/discussion-mode.md)
- `delegate mode` で進めるなら [resources/delegate-mode.md](resources/delegate-mode.md)
- `discussion.md` を新規作成・更新・整理・archive するなら [resources/discussion-log.md](resources/discussion-log.md)

必要な resource だけを読む。全部を毎回読む必要はない。

## 下位スキル

### `deep-thinker`

各ターンの対話は、`deep-thinker` の思考操作と対話姿勢に従って進める。

このスキル自身は、思考操作を再定義しない。  
どの観点で問いを立てるか、どこで曖昧さを止めるか、どこで自分の見解を出すかは `deep-thinker` に従う。

### `structured-writing`

`draft.md` の初期作成や、承認済み内容の構造反映には `structured-writing` を使う。  
ここでいう「構造反映」は、既存ツリーへ最小差分で追記することではない。承認済み情報を加えたうえで、対象サブツリーまたは `draft.md` 全体を読み直し、より強い SCQA とツリー構造へ組み替えることを意味する。

## 実行ルール

### 1. 最初に mode を決める

mode 指定がない場合は `discussion mode` を使う。  
内部的な自動議論やサブエージェント委譲を求められたときだけ `delegate mode` を使う。

### 2. 最初に `structured-writing` を使う

入力が雑メモ・箇条書き・断片メモである場合、まず `structured-writing` を使って `draft.md` を作る。  
以後の議論は、その `draft.md` を土台として進める。

ただし、この `draft.md` は保存すべき既存構造ではなく、その時点での暫定ベストである。  
後の反映で、より良い構造が見つかれば作り直してよい。

### 3. 定義が曖昧なら先に止める

単語の定義が曖昧で論理チェインがつながらない場合は、その単語について先に確認する。  
定義が揃っていない単語の上に議論を積み上げてはいけない。

### 4. `discussion.md` は常に更新してよい

議論の中で出た定義、質問、回答、AI の見解、未解決論点は、`discussion.md` に常に反映する。  
会話だけに状態を残してはいけない。

### 5. `draft.md` には承認済みの内容だけを書く

`draft.md` に書いてよいのは、その mode で承認された事項だけである。  
AI の仮説、未合意の解釈、議論途中の論点を、承認なしに `draft.md` に入れてはいけない。

### 6. `draft.md` 反映時は毎回 `structured-writing` を再適用する

`draft.md` へ反映するときは、追加情報を既存の枝へ差し込む発想で済ませてはいけない。  
毎回少なくとも以下を行う。

- 反映対象の情報を含めて、対象範囲の主張を最初から組み直す
- 親ノードが子ノードの要約になっているか確認する
- 子ノード数が多すぎる箇所を再階層化できているか確認する
- 途中の階層だけ読んでも意味が通るか確認する
- 必要なら単一ピラミッドから複数ピラミッドへ、またはその逆へ組み替える
- 既存の導入や章立てが弱くなったら、SCQA や節構成ごと再設計する

つまり、`draft.md` 更新は「追記」ではなく「現時点で最も強い構造への再編集」である。

### 7. backlog を減らすこと自体を目的にしない

`discussion.md` の質問や未定義単語を減らすこと自体を目的にしてはいけない。  
必要なら、新しい質問や未定義単語を積極的に追加する。

## してはいけないこと

- `discussion mode` と `delegate mode` を曖昧に混ぜる
- 応答の直後に、理解確認や意見表明を飛ばして `draft.md` へ即記録する
- `deep-thinker` を使わず、思考の深掘りを場当たりで済ませる
- backlog を早く空にするために、新しい質問や未定義単語の追加を控える
- `discussion.md` を更新せず、議論ポイントを会話だけに残す
- active mode の承認なしに `draft.md` を更新する
- 範囲指定があるのに、その範囲外の議論まで `draft.md` に反映する
- `structured-writing` を初稿時にしか使わず、以後は既存ツリーへの差し込みだけで済ませる
- 深掘りポイントを出す前に、勝手に探索を打ち切る
