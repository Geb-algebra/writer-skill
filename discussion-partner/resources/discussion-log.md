# Discussion Log

## `definitions.md` の役割

`definitions.md` は、議論全体で使ってよい厳密用語の辞書である。
ここで定義した用語以外の言葉は、議論、`discussion.md`、`draft.md`、およびこのスキルを使う AI 自身の思考のすべてで、ごく一般的な意味でしか使ってはいけない。
これは表現上の制約ではなく、解釈、推論、質問生成、判断の制約でもある。

一般的な意味のままでは言いたいことが表現できない、またはある概念を説明するのに長い説明文を毎回繰り返す必要があるときだけ、新しい単語を定義する。

`definitions.md` に入れてよいのは、少なくとも以下のいずれかを満たす用語だけである。

- この議論や文書のために新しく作った用語
- 一般的な意味とは大きく異なる独自の意味で使う用語
- 一般語だが、この議論では意味を大きく狭めて厳密に使う用語

逆に、以下は `definitions.md` の定義項目にしてはいけない。 `discussion.md` に書く。

- 実装配置、呼び出し順、処理順、運用手順の説明
- 因果、方針、ルール、設計判断の説明
- 例示、補足、長い解説文

## `definitions.md` の形式

`definitions.md` では、各項目を必ず以下の形式の箇条書きで書く。

- **{Term}**: {definition}

AI が提案したが人間がまだ承認していない用語には、行末に必ず `(proposed)` を付ける。
この状態の用語は、ユーザーに承認判断を依頼する対象である。

`{definition}` 部分では、以下だけを使ってよい。

- ごく一般的な意味で使う未定義単語
- `definitions.md` のその項目より上の行で定義済みの用語

つまり、ある定義の中で別の定義済み用語を使いたいなら、その依存先を上に置く。
未定義の専門語を、定義の中にさらに持ち込んではいけない。

## 議論開始時の抽出

議論の初めに `draft.md` や他の resource が与えられた場合は、そこから厳密用語候補を抽出し、`definitions.md` に `(proposed)` 付きで追加する。
この抽出は「その文章で特殊な意味を担っていそうな語」を拾う作業であり、一般語を片っ端から辞書化する作業ではない。

## `definitions.md` 更新後の validation

`definitions.md` に項目を追加・変更したら、その直後に必ず validation を行う。

確認すること:

- 各定義が、ごく一般的な意味の単語と、その項目より上で定義済みの用語だけで書かれているか
- 未定義用語を定義文の中へ持ち込んでいないか
- 新しく依存が増えたなら、依存先が定義より上に並んでいるか

## `discussion.md` の構成

`discussion.md` は、常時更新される作業メモとして少なくとも以下の 3 節を持つ。

## 1. Question Backlog

深掘りポイントをすべて貯める場所。各項目は以下を持つ。

- `ID`
- `Operation`: その問いを生んだ `deep-thinker` の思考操作名。なければ `none`
- `Target`
- `Question`
- `Why This Matters`
- `Priority`
- `Status`: `open` / `active` / `answered` / `reflected` / `parked` / `dropped`

`parked` は「重要だが今は掘らない」、`dropped` は「不要と判断した」を意味する。

## 2. Active Questions

現時点で、次に掘る候補として残しておく問い。

## 3. Answered / Reflected Log

どの回答がいつ得られ、`draft.md` に反映済みかを残す。

## archive 操作

ユーザーが以下のように言ったら、`discussion.md` の archive 操作を行う。

- `discussionを整理して`
- `discussion.md を圧縮して`
- `議論ログを軽くして`
- `discussion をアーカイブして`

この操作の目的は、`discussion.md` を軽くすることであって、未解決論点を捨てることではない。

### Step 1. `discussion.md` を読む

まず `discussion.md` を読み、各項目に付いている状態を確認する。

### Step 2. 状態だけを見て archive 対象を特定する

archive 対象は、`draft.md` と読み比べて判定してはいけない。  
`discussion.md` の各項目に書かれた状態だけを見て、機械的に決める。

archive 対象にしてよいのは、少なくとも以下である。

- `Question Backlog` のうち `Status: reflected` の項目
- `Answered / Reflected Log` にある過去の議論ログ

### Step 3. `discussion-archive.md` に移す

特定した archive 対象を `discussion-archive.md` に移す。  
`discussion-archive.md` がなければ作る。すでに存在するなら追記する。

archive では以下を守る。

- 元の文脈が分かるように、まとまり単位で移す
- 何を archive したか分かる見出しか区切りを付ける
- `discussion.md` から消す前に、必要な情報が archive 側へ移っていることを確認する

### Step 4. `discussion.md` には未反映要素だけ残す

archive 後の `discussion.md` には、未反映要素だけを残す。

残すもの:

- `Question Backlog` のうち未反映の項目
- 今後も掘る必要がある `Active Questions`
- 空にした `Answered / Reflected Log` 見出し

### Step 5. ログ節は空に戻す

`Answered / Reflected Log` は archive 後に空に戻す。  
ただし節そのものは消さず、次の議論を記録できる空の状態で残す。

### Step 6. `draft.md` は勝手に書き換えない

archive 操作は、`discussion.md` の圧縮が目的である。  
別途反映指示がない限り、この操作だけで `draft.md` を新たに書き換えてはいけない。

### Step 7. `definitions.md` は archive しない

`definitions.md` は議論を支配する重要なリソースなので、archive してはいけない。
今ある `discussion.md` の archive 処理を `definitions.md` に適用してはいけない。

## してはいけないこと

- archive 時に、未反映要素まで `discussion.md` から消す
- archive 時に、議論ログを捨てて `discussion-archive.md` へ移さない
- 過去に出た深掘りポイントを、確認なしで消す
- `definitions.md` の内容を `discussion-archive.md` へ移す
