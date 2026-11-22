# Thesis and Paper Audit

Audit an academic paper the way a strict examiner would, then keep auditing it until the findings stop changing. The method has two layers. The first pass finds problems. The second pass verifies every finding against a primary source. Short follow-up rounds are optional, only for a paper that is still being revised or where the stakes justify another look. The law thesis audit that shaped this skill ran one first pass, one full second pass, and twenty-five half-hour rounds. The rounds found 36 more issues, then found nothing for the last five rounds, so rounds are no longer part of the default method.

## Take in the paper and set the baseline

- Ask the user for the paper file and the requirements or template document that governs it, and read both before judging anything.

- Extract the paper text with `pdftotext` and keep the extracted text as the working copy for searches and counts.

- Count words under every plausible rule and record each result, such as body text alone, body plus abstract, and text including punctuation, so a limit dispute can be settled by pointing at one row.

- Record the file hash with `md5sum` and the modification time, and check both again at the start of every later round.

- Inspect the PDF metadata with `pdfinfo` and record the author, creator, and creation time as forensic evidence, not as a verdict on its own.

- Ask the user whether the paper is a draft or a final version, and record the answer, because several judgements change with it, such as unsigned declarations and missing supervision records.

- Record the submission deadline, and say once if it has already passed, then set the point aside unless the user asks to act on it.

- Ask the user for the issue target, and use 100 when the user gives no number.

## Run the first pass

- Read the whole paper against the requirements document and the template, and number every issue you find in one continuous sequence.

- Check the paper against the scoring rubric band by band, since a missing element can cost a whole grade band, such as originality or a literature review.

- Keep searching until the target is reached, and say so plainly if the paper runs out of real issues before the target.

- Never pad the list with weak or trivial items to reach the target, and never repeat an issue under a new number.

- Give each issue one of three severity tiers. A blocker stops submission or fails the paper. A major issue affects the grade or the defense. A minor issue affects polish and the reader impression.

- Write every issue in the same shape, with its location in the paper, the evidence for it, and a concrete fix the author can apply.

- Deliver the list as a report file in the goal files folder, and keep the count visible in the file name or heading.

## Run the second pass

- Re-verify every first pass item against a primary source, and treat this pass as verification rather than a hunt for new issues.

- Search with `browser.search` and read the source with `browser.open`, and prefer the primary source over a summary or a repost.

- Check statutes against the official published text, citations against the publisher or index record, cases against the court or regulator publication, and standards against the standards body record.

- Give each item exactly one verdict. Confirmed means the primary source agrees. Discrepancy means a number, date, attribution, or wording differs. Unverifiable means no primary source could be found. Serious error means the paper states something the source contradicts.

- Record a new issue only when the second pass turns up a problem the first pass missed, and number it in the same sequence.

- Write the verdicts into a second report file and keep the first pass list unchanged, so the two passes can be compared line by line.

## Verify every number and fact

- List every number, date, case, quotation, and citation in the paper and check each one against its primary source.

- Try to disprove each number before accepting it, and check whether a rounded figure hides a material gap, such as a total rounded down by tens of thousands.

- Recompute every total from its parts and check that a total was not described as if it belonged to one part alone.

- Check that no cited source is dated after the paper completion date, and flag any citation that lands within days of completion as rushed rather than wrong.

- Check quoted wording character by character against the source, and record omissions of exceptions, limits, or second sentences as findings in their own right.

- Treat a gap as a dated finding with the sources you tried, and never write a number you could not verify as if it were confirmed.

## Challenge authenticity

- Keep three pairs of judgements apart at all times. Not found is not fabricated. Highly suspected AI assistance is not pure AI generation. A sloppy citation is not a fake citation.

- Weigh forensic signals against counter evidence before drawing any conclusion. Signals include program generated metadata, a creation time in the small hours, footnotes that do not match the bibliography, zero figures or tables, and identical access dates across unrelated footnotes.

- Counter evidence includes precise distinctions the author demonstrably made, such as a statute exception handled correctly or two near identical doctrines kept apart.

- State the verdict as a graded conclusion, such as content largely true with hard errors, or writing highly suspected to be AI assisted, and never as a certainty the evidence cannot support.

- Name the extra proof that would settle the question before the paper is submitted, such as a similarity report, earlier drafts, and supervision records, and list which items depend on that proof.

## Optional follow-up rounds

- Run follow-up rounds only when the user asks for them, never by default. There is no need to keep patrolling a paper that is finished.

- Use them only for a paper that is still being revised, or where the stakes justify another look, such as a defense or a submission.

- Keep the rounds short. Give each round one rotating angle, such as statutes, citations, cases, numbers, language, logic, dates, or structure, and name the angle in the round log.

- Stop at the first round that finds nothing. Do not wait for several empty rounds.

