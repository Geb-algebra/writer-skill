# Discussion Log

## `discussion.md` の構成

`discussion.md` は、常時更新される作業メモとして少なくとも以下の 4 節を持つ。

## 1. Definitions

単語の辞書。各項目は以下を持つ。

- `ID`
- `Term`
- `Current Definition`
- `Status`: `open` / `proposed` / `confirmed` / `deferred`
- `Source`
- `Reflected to Draft`: `yes` / `no`

## 2. Question Backlog

深掘りポイントをすべて貯める場所。各項目は以下を持つ。

- `ID`
- `Operation`: その問いを生んだ `deep-thinker` の思考操作名。なければ `none`
- `Target`
- `Question`
- `Why This Matters`
- `Priority`
- `Status`: `open` / `active` / `answered` / `reflected` / `parked` / `dropped`

`parked` は「重要だが今は掘らない」、`dropped` は「不要と判断した」を意味する。

## 3. Active Questions

現時点で、次に掘る候補として残しておく問い。

## 4. Answered / Reflected Log

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

- `Definitions` のうち `Reflected to Draft: yes` の項目
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

- `Definitions` のうち `Reflected to Draft: no` の項目
- `Question Backlog` のうち未反映の項目
- 今後も掘る必要がある `Active Questions`
- 空にした `Answered / Reflected Log` 見出し

### Step 5. ログ節は空に戻す

`Answered / Reflected Log` は archive 後に空に戻す。  
ただし節そのものは消さず、次の議論を記録できる空の状態で残す。

### Step 6. `draft.md` は勝手に書き換えない

archive 操作は、`discussion.md` の圧縮が目的である。  
別途反映指示がない限り、この操作だけで `draft.md` を新たに書き換えてはいけない。

## してはいけないこと

- archive 時に、未反映要素まで `discussion.md` から消す
- archive 時に、議論ログを捨てて `discussion-archive.md` へ移さない
- 過去に出た深掘りポイントを、確認なしで消す
