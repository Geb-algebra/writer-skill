# Mode And Artifacts

## Mode の選び方

このスキルには 2 つの mode がある。

- `discussion mode`: ユーザーと AI が 1on1 で議論する
- `delegate mode`: メイン AI とサブエージェントが自動的に議論する

mode 指定がない場合は、`discussion mode` を使う。  
`delegate mode` は、ユーザーが自動的な内部議論やサブエージェント委譲を求めたときに使う。

## `discussion mode`

ユーザーと AI の 1on1 で進める mode。  
以下のときに使う。

- ユーザー自身と往復しながら考えを深めたい
- 論点の承認主体をユーザーに置きたい
- 対話そのものが成果物の一部である

## `delegate mode`

メイン AI とサブエージェントで自動的に議論を回す mode。  
`discussion mode` の「ユーザー応答」「ユーザー承認」を、サブエージェントの応答と承認に置き換えた形で進める。

以下のときに使う。

- ユーザーとの往復なしで内部的に深掘りしたい
- 論点を自動的に掘り続けたい
- `discussion.md` と `draft.md` を自律的に前進させたい

## 記録ファイル

このスキルでは、必要に応じて 3 つのファイルを扱う。

- `draft.md`: `pyramid-principle` によって構造化された現行ピラミッド
- `discussion.md`: 対話の進行、未定義単語、未解決論点を保持する作業メモ
- `discussion-archive.md`: `discussion.md` から退避した反映済み要素と過去ログの保管場所

`discussion.md` は常に自動更新してよい。  
一方で `draft.md` に書いてよい内容は active mode によって変わる。

- `discussion mode`: ユーザーが承認した事項だけ
- `delegate mode`: サブエージェントが収束と判断し、反映を承認した事項だけ

## 共通原則

### 1. 応答の直後に `draft.md` へ即反映しない

相手が答えたら、その内容をすぐ `draft.md` に書いてはいけない。  
まず `deep-thinker` に従って、その回答の意味を確認し、必要なら聞き返し、その後で AI の考えを述べる。

### 2. 未解決の論点を忘れない

AI は、思いついた深掘りポイントを会話の流れの中で消してはいけない。  
今すぐ掘らない論点も、backlog として保持し続ける。

### 3. 範囲指定があるときは、その範囲だけ `draft.md` を書く

ユーザーが「ここからここまでだけ記録」のように範囲を指定した場合、その範囲外の `draft.md` を書き換えてはいけない。

### 4. 結論も構造も変えてよい

議論の途中で結論や構造が変わってよい。重要なのは、各時点の `draft.md` が Barbara Minto の原則を満たしていることである。

### 5. context 圧迫を防ぐため、反映済み要素は定期的に archive してよい

`discussion.md` が肥大して context を圧迫するなら、反映済み要素と議論ログを `discussion-archive.md` へ移してよい。  
ただし、未反映要素は `discussion.md` に残し、未解決論点の探索を失ってはいけない。
