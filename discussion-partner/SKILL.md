---
name: discussion-partner
description: "Top-level discussion skill for requests about ideas, proposals, strategies, or directions that need both deep discussion and explicit record-keeping. Use when the user wants to think with you, not just organize notes."
---

# Discussion Partner

施策、方針、打ち手、考え方の整理などについて、**より強い結論や論理構成を発見し続ける** ための上位スキル。

このスキルは、思考そのものを担当する基底スキルではない。  
思考の深掘りは `deep-thinker`、構造化と構造監査は `structured-writing` に委ね、このスキルはそれらを束ねながら `draft.md`、`discussion.md`、`definitions.md` を運用する。

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
3. `discussion.md` に議論ポイントと未解決論点を、`definitions.md` に厳密定義が必要な用語を取りこぼさず記録する
4. active mode に応じた承認ルールでのみ `draft.md` を更新する

## Mode の選び方

このスキルには 2 つの mode がある。

- `discussion mode`: ユーザーと AI が 1on1 で議論する
- `delegate mode`: メイン AI とサブエージェントが自動的に議論する

mode 指定がない場合は、`discussion mode` を使う。
`delegate mode` は、ユーザーが自動的な内部議論やサブエージェント委譲を求めたときに使う。

`discussion mode` は以下のときに使う。

- ユーザー自身と往復しながら考えを深めたい
- 論点の承認主体をユーザーに置きたい
- 対話そのものが成果物の一部である

`delegate mode` は以下のときに使う。

- ユーザーとの往復なしで内部的に深掘りしたい
- 論点を自動的に掘り続けたい
- `definitions.md`、`discussion.md`、`draft.md` を自律的に前進させたい

## 記録ファイルと最重要ルール

このスキルでは、必要に応じて 4 つのファイルを扱う。

- `definitions.md`: 議論全体で使ってよい厳密用語の辞書
- `draft.md`: `structured-writing` によって構造化された現行ドラフト
- `discussion.md`: 対話の進行、質問、回答、未解決論点を保持する作業メモ
- `discussion-archive.md`: `discussion.md` から退避した反映済み要素と過去ログの保管場所

`definitions.md` は議論を支配する最重要リソースである。
`definitions.md` にある用語だけが、ごく一般的な意味から外れた厳密な意味を持てる。
それ以外の言葉は、議論、`discussion.md`、`draft.md`、およびこのスキルを使う AI 自身の思考のすべてで、ごく一般的な意味でしか使ってはいけない。
AI は出力だけでなく、resource の読解、論点整理、質問生成、仮説形成、反論、構造再編の判断まで、`definitions.md` にある用語と一般意味の単語だけで行わなければならない。

一般的な意味のままでは言いたいことが表現できない、またはある概念を毎回長く説明しないといけないときだけ、新しい用語を `definitions.md` に定義する。
その定義は AI が提案してもよいし、ユーザーが直接指示してもよい。

`definitions.md` と `discussion.md` は常に自動更新してよい。
一方で `draft.md` に書いてよい内容は active mode によって変わる。

- `discussion mode`: ユーザーが承認した事項だけ
- `delegate mode`: サブエージェントが収束と判断し、反映を承認した事項だけ

## 共通原則

### 1. 応答の直後に `draft.md` へ即反映しない

相手が答えたら、その内容をすぐ `draft.md` に書いてはいけない。
まず `deep-thinker` に従って、その回答の意味を確認し、必要なら聞き返し、その後で AI の考えを述べる。

### 2. 最初に `definitions.md` を読む

`draft.md` や他の resource を読む前に、まず `definitions.md` を読む。
そこで定義されている用語だけを、その定義に従って解釈する。`definitions.md` にない言葉へ独自の意味を補ってはいけない。
これは出力時の表現制約ではなく、内部思考と解釈の制約でもある。