- Start each round by checking the file hash and modification time, and say in the log whether the paper changed since the last round.

- Search the old issue list before numbering anything new, and report only genuinely new findings.

- Log every round even when it finds nothing, and write the log file in the goal hidden files folder.

- Keep a correction ledger and retract an earlier conclusion in it as soon as new evidence overturns it, with the round number and the source that changed the answer.

- Deliver each round briefly to the user with its new findings only, and say when a round found nothing rather than staying silent.

- Do not put rounds on a timer by default. If the user wants a timed cycle, schedule it with `cron.add` on a 30 minute interval, owned by the goal or tracked item for the review, and stop the schedule when the user says stop, when the paper is finalized, or at the first round that finds nothing.

## Write the closing summary

- Read `/opt/muse/skills/documents/SKILL.md` first and follow its PDF workflow when the user asks for the final summary.

- Build the summary as HTML, render it with `/opt/muse/assets/artifacts/scripts/render_audit.mjs`, validate it with `/opt/muse/assets/artifacts/scripts/validate_pdf.sh`, and read every rendered page before delivering the file.

- Include sections for overall conclusions, the full first pass table, the full second pass table, later round findings if any rounds ran, the correction ledger, items still unverifiable, fix priority, and the round log if any rounds ran.

- Extract the issue tables from the report files with a script rather than retyping them, and check the extracted counts against the logs before rendering.

- Deliver the PDF as an attachment with a short summary of the headline conclusions and the total issue count.

## Keep the bookkeeping straight

- Keep per round logs, extraction scripts, and working notes in the goal hidden files folder, where the user does not see them.

- Keep deliverables the user asked for in the goal files folder, and do not copy a finished file into the user files folder afterwards.

- Record only durable outcomes in MEMORY.md, such as the total issue count, the verified facts that closed open questions, and the items still unverifiable.

- Close the tracked item for the review when the user stops the rounds or the final summary is delivered, and remove the schedule at the same time.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Ask the author for earlier drafts and supervision records at intake, since those settle authenticity questions faster than any text analysis.

- Confirm the word count rule with the institution before rewriting, since the same paper can pass under one rule and fail under another.

- Freeze the paper during a review cycle, and re-baseline the hash and counts whenever a new version arrives.

- Skip the follow-up rounds for an ordinary paper. The first pass and the second pass catch what matters, and rounds after that mostly return empty.

# 论文核查方法

这个 skill 来自一次法学论文核查，那次核查做了一轮首轮，一轮完整第二轮，和 25 轮半小时复查。像严格的考官一样审一篇学术论文，然后一直审到找不出新东西为止。这个方法有两层。首轮找问题。第二轮逐条对一手来源验证。短的后续轮查是可选的，只在论文还在改或利害足够大时才用。那次核查的轮查又找到 36 条问题，然后连续 5 轮没有新发现，所以轮查不再是默认做法。

## 收稿并定基线

- 向用户要论文文件和管这篇论文的要求文档或模板，先读完再下判断。

- 用 `pdftotext` 提论文文字，把提好的文字留作搜索和计数的底本。

- 按每一种可能的口径各算一遍字数并都记下来，比如只算正文，正文加摘要，含标点的字数，这样字数上限有争议时能指着某一行解决。

- 用 `md5sum` 记文件 hash 和修改时间，每一轮开始前再查一遍。

- 用 `pdfinfo` 看 PDF 元数据，把作者、创建工具和创建时间记作取证信号，本身不单独当结论。

- 问用户这是草稿还是终稿并记下来，因为几处判断会跟着变，比如没签名的声明和缺失的指导记录。

- 记下截稿日，过期了只说一次，用户不让再提就先放下。

- 问用户要找多少条问题，用户不说就用 100。

## 首轮找问题

- 对照要求文档和模板通读全文，找到的问题按一个连续序号编号。

- 按评分标准逐档对照检查，因为缺一个要素可能丢掉一整档分数，比如原创性或文献综述。

- 一直找到目标数为止，论文在目标数之前就没真问题了就直说。

- 绝不拿弱问题或琐碎问题凑数，也绝不把同一个问题换个编号再报一遍。

- 每个问题定一个严重级别。定为 blocker 就是交不上去或不及格。定为 major 影响分数或答辩。定为 minor 影响观感和印象。

- 每个问题写成同一格式，写明在论文里的位置、证据和作者能照着改的具体改法。

- 把清单交成报告文件，放在 goal 的 files 文件夹里，文件名或标题里写明条数。

## 第二轮全量复核

- 逐条回一手来源复核首轮每一条，这一轮是验证，不是再找新问题。

- 用 `browser.search` 搜，用 `browser.open` 读原文，优先一手来源而不是转述或转载。

- 法条对官方公布文本，引文对出版方或索引记录，案例对法院或监管机构的发布，标准对标准机构的记录。

