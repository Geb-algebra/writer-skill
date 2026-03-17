# Pyramid Structure

雑多な箇条書き（Brain Dump）を階層構造で整理する方法。

 **Barbara Minto の Pyramid Principle** に従う。

## Pyramid Principle とは

**導入を先頭**に置いた後、**メインメッセージ → 理由 → 根拠** のツリー構造で情報を整理する。

- 導入は SCQA（Situation, Complication, Question, Answer）で構成する。 Answerがメインメッセージ。
- その後、Answerを支える主張をツリー構造の箇条書きで構成する。
- ツリーの親ノードは子ノードの要約
- 同階層の要素は同種の主張に揃える
- 1つの親に対する子ノードは3–4個程度で、**MECE** に親ノードを支える。
- ツリーの各分岐の深さや幅はなるべく均一にする。

思い出しフック: **SCQA** / **Deduction / Induction** / **3–4 grouping**

## 出力形式

整理結果はIntroductionおよびContentの2節に配置。 加えて、整理がうまくできない箇所を洗い出してIssuesに記載する。

Introductionは SCQA を一つずつ並べた4アイテムの箇条書きで構成。 各箇条書きの中に、そのアイテムを補足する追加情報を入れることができる。

Contentに、Answerを主張としたツリー構造の箇条書きを配置。

Issuesに、ツリー構造への整理がうまくできない箇所を列挙。 以下のような課題がありうる。

- XXXに関する理由・根拠がなく、主張をMECEに支えられない。
- 主張を支えるのに不必要な情報がある。
- 特定の分岐に対して材料が少なく、ツリーの深さや幅が他と大きく異なる。

```
## Introduction

- {Situation}
    - {Additional Information}
- {Complication}
    - {Additional Information}
- {Question}
    - {Additional Information}
- {Answer}
    - {Additional Information}

## Content

- {Answer}
    - {Reason A}
        - Fact A1
        - Fact A2
    - Reason B
        - Fact B1
        - Fact B2

## Issues

- {Issue 1}
- {Issue 2}
```

## 制約

禁止: 情報の追加・補完・推測・意味の拡張

許可: 並び替え・グルーピング・階層化・上位ノード作成のための最小限の要約
