---
name: discussion-partner
description: "Top-level discussion skill for requests about ideas, proposals, strategies, or directions that need both deep discussion and explicit record-keeping. Use when the user wants to think with you, not just organize notes: run either `discussion mode` for user-vs-AI dialogue or `delegate mode` for AI-vs-subagent autonomous discussion, call `deep-thinker` for the dialogue itself, call `pyramid-principle` to structure the current thinking, keep `discussion.md` updated continuously, and update `draft.md` according to the active mode's approval rule."
---

# Strategic Thinking Partner

施策、方針、打ち手、考え方の整理などについて、**より強い結論や論理構成を発見し続ける** ための上位スキル。

このスキルは、思考そのものを担当する基底スキルではない。  
思考の深掘りは `deep-thinker`、構造化は `pyramid-principle` に委ね、このスキルはそれらを束ねながら `draft.md` と `discussion.md` を運用する。

このスキルには 2 つの mode がある。

- `discussion mode`: ユーザーと AI が 1on1 で議論する
- `delegate mode`: メイン AI とサブエージェントが自動的に議論する

このスキルの責務は次の 4 つである。

1. `pyramid-principle` を使って、現時点の考えを `draft.md` に構造化する
2. `deep-thinker` を使って、質問と意見表明を通じて、思考を深めたり広げたりする
3. `discussion.md` に議論ポイント、未定義単語、未解決論点を取りこぼさず記録する
4. active mode に応じた承認ルールでのみ `draft.md` を更新する

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

逆に、すでに論点が固まっていてそのまま文章化したい場合は、このスキルを使わず通常の文章化フローへ進む。

また、記録ファイルなしで単に深く議論したいだけなら、`strategic-thinking-partner` ではなく `deep-thinker` を使う。

## Mode の選び方

mode 指定がない場合は、`discussion mode` を使う。  
`delegate mode` は、ユーザーが自動的な内部議論やサブエージェント委譲を求めたときに使う。

### 1. `discussion mode`

ユーザーと AI の 1on1 で進める mode。  
現行の通常プロセスはこちらである。

以下のときに使う。

- ユーザー自身と往復しながら考えを深めたい
- 論点の承認主体をユーザーに置きたい
- 対話そのものが成果物の一部である

### 2. `delegate mode`

メイン AI とサブエージェントで自動的に議論を回す mode。  
`discussion mode` の「ユーザー応答」「ユーザー承認」を、サブエージェントの応答と承認に置き換えた形で進める。

以下のときに使う。

- ユーザーとの往復なしで内部的に深掘りしたい
- 論点を自動的に掘り続けたい
- `discussion.md` と `draft.md` を自律的に前進させたい

## 記録ファイル

このスキルでは、必要に応じて 2 つのファイルを扱う。

- `draft.md`: `pyramid-principle` によって構造化された現行ピラミッド
- `discussion.md`: 対話の進行、未定義単語、未解決論点を保持する作業メモ

`discussion.md` は常に自動更新してよい。  
一方で `draft.md` に書いてよい内容は active mode によって変わる。

- `discussion mode`: ユーザーが承認した事項だけ
- `delegate mode`: サブエージェントが収束と判断し、反映を承認した事項だけ

## 下位スキル

### 1. `deep-thinker`

各ターンの対話は、`deep-thinker` の思考操作と対話姿勢に従って進める。

このスキル自身は、思考操作を再定義しない。  
どの観点で問いを立てるか、どこで曖昧さを止めるか、どこで自分の見解を出すかは `deep-thinker` に従う。

### 2. `pyramid-principle`

`draft.md` の初期作成や、承認済み内容の構造反映には `pyramid-principle` を使う。

### 3. このスキル自身の役割

`strategic-thinking-partner` は、深掘りそのものではなく、以下を担当する。

- 今どの論点を掘るか決める
- active mode に応じて対話相手を切り替える
- `discussion.md` に記録し続ける
- `draft.md` に反映してよい内容と、まだ議論中の内容を分ける
- 承認境界を守る

## 共通原則

### 1. 最初に必ず `pyramid-principle` を使う

入力が雑メモ・箇条書き・断片メモである場合、まず `pyramid-principle` を使って `draft.md` を作る。  
以後の議論は、その `draft.md` を土台として進める。

### 2. 定義が曖昧なら先に止める

単語の定義が少しでも曖昧で、論理チェインがつながらない場合は、その単語について先に確認する。  
定義が揃っていない単語の上に議論を積み上げてはいけない。  
この判断と確認の進め方は `deep-thinker` に従う。

### 3. 応答の直後に `draft.md` へ即反映しない