- 每条只给一个结论。属实是一手来源一致。有出入是数字、日期、归属或措辞不同。无法验证是找不到一手来源。严重错误是论文写的内容和来源相反。

- 只有第二轮发现了首轮漏掉的问题才新编号，沿用同一序号。

- 结论写进第二份报告文件，首轮清单原样不动，两轮可以逐行对照。

## 核验每个数字和事实

- 列出论文里每个数字、日期、案例、引言和引文，逐个对一手来源核验。

- 接受每个数字之前先试着证伪它，再看取整是不是藏住了实质差距，比如总数往下取整了几万。

- 每个总数都从组成部分重算一遍，查总数是不是被说成只属于其中一部分。

- 查引用的来源没有晚于论文完稿日期的，完稿前几天内引用的标为仓促而不是错误。

- 引文逐字对原文，漏掉例外、限定或第二句话的，本身就是一条问题。

- 核实不了的记成一条带日期的发现，写明试过哪些来源，绝不把没核实的数字写成已证实。

## 质疑真实性

- 三对判断任何时候都要分开。查不到不是编造。高度疑似 AI 辅助不是纯 AI 生成。引用马虎不是引用造假。

- 下结论前先把取证信号和反证一起称。信号包括程序生成的元数据、凌晨的创建时间、脚注和参考文献对不上、零图表、互不相关的脚注访问日期完全相同。

- 反证包括作者确实做出的精确区分，比如某条法条的例外处理正确，或两个很像的学说被分得清清楚楚。

- 结论写成分级的，比如内容大体真实但有硬伤，或写作高度疑似 AI 辅助，绝不说证据撑不住的定论。

- 写明定稿前补什么证能把问题定下来，比如查重报告、旧稿和指导记录，并写明哪些条目要等这些证。

## 可选的后续轮查

- 只有用户要求才跑后续轮查，绝不默认跑。已经定稿的论文没有必要一直巡查。

- 只在论文还在改，或利害足够大值得再看一眼时才用，比如答辩或投稿。

- 轮查要短。每轮只定一个角度，比如法条、引文、案例、数字、语言、逻辑、日期或结构，角度写进轮次日志。

- 第一轮没有新发现就停，不要等好几轮空轮。

- 每轮先查文件 hash 和修改时间，日志里写论文自上一轮有没有变过。

- 编新号之前先查旧清单，只报真正的新发现。

- 每轮都记日志，空轮也记，日志文件放在 goal 的 hidden files 文件夹。

- 备一本修正账，有新证据推翻旧结论就马上在账里撤回，写明轮次和改答案的来源。

- 每轮简短报给用户，只报新发现，空轮也说一声而不是不吭声。

- 默认不要给轮查排定时任务。用户想要定时轮查才用 `cron.add` 每 30 分钟排一轮，挂在负责这次复查的 goal 或 tracked item 下面，用户叫停、论文定稿或第一轮没有新发现就停。

## 写结项总结

- 用户要结项总结时先读 `/opt/muse/skills/documents/SKILL.md`，按里面的 PDF 流程做。

- 总结先写成 HTML，用 `/opt/muse/assets/artifacts/scripts/render_audit.mjs` 渲染，用 `/opt/muse/assets/artifacts/scripts/validate_pdf.sh` 校验，交付前逐页读一遍渲染结果。

- 总结里要有总体结论、首轮全表、第二轮全表、后续发现（跑过轮查才写）、修正账、仍无法验证项、修改优先级和轮次日志（跑过轮查才写）。

- 表格用脚本从报告文件里提取，不要手抄，提取完先对条数再渲染。

- PDF 当附件交付，同时简短说主要结论和问题总数。

## 记好账

- 每轮日志、提取脚本和工作底稿放在 goal 的 hidden files 文件夹，用户看不到的地方。

- 用户要的交付物放在 goal 的 files 文件夹，事后不要再往 user files 文件夹里复制一份成品。

- MEMORY.md 里只记耐久结论，比如问题总数、已关闭的待核实事实和仍无法验证项。

- 用户叫停轮查或交付结项总结时关闭这次复查的 tracked item，同时删掉定时任务。

## 可用连接器

- 用 `muse.connector_search` 找其他连接器，用 `muse.skill_search` 找相关 skill。

- 这里没有合适的，就去网上找有维护的 API 或 MCP 服务，用 [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md) 接进来，或自己搭一个连接器。

## 效果更好的替代做法

- 收稿时就向作者要旧稿和指导记录，这些东西比任何文本分析都更快定真实性。

- 动笔改之前先和学校确认字数口径，同一篇论文按一个口径过关按另一个口径可能不过。

- 复查期间冻结论文，收到新版本就重新定基线，hash 和字数都重算。

- 普通论文跳过后续轮查。首轮和第二轮能抓住要紧的，再往后轮查多半是空轮。