議論の初めに `draft.md` や他の resource が与えられた場合は、そこに出てくる厳密用語候補を抽出し、`definitions.md` に ` (proposed)` 付きで追加する。
この時点ではまだ人間承認前なので、未承認の用語には明示的に ` (proposed)` を付ける。

### 3. 未解決の論点を忘れない

AI は、思いついた深掘りポイントを会話の流れの中で消してはいけない。
今すぐ掘らない論点も、backlog として保持し続ける。

### 4. 範囲指定があるときは、その範囲の議論だけを `draft.md` に反映する

ここでいう範囲指定は、`draft.md` 上の章や節の範囲ではなく、どの議論までを一旦確定扱いにするかの指定を指す。
ユーザーが「直前のこの話題はまだ pending だけど、その前までを一旦 draft にして」のように言った場合、pending の話題は `discussion.md` に残し、それより前の承認済み議論だけを `draft.md` に反映する。
範囲外の議論まで確定済みとして `draft.md` に混ぜてはいけない。

### 5. 結論も構造も変えてよい

議論の途中で結論や構造が変わってよい。重要なのは、各時点の `draft.md` が SCQA と要約ツリーの原則を満たしていることである。
承認済み情報を `draft.md` に反映するときは、今のツリー構造を守ることを優先してはいけない。既存ツリーへの最小差分の追加ではなく、対象サブツリーまたは全体を再読し、より強い SCQA とツリーへ再構成する。

### 6. context 圧迫を防ぐため、`discussion.md` の反映済み要素は定期的に archive してよい

`discussion.md` が肥大して context を圧迫するなら、反映済み要素と議論ログを `discussion-archive.md` へ移してよい。
ただし、未反映要素は `discussion.md` に残し、未解決論点の探索を失ってはいけない。
`definitions.md` は archive してはいけない。

## 追加で読む resource

状況に応じて以下を読む。

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
一方で、足りない観点の洗い出し、論点の深掘り、追加質問による内容拡張は `structured-writing` の責務ではない。そこはこの `discussion-partner` が担う。

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

単語の定義が曖昧で論理チェインがつながらない場合は、その単語を `definitions.md` に定義すべきか先に確認する。
`definitions.md` にない単語へ独自の意味を勝手に載せたまま議論を積み上げてはいけない。

### 4. `discussion.md` と `definitions.md` は常に更新してよい

議論の中で出た質問、回答、AI の見解、未解決論点は `discussion.md` に、厳密定義が必要な用語は `definitions.md` に常に反映する。
会話だけに状態を残してはいけない。

`definitions.md` で定義した用語以外の言葉は、議論、`discussion.md`、`draft.md`、およびこのスキルを使う AI 自身の思考のすべてで、ごく一般的な意味でしか使ってはいけない。
つまり、AI は内部で解釈するときも、判断するときも、論点を組み立てるときも、`definitions.md` にある用語と一般意味の単語だけで考えなければならない。
一般的な意味のままでは言いたいことが表現できない、または長い説明文を何度も繰り返す必要があるときだけ、新しい単語を定義する。

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

`discussion.md` の質問や、`definitions.md` に置くべき新語提案を減らすこと自体を目的にしてはいけない。
必要なら、新しい質問や新しい用語提案を積極的に追加する。

## してはいけないこと

- `discussion mode` と `delegate mode` を曖昧に混ぜる
- 応答の直後に、理解確認や意見表明を飛ばして `draft.md` へ即記録する
- `deep-thinker` を使わず、思考の深掘りを場当たりで済ませる
- backlog を早く空にするために、新しい質問や新しい用語提案の追加を控える
- `discussion.md` を更新せず、議論ポイントを会話だけに残す
- active mode の承認なしに `draft.md` を更新する
- 範囲指定があるのに、その範囲外の議論まで `draft.md` に反映する
- `structured-writing` を初稿時にしか使わず、以後は既存ツリーへの差し込みだけで済ませる
- 深掘りポイントを出す前に、勝手に探索を打ち切る
