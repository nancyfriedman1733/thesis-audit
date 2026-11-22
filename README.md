# Thesis Audit

![skill](https://img.shields.io/badge/skill-thesis__audit-blue)
![method](https://img.shields.io/badge/method-two--layer%20audit-green)
![languages](https://img.shields.io/badge/languages-EN%20%7C%20%E4%B8%AD%E6%96%87%20%7C%20%E6%97%A5%E6%9C%AC%E8%AA%9E-orange)
![inputs](https://img.shields.io/badge/inputs-PDF%20%7C%20LaTeX%20%7C%20Word-lightgrey)
![license](https://img.shields.io/badge/License-MIT-yellow.svg)

**Language:** [English](#en) · [中文](#zh) · [日本語](#ja)

---

<a id="en"></a>
## English

Audit an academic paper the way a strict examiner would, then keep auditing it until the findings stop changing.

This skill was distilled from a real audit, not written from theory. It was built while reviewing a law bachelor's thesis, where it found **136 issues** across one first pass, one full second pass, and 25 half-hour follow-up rounds. The same two-layer pattern was later used on a computer-science conference submission (EICA AI-CS 2026, **182 issues**), which is what motivated the format-aware intake: PDF, LaTeX, and Word are all handled, not just PDF.

### Results so far

| Paper | Issues found | Follow-up rounds |
| --- | --- | --- |
| Law bachelor's thesis (Personal Information Protection Law) | 136 | 25 |
| EICA AI-CS 2026 conference paper (Human-AI resume screening) | 182 | 29 |

### How it works

**Two layers, no more by default.**

1. **First pass — find problems.** Read the whole paper against its requirements document and template. Number every issue in one continuous sequence, each with its location, the evidence, and a concrete fix. Keep going until the target is reached (default: 100). Never pad the list to hit the number. When the severity tier is unclear, choose the higher tier and say why.
2. **Second pass — verify everything.** Re-check every first-pass item against a primary source: statutes against the official text, citations against the publisher or index record, cases against the court or regulator publication, numbers recomputed from their parts. Open every source you cite — a search snippet is not a source. Each item gets exactly one verdict: confirmed, discrepancy, unverifiable, or serious error.

**Short follow-up rounds are optional**, only for a paper that is still being revised or where the stakes justify another look (a defense, a submission). Each round takes one rotating angle — statutes, citations, cases, numbers, language, logic, dates, structure — and **stops at the first round that finds nothing**. No timers by default. If a new version arrives mid-review, only the changed passages and their dependents are re-checked.

**Authenticity is graded, never a certainty.** "Not found" is not "fabricated." "Highly suspected AI assistance" is not "pure AI generation." The skill weighs forensic signals (generated metadata, small-hours creation time, footnotes that do not match the bibliography, zero figures) against counter-evidence (precise distinctions the author demonstrably made), and names the extra proof that would settle the question — a similarity report, earlier drafts, supervision records.

### What it checks

- Requirements and template compliance, scoring rubric band by band
- Every number, date, case, quotation, and citation against its primary source
- Statistics recomputed from the reported parts (kept as a rerunnable script)
- Citation direction and attribution — including references whose titles, identifiers, or claims do not match the source
- Legal and regulatory sources, with jurisdiction and effective dates checked
- Discipline-matched checks: statutes and cases for law, repository and publisher records plus model, prompts, and data for computing, data, code, and units for science
- Authenticity signals, kept strictly separate from verdicts

### Quick start

This is a [Muse](https://muse.ai) skill. To use it:

1. Copy this folder into your custom skills directory, e.g. `~/workspace/custom-skills/thesis_audit/`.
2. Send Muse your paper file and its requirements document or template, and say: `按 thesis_audit 核查这篇论文` (or: `Audit this paper with thesis_audit`).
3. Tell Muse the issue target if you have one; otherwise it defaults to 100. Tell Muse whether the paper is a draft or a final version.

Muse will deliver a first-pass report, a second-pass verification report, and — if you ask for one — a closing summary PDF.

### Who is this for

- Students and researchers preparing a thesis, dissertation, or journal submission
- Anyone who wants a second, adversarial read before a defense or a deadline
- Supervisors who want a checklist of what to verify before signing off

### Repo layout

```
thesis-audit/
├── SKILL.md      # The skill, bilingual: English first, then 中文
├── skill.yaml    # Skill metadata (name, title, description)
├── README.md     # This file: English, 中文， 日本語 in one file
└── LICENSE       # MIT License
```

### Changelog

- 2026-11-23: README is now a single trilingual file (English, 中文， 日本語）.

#### v1.2 — 2026-11-23

- **Cite only sources you opened.** A search snippet is not a source, and a summary page is not the primary source.
- **Unclear severity goes up, with reasons.** When the tier is unclear, choose the higher tier and say why.
- **Disputed findings go to the correction ledger.** If the user disputes a finding, re-check it against the primary source and record the outcome, either retracting it or keeping it with the source quoted.
- **Connectors, specified.** The core method needs only the browser; Google Docs and Drive are named as intake sources when the paper lives there.

#### v1.1 — 2026-11-23

- **Format-aware intake.** PDF, LaTeX, and Word are now handled explicitly. LaTeX is read as source, and page counts are audited statically when no local compiler is available.
- **Re-baseline on revision.** If a new version arrives mid-review, only the changed passages and their dependents are re-checked, and the re-baseline is logged.
- **Discipline-matched checks.** The two layers stay the same; the sources change with the discipline.
- **Recomputation scripts are kept** with the round logs so later rounds rerun them instead of redoing the arithmetic.

#### v1.0 — 2026-11-22

- Initial bilingual release. Two layers (first pass + full second pass), optional follow-up rounds that stop at the first empty round, closing-summary PDF workflow, correction ledger, and bookkeeping rules.
- Validated end to end on the originating law thesis audit.

### License

MIT License — see [LICENSE](LICENSE).

---

<a id="zh"></a>
## 中文

像严格的考官一样审一篇学术论文，然后一直审到找不出新东西为止。

这个 skill 不是凭理论写出来的，是从一次真实核查里提炼出来的。做法学本科毕业论文核查时，它一轮首轮、一轮完整第二轮、25 轮半小时复查，一共找到 **136 条问题**。同一套两层方法后来又用在一篇计算机会议投稿（EICA AI-CS 2026，**182 条问题**）上，也正是这次经历让人补上了按文件类型分流收稿：PDF、LaTeX、Word 都能处理，不只是 PDF。

### 已有战绩

| 论文 | 找到的问题 | 后续轮次 |
| --- | --- | --- |
| 法学本科毕业论文（个人信息保护法） | 136 条 | 25 轮 |
| EICA AI-CS 2026 会议论文（人机协作简历筛选） | 182 条 | 29 轮 |

### 方法

**默认只有两层，不多。**

1. **首轮——找问题。** 对照要求文档和模板通读全文，找到的问题按一个连续序号编号，每条写明位置、证据和作者能照着改的具体改法。一直找到目标数为止（默认 100 条），绝不拿弱问题凑数。严重级别拿不准就定高一级并写明理由。
2. **第二轮——逐条验证。** 首轮每一条都回一手来源复核：法条对官方公布文本，引文对出版方或索引记录，案例对法院或监管机构的发布，数字从组成部分重算。结论里引的每个来源都要亲自打开看过，搜索结果的摘要不是来源。每条只给一个结论：属实、有出入、无法验证、严重错误。

**短的后续轮查是可选的**，只在论文还在改或利害足够大时才用，比如答辩或投稿。每轮只定一个角度——法条、引文、案例、数字、语言、逻辑、日期、结构——**第一轮没有新发现就停**。默认不排定时任务。复查中收到新版本，只复核改动过的段落和依赖这些段落的内容。

**真实性只给分级结论，绝不给定论。** 查不到不是编造。高度疑似 AI 辅助不是纯 AI 生成。skill 会把取证信号（程序生成的元数据、凌晨的创建时间、脚注和参考文献对不上、零图表）和反证（作者确实做出的精确区分）一起称，并写明补什么证能把问题定下来，比如查重报告、旧稿和指导记录。

### 检查什么

- 对照要求文档和模板，按评分标准逐档检查
- 每个数字、日期、案例、引言和引文，逐个对一手来源核验
- 统计数从报告的组成部分重算，重算脚本留下来可重跑
- 引文方向和归属，包括标题、编号或主张与来源对不上的引用
- 法律和监管来源，核查管辖和生效日期
- 检查项跟着学科走：法学查法条案例，计算机查代码库和出版方记录并要模型、提示词和数据，理科查数据、代码和单位
- 真实性信号和结论严格分开

### 快速上手

这是 [Muse](https://muse.ai) 的 skill，这样用：

1. 把这个文件夹复制到你的 custom skills 目录，比如 `~/workspace/custom-skills/thesis_audit/`。
2. 把论文文件和要求文档或模板发给 Muse，说：`按 thesis_audit 核查这篇论文`。
3. 有目标条数就告诉 Muse，没有就默认 100 条。再告诉 Muse 这是草稿还是终稿。

Muse 会交出首轮报告、第二轮复核报告，需要的话还会交一份结项总结 PDF。

### 适合谁

- 准备毕业论文、学位论文或期刊投稿的学生和研究者
- 答辩或截稿前想再找一个人狠狠挑一遍毛病的人
- 签字前想逐项核对的导师

### 仓库结构

```
thesis-audit/
├── SKILL.md      # skill 正文，双语：英文在前，中文在后
├── skill.yaml    # skill 元数据（名称、标题、描述）
├── README.md     # 本文件：英文、中文、日文合一
└── LICENSE       # MIT License
```

### 更新日志

- 2026-11-23：README 改成英文、中文、日文合一的单个文件。

#### v1.2 — 2026-11-23

- **只引用亲自打开过的来源。** 搜索结果的摘要不是来源，转述页也不是一手来源。
- **级别拿不准就定高一级，并写明理由。**
- **有异议的结论进修正账。** 用户对某条结论有异议就对着一手来源再核一遍，结果记进修正账，要么撤回，要么留下来并把来源引文附上。
- **连接器写具体了。** 核心方法只需要浏览器；论文在 Google Docs 或 Drive 里时，先用对应的连接器取回来。

#### v1.1 — 2026-11-23

- **按文件类型分流收稿。** PDF、LaTeX、Word 分开处理。LaTeX 直接读源码，本地没有编译器就改做静态审计。
- **收到新版本重新定基线。** 只复核改动过的段落和依赖这些段落的内容，重新定基线写进日志。
- **检查项跟着学科走。** 两层方法不变，变的是来源。
- **重算脚本留下来。** 和轮次日志放在一起，后面的轮次直接重跑。

#### v1.0 — 2026-11-22

- 首个双语版。两层（首轮＋完整第二轮），后续轮查可选、第一轮空轮即停，结项总结 PDF 流程，修正账和记账规则。
- 在法学论文核查上端到端验证通过。

### License

MIT License，见 [LICENSE](LICENSE)。

---

<a id="ja"></a>
## 日本語

厳格な試験官のように学術論文を査読し、指摘がなくなるまで査読を続けるためのスキルです。

このスキルは理論から書かれたものではなく、実際の査読から生まれました。法学の学士論文の査読では、1回目の全数査読、2回目の全数再検証、25回の30分ごとのフォローアップ査読で、合計 **136件の問題** を発見しました。同じ二層の方法はその後、計算機科学の国際会議投稿（EICA AI-CS 2026、**182件の問題**）にも使われました。この経験から、PDF、LaTeX、Word を区別して受け取る仕組みが加わりました。PDF だけではありません。

### 実績

| 論文 | 発見した問題 | フォローアップ査読 |
| --- | --- | --- |
| 法学学士論文（個人情報保護法） | 136件 | 25回 |
| EICA AI-CS 2026 会議論文（人間とAIによる履歴書スクリーニング） | 182件 | 29回 |

### 方法

**基本は二層だけです。**

1. **1回目——問題を見つける。** 要求文書とテンプレートに照らして全文を読み、見つけた問題に通し番号を付けます。各問題には論文内の位置、証拠、著者がそのまま実行できる修正方法を書きます。目標件数（既定値は100件）に達するまで続け、件数を稼ぐために弱い問題を並べることはしません。重要度の判断に迷った場合は一段階上げ、その理由を書きます。
2. **2回目——すべてを検証する。** 1回目の各項目を一次資料に当たって再確認します。法令は官報の原文、引用は出版社または索引の記録、判例は裁判所または規制機関の公表、数値は内訳から再計算します。結論で引用する資料はすべて自分で開いて確認すること。検索結果の抜粋は資料ではありません。各項目には「確認済み」「食い違い」「検証不能」「重大な誤り」のいずれか一つだけを付けます。

**短いフォローアップ査読は任意です。** 論文がまだ改訂中の場合、あるいは答弁や投稿のように利害が大きい場合にのみ行います。各回は法令、引用、判例、数値、言語、論理、日付、構成のうち一つの角度だけを取り上げ、**新しい発見がなかった回が出た時点で止めます**。既定ではタイマーは使いません。査読中に新版が届いた場合は、変更された箇所とそれに依存する内容だけを再確認します。

**真正性の判断は段階評価であり、断定ではありません。** 「見つからない」は「捏造」ではありません。「AIによる補助の疑いが強い」は「純粋なAI生成」ではありません。スキルは物的証拠（プログラムが生成したメタデータ、深夜の作成時刻、脚注と参考文献の不一致、図表ゼロ）と反証（著者が実際に行った精密な区別）を秤にかけ、問題を確定させるために必要な証拠——類似度レポート、旧稿、指導記録——を明示します。

### 査読する内容

- 要求文書とテンプレートへの適合、評価基準の各段階に沿った確認
- すべての数値、日付、判例、引用、文献を一次資料と照合
- 統計値は報告された内訳から再計算し、再計算スクリプトを残して再実行可能にする
- 引用の方向と帰属。題名、識別子、主張が資料と一致しない引用を含む
- 法令・規制資料。管轄と施行日を確認する
- 学問分野に合わせた確認項目。法学では法令と判例、計算機科学ではリポジトリと出版社の記録に加えてモデル、プロンプト、データ、理系ではデータ、コード、単位
- 真正性のシグナルと結論は厳密に分ける

### クイックスタート

これは [Muse](https://muse.ai) のスキルです。使い方は次のとおりです。

1. このフォルダをカスタムスキルのディレクトリにコピーします。例：`~/workspace/custom-skills/thesis_audit/`。
2. 論文ファイルと要求文書またはテンプレートを Muse に送り、`按 thesis_audit 核查这篇论文`（または `Audit this paper with thesis_audit`）と伝えます。
3. 目標件数があれば伝え、なければ既定値の100件になります。草稿か最終稿かも伝えてください。

Muse は1回目の査読レポート、2回目の検証レポートを出し、希望があれば最終サマリーのPDFも出します。

### 対象

- 卒業論文、学位論文、学術誌投稿を準備している学生・研究者
- 答弁や締切の前に、もう一度厳しく見直してほしい人
- 署名する前に項目ごとに確認したい指導教員

### リポジトリ構成

```
thesis-audit/
├── SKILL.md      # スキル本文。バイリンガル：英語が先、中国語が後
├── skill.yaml    # スキルのメタデータ（名前、タイトル、説明）
├── README.md     # このファイル：英語、中国語、日本語を1ファイルに統合
└── LICENSE       # MIT License
```

### 変更履歴

- 2026-11-23：README を英語、中国語、日本語の単一ファイルに統合しました。

#### v1.2 — 2026-11-23

- **自分で開いた資料だけを引用する。** 検索結果の抜粋は資料ではなく、要約ページも一次資料ではありません。
- **重要度に迷ったら一段階上げる。その理由も書く。**
- **異議のある結論は修正台帳へ。** 利用者が結論に異議を唱えた場合は一次資料に当たって再確認し、結果を修正台帳に記録します。撤回するか、資料の引用を添えて残すかです。
- **コネクタを具体化。** 中核の方法に必要なのはブラウザだけです。論文が Google Docs や Drive にある場合は、対応するコネクタで先に取得します。

#### v1.1 — 2026-11-23

- **ファイル種別に応じた受付。** PDF、LaTeX、Word を区別して扱います。LaTeX はソースを直接読み、ローカルにコンパイラがない場合は静的に監査します。
- **改訂版が届いたらベースラインを取り直す。** 変更箇所とそれに依存する内容だけを再確認し、取り直しをログに記録します。
- **分野に合わせた確認項目。** 二層の方法は変わらず、資料だけが変わります。
- **再計算スクリプトを残す。** 査読ログと一緒に置き、後の査読では手計算ではなくスクリプトを再実行します。

#### v1.0 — 2026-11-22

- 初のバイリンガル版。二層（1回目＋2回目の全数検証）、フォローアップ査読は任意で、空振りの回が出たら停止。最終サマリーPDFの手順、修正台帳、記帳ルールを含みます。
- 法学論文の査読でエンドツーエンドの検証を完了しました。

### ライセンス

MIT License — [LICENSE](LICENSE) を参照してください。