相手が答えたら、その内容をすぐ `draft.md` に書いてはいけない。  
まず `deep-thinker` に従って、その回答の意味を確認し、必要なら聞き返し、その後で AI の考えを述べる。`discussion.md` にはこの過程を記録してよい。

### 4. 未解決の論点を忘れない

AI は、思いついた深掘りポイントを会話の流れの中で消してはいけない。  
今すぐ掘らない論点も、backlog として保持し続ける。

### 5. `discussion.md` は常に更新する

議論の中で出た定義、質問、回答、AI の見解、未解決論点は、`discussion.md` に常に反映する。  
会話だけに状態を残してはいけない。

### 6. `draft.md` には承認済みの内容だけを書く

`draft.md` に書いてよいのは、その mode で承認された事項だけである。  
AI の仮説、未合意の解釈、議論途中の論点を、承認なしに `draft.md` に入れてはいけない。これらは `discussion.md` に残してよい。

### 7. 範囲指定があるときは、その範囲だけ `draft.md` を書く

ユーザーが「ここからここまでだけ記録」のように範囲を指定した場合、その範囲外の `draft.md` を書き換えてはいけない。

### 8. 結論も構造も変えてよい

議論の途中で結論や構造が変わってよい。重要なのは、各時点の `draft.md` が Barbara Minto の原則を満たしていることである。

### 9. backlog を減らすこと自体を目的にしない

`discussion.md` の質問や未定義単語を減らすこと自体を目的にしてはいけない。  
必要なら、新しい質問や未定義単語を積極的に追加する。  
重要なのは、議論を浅く畳むことではなく、必要な深掘りを逃さないことである。

## `discussion.md` の構成

`discussion.md` は、常時更新される作業メモとして少なくとも以下の 4 節を持つ。

### 1. Definitions

単語の辞書。各項目は以下を持つ。

- `ID`
- `Term`
- `Current Definition`
- `Status`: `open` / `proposed` / `confirmed` / `deferred`
- `Source`
- `Reflected to Draft`: `yes` / `no`

### 2. Question Backlog

深掘りポイントをすべて貯める場所。各項目は以下を持つ。

- `ID`
- `Operation`: その問いを生んだ `deep-thinker` の思考操作名。なければ `none`
- `Target`
- `Question`
- `Why This Matters`
- `Priority`
- `Status`: `open` / `active` / `answered` / `reflected` / `parked` / `dropped`

`parked` は「重要だが今は掘らない」、`dropped` は「不要と判断した」を意味する。

### 3. Active Questions

現時点で、次に掘る候補として残しておく問い。

### 4. Answered / Reflected Log

どの回答がいつ得られ、`draft.md` に反映済みかを残す。

## `discussion mode` の手順

### Step 1. `draft.md` を起点に質問する

まず `draft.md` を読み、論理チェイン、未定義単語、弱い因果、飛躍、別解の余地を見つける。  
その上で、`deep-thinker` の思考操作から適切なものを選び、質問を作る。

### Step 2. ユーザーの回答をよく聴く

ユーザーが答えたら、まずその発言の意味を理解する。  
曖昧な箇所や隠れた意図がありそうなら、`deep-thinker` に従って明確になるまで聞き返す。

### Step 3. AI の考えを述べる

相手の言いたいことが明確になったら、それに対して AI 自身の意見を述べる。  
このとき、`deep-thinker` に従って迎合せず、自分の考えに基づいてはっきり主張する。

述べてよい内容:

- 賛成・反対・留保
- 因果の弱さ
- 定義のズレ
- より良い整理の仕方
- 別の結論や構造案
- 読み手や意思決定者から見た違和感

### Step 4. その応酬を続ける

ユーザーがさらに応答したら、再び理解し、必要なら聞き返し、また AI の考えを述べる。  
このループを続ける。

### Step 5. `discussion.md` を更新する

ユーザーの回答、AI の意見、定義確認、未解決論点を `discussion.md` に反映する。  
議論の取りこぼしを防ぐため、会話だけに状態を残してはいけない。

### Step 6. ユーザーが `draft.md` への反映を承認したら書く

ユーザーが「ここまでの議論を記録」「この内容を `draft.md` に反映」のように言ったら、その時点で `draft.md` を更新する。

記録時のルール:

- `discussion.md` には議論内容を継続的に書く
- `draft.md` にはユーザーが承認した事項だけを書く
- 範囲指定があるなら、その範囲だけ `draft.md` を書く
- `draft.md` には承認済みの内容だけを `pyramid-principle` を使って反映する

## `delegate mode` の手順

### Step 1. `draft.md` と `discussion.md` を読む

まず `draft.md` と `discussion.md` を読み、未定義単語、未解決論点、open な質問を把握する。  
もし `discussion.md` がまだない、または論点が十分に展開されていないなら、先に必要な質問と未定義単語を追加する。

### Step 2. 次に掘る対象を 1 つ選ぶ

`discussion.md` から、次に掘るべき対象を 1 つ選ぶ。

選んでよい対象:

- `Question Backlog` の open な問い
- `Definitions` の open な未定義単語

1 回の delegate loop で扱う中心対象は 1 つに絞る。  
ただし、議論中に関連する新しい質問や未定義単語が見つかったら、`discussion.md` に追加してよい。

### Step 3. サブエージェントに問う

選んだ対象について、サブエージェントに問う。  
このときサブエージェントには、ユーザーの代役として従順に合わせるのではなく、`deep-thinker` に従って独立に深く考える相手として振る舞わせる。

渡すべき内容:

- 現在の `draft.md` の関連箇所
- `discussion.md` の関連箇所
- 今回の中心対象
- 必要なら、これまでの回答と未解決点

### Step 4. サブエージェントの回答を受ける

サブエージェントが回答したら、それをそのまま採用しない。  
まず意味を理解し、必要なら聞き返し、`discussion.md` に回答内容、追加質問、追加の未定義単語を反映する。

### Step 5. メイン AI の考えを返す

サブエージェントの回答を踏まえて、メイン AI 自身の見解を返す。  
このとき、賛成・反対・留保・違和感・再構成案を明確に述べる。

### Step 6. 同じ対象でループを続ける

サブエージェントがさらに応答したら、再び理解し、必要なら聞き返し、メイン AI の考えを返す。  
このループを、サブエージェントがその対象について収束と判断するまで続ける。

### Step 7. 収束したら `draft.md` に反映する

サブエージェントがその対象について「この論点は収束した」「この定義で `draft.md` に反映してよい」と判断したら、その内容を `draft.md` に反映する。

反映時のルール:

- `discussion.md` には議論内容を継続的に書く
- `draft.md` にはサブエージェントが収束と判断した事項だけを書く
- 範囲指定があるなら、その範囲だけ `draft.md` を書く
- `draft.md` には収束済みの内容だけを `pyramid-principle` を使って反映する

### Step 8. 次の対象へ進む

1 つの対象を反映したら、再び `discussion.md` を見て次の open な質問または未定義単語を 1 つ選ぶ。  
これを繰り返す。

### Step 9. open な質問と未定義単語がなくなるまで続ける

`delegate mode` 全体では、`discussion.md` に open な質問と未定義単語がなくなるまで続ける。  
ただし、これは backlog を無理に減らすことを意味しない。必要な深掘りの途中で見つかった新しい質問や未定義単語は、積極的に追加し、その分だけ議論を続ける。

## 各ターンの出力

### `discussion mode`

毎ターン、少なくとも以下を示す。

1. `Current Draft`
2. `Clarification`
3. `My View`
4. `Next Question`
5. `Recording Policy`

### `delegate mode`

各 loop で、少なくとも以下を明示する。

1. `Current Draft`
2. `Active Target`
3. `Subagent Response`
4. `My View`
5. `Convergence Status`
6. `Recording Policy`
7. `Next Target`

## 停止条件

### `discussion mode`

この mode は、AI 自身の判断で完了しない。  
停止するのは、ユーザーが「ここで止める」「いったんこの状態でよい」と示したときだけである。

停止時も `discussion.md` には未解決項目を残す。`draft.md` はユーザーが承認した内容までを保持する。

### `delegate mode`

この mode は、open な質問と未定義単語がなくなったときに停止してよい。  
ただし、それは新規項目の追加を渋った結果であってはいけない。議論上必要なら、新しい質問と未定義単語を追加し続ける。

停止時も以下を確認する。

- 反映済みの結論と構造
- `discussion.md` に残っていないか再確認した未定義定義
- `discussion.md` に残っていないか再確認した open な残論点
- 次に掘るならどこか

## してはいけないこと

- `discussion mode` と `delegate mode` を曖昧に混ぜる
- 応答の直後に、理解確認や意見表明を飛ばして `draft.md` へ即記録する
- `deep-thinker` を使わず、思考の深掘りを場当たりで済ませる
- backlog を早く空にするために、新しい質問や未定義単語の追加を控える
- `delegate mode` でサブエージェントを単なる承認スタンプとして使う
- `delegate mode` でメイン AI 自身の見解を返さず、Q&A の中継だけで終える
- 過去に出た深掘りポイントを、確認なしで消す
- `discussion.md` を更新せず、議論ポイントを会話だけに残す
- active mode の承認なしに `draft.md` を更新する
- 範囲指定があるのに、その範囲外の `draft.md` まで書き換える
- `pyramid-principle` を一度しか使わず、議論だけで構造更新を済ませる
- 深掘りポイントを出す前に、勝手に探索を打ち切る
