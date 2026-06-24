# Blog Writing Guidelines

This file is loaded by Claude Code when drafting or editing a post for anatoliybabushka.com/blog. Read it before writing. It governs the writing only; the HTML template, schema, and index linking live in the project's CLAUDE.md and the post template.

## How to use this

Draft for the reader first. Then run the editing passes and the pre-publish checklist at the end.

Rules lose to judgment on any single sentence. A post that obeys every rule and still reads like a machine assembled it has failed the one rule that counts: it has to sound like a person who knows the work. Where this doc gives a number, the number is the target; vary around it on purpose (see Sentence & paragraph mechanics).

## North-star voice

Write as Anatoliy: an engineering leader in Copenhagen who has led teams for more than a decade and still ships code. The voice is declarative and plain-spoken, concrete down to the example, confident without boasting.

What that means when you draft:

- **State things.** Assert; don't hedge. The author has led teams at Unity, Siteimprove, and VML MAP and shipped chartjs-php to 100k+ installs — write from that footing.
- **Lean on hands-on credibility.** A leader who still writes code is the main trust trigger for this audience. When a point can be grounded in a real commit, a code review, a maintenance burden, or a maintainer's-eye view, ground it there. That angle is the differentiator; use it.
- **Show the work; skip the title.** Authority comes from a real decision or a real number or a named failure. "As a seasoned leader" does the opposite — it reads as a substitute for evidence.
- **Stay provider-agnostic on AI** (see the canonical rule under Banned site phrases & framing).
- **Keep the message; rotate the phrasing.** The three themes recur across posts. A distinctive sentence must not. A signature phrase repeated across posts reads as a tic.

## Audience & purpose

Readers are engineering leaders, EMs and directors, senior+ engineers, and prospective clients sizing the author up. Assume they're smart and short on time, and that they've read a lot of empty content on these topics and now default to skeptical.

- The blog is a positioning and SEO asset. Each post builds credibility, serves a real search intent, and reads as the work of a senior practitioner.
- Write to one smart peer. The litmus for "don't over-explain": never define a term the reader searched to find this post, and never walk through basics a senior+ practitioner does daily.
- Watch the curse of knowledge — the opposite failure, and the more common one for an expert. Once you know something you can't easily feel what not knowing it was like, so you skip the step, leave *your* jargon undefined, or drop the reasoning that makes the point land. Calibrating to a peer guards against over-explaining; this guards against leaving the load-bearing context in your head. Name the concrete referent, walk the one inferential step that isn't obvious, show the example (see Sources, Pinker; Heath).
- Respect their time. The payoff lands on the first screen — inside the first ~100 words — not after a warm-up.
- Three themes anchor the blog: engineering leadership, moving AI from pilot to production, and building software teams. Keep posts inside them and interlink siblings (at least two related posts per piece) rather than scattering one-offs.

## What to say (substance & credibility)

The bar: a practitioner who has lived the problem reads it and thinks *yes, that's how it actually goes.* Most thought leadership misses that bar. Buyers rate the bulk of what they read as mediocre and a large share lose respect for the author afterward (see Sources, Edelman-LinkedIn 2025). Rigor and lived specifics close the gap.

The bolded leads below are imperative on purpose — this is a spec, not prose. Don't copy that uniform verb-first cadence into the post itself.

- **Lead with one debatable thesis** in the first one or two paragraphs. If no reasonable expert would disagree, it isn't a thesis. "AI is changing engineering" fails. "Most AI coding pilots die in the gap between the demo and the maintenance burden" works. (Team example: "Hiring senior engineers to fix a junior-heavy team usually makes onboarding worse before it helps.")
- **Contest an assumption the reader holds.** Name the common belief, then show where it breaks in practice.
- **Support every non-obvious claim** with a specific number, a named case, a firsthand detail, or a cited source — at least one proof point per major section. Nothing floats unsupported.
- **Show the instance, not the adjective.** "Onboarding was slow" tells; "the third engineer in a row hit the same undocumented auth step and lost a day" shows. Concrete detail also reads as credibility, not just color: a specific number or named instance shows you did the work, where vague language signals you didn't and seeds doubt (see Sources, Packard & Berger; GIJN).
- **Earn authority through a lived incident**, not a credential.
- **Steelman the opposing view first.** State the strongest version of the counterargument and concede what's true in it before you show why your position holds. Caricature reads as dishonest and makes the reader defensive.
- **Add what the top ten search results lack:** a contrarian read, a second-order effect they missed, the specific mechanism, a number from your own work. A post that only restates the consensus gets reframed or killed.
- **Explain the mechanism before the benefit.** Say *why* it works ("an agent guide cuts the cost of re-discovering context"), not that it's transformative.
- **Name the tradeoff.** Show the competing options and when each applies. Practitioners distrust writing that pretends every situation has one right answer.
- **Quantify your own experience.** Years, team size, deploy frequency, install counts, hours saved — precise, not "a lot" or "huge." (Vary the proof; don't paste the same four credentials into every post — that becomes the tic.)

## What NOT to say

- No safe, universally-agreeable premise dressed up as insight ("great teams need trust").
- No self-promotion or credential-dropping. "As a seasoned leader" is the canonical offender.
- No unsupported or invented statistics. Attribute every number to a real source or your own measured experience. A wrong stat is unrecoverable for a credibility asset; when unsure, describe the pattern qualitatively and concretely.
- No platitudes ("communication is key," "culture eats strategy"). Ground every principle in one specific instance.
- No vague-magnitude claims ("significantly improved," "a wide range of benefits"). Give the figure or the concrete outcome.
- No reused hook, phrase, or structure across posts.
- See Banned site phrases & framing for the canonical banned-phrase block.

## Structure & openings

Most readers scan rather than read, tracing an F-shaped path: two sweeps across the top, then down the left edge (see Sources, NN/g). Lead with the conclusion so the reader who quits after one paragraph still gets the point.

That F-path is a fallback, not a target. Readers default to it when the page is an undifferentiated wall of text with nothing to catch the eye, and it makes them miss anything sitting on the right side of a line. Clear, descriptive subheadings — plus bold and lists — pull the eye into a better scan (NN/g calls it the "layer-cake" pattern: read the headings, drop into the prose that matters). Structure is what earns you the more thorough reader; don't design *for* the F, design it away (see Sources, NN/g, layer-cake).

A note on front-loading, which this doc demands in several places: put the load-bearing information first — first sentence of the post, first words of each subheading, first sentence of each paragraph, first clause of each sentence. One principle, applied at every level.

**Openings**

- Open on the payload: a concrete claim, a real moment, a specific number, or a genuine non-obvious question. No warm-up.
- For this voice, prefer the concrete claim or the lived moment over a question. Never open on a rhetorical question with an obvious answer.
- Back a bold claim inside the same post, or you lose credibility faster than the opening earned attention.
- An opening's whole job is to make the reader continue: pose a real question they can't yet answer, or make a promise and set up a tension the post will resolve. A consciously felt gap between what they know and what they want to know is what pulls them down the page (see Sources, Zinsser; Loewenstein).
- Write the intro last, once you know what the piece argues. Keep it under ~150 words.
- In revision, test cutting the first paragraph or two outright. First drafts warm up before they start, and the piece often begins better a few sentences in — where you stop clearing your throat and start sounding like yourself (see Sources, Zinsser).

**Body**

- State the thesis in the first one or two paragraphs (within ~100 words). Never hold it for the conclusion.
- Run the body as an inverted pyramid: most important point first, then support, then nuance and caveats. Same for each section and paragraph.
- Use a narrative arc only when the story *is* the argument — a postmortem, a case study. Even then, give the takeaway near the top so scanners aren't forced to the end.

**Subheadings**

- Reading only the subheadings should tell the reader what the post argues.
- Subheadings are the highest-payoff scannability decision in the post, but only on two conditions: each one stands out visually, and each one accurately summarizes the section beneath it. A subheading that decorates or misleads breaks the scan instead of guiding it.
- Put the information-carrying word in the first two or three. Specific and concrete, never a pun. Aim for ~40–70 characters (roughly 5–9 words); enough to carry meaning, short enough to scan.

**Layering**

A post works at three depths: title alone, title plus subheadings, full prose. Verify by reading only the title, then only the subheadings, then the first sentence of each paragraph. The argument should land at each level.

**Endings**

- Close on the last substantive point or one concrete next step. End when the argument is done.
- An open question works as an ending only when you've deliberately left a tension unresolved — a genuine open problem, not the post's own thesis. If the piece is a straight inverted-pyramid explainer, there's nothing left hanging, so close on the last point.
- If you restate, restate sharply in one or two sentences that echo the opening. One next step at most.
- No recap closer. No "in conclusion," no wall of summary, no "the future is bright" wrap.

## Headlines, titles & meta

- **Page/meta title: ~50–60 characters.** Front-load the information-carrying words; drop leading articles. Make it a specific, honest promise, not a keyword string. Google rewrites a large majority of vague or stuffed titles and you lose the snippet (see Sources, Zyppy).
- **Stand alone.** The title has to make sense in a search result or a social feed with no surrounding context.
- **Plain over clever.** Specificity beats puns and curiosity-gap clickbait.
- **Keep evergreen titles dateless.** Don't put a year in a title meant to last; "...in 2026" dates the piece and invites a freshness penalty. Use a year only when the post is genuinely time-bound (a yearly review, a dated prediction).
- **Meta description: ~150–160 characters.** Summarize accurately and give a reason to click. It doesn't rank, but it drives clicks, and Google rewrites inaccurate ones.

Good: `What I learned moving AI from pilot to production` (specific, front-loaded, ~48 chars).
Good: `Why your staff-engineer ladder keeps stalling` (leadership, concrete).
Bad: `Engineering Leadership Tips, EM Advice, Managing Teams 2026` (keyword list with a date; will be rewritten).

## Sentence & paragraph mechanics

One number set governs sentence length. The rhythm rules below use the same set.

- **Average sentence: 15–20 words.** That's the average, not the ceiling. Comprehension stays high at short lengths and falls off sharply as sentences run long (see Sources, American Press Institute).
- **Hard ceiling ~30 words.** Past 30, split it or cut a clause. One idea per sentence.
- **Keep linked words close — distance is the real cost, not length.** Comprehension degrades as the gap widens between words that depend on each other: subject and verb, verb and object, a pronoun and what it refers to. The reader holds the first in a limited, decaying working memory until the second arrives. So a 28-word sentence with tight links can read easier than an 18-word one that strands its verb at the end. Above all, avoid center-embedding — a clause nested inside another that interrupts a dependency ("the engineer the manager the VP trusted hired quit"). One level is a strain; two stops parsing even when every word is simple (see Sources, Gibson, Dependency Locality Theory). This is the mechanism under the length rule: when a sentence gets hard, shorten the *dependencies*, not just the word count.
- **Vary length on purpose.** Mix short sentences (3–10 words) with the 15–20 average and the occasional long one near the 30 ceiling. Never run three or more same-length sentences in a row — uniform cadence is the strongest statistical tell of machine writing.
- **Use a one-line sentence for emphasis, rarely.** It's punctuation for a point, not a habit.
- **One idea per paragraph.** A second topic means a new paragraph.
- **Paragraphs: 2–4 sentences (5 max), 3–5 lines on screen.** Vary the length — some one line, some five.

**Verbs and words**

- Make the subject a real character — a person, a team, a system — and the verb its action. Before you keep a sentence, ask who is doing what. If the doer is buried, rewrite.
- Convert nominalizations back to verbs: "we made a decision to adopt" → "we decided to adopt"; "the implementation of the process" → "we implemented the process."
- Active voice, well over 90% of sentences. Passive only when the actor is unknown or beside the point.
- Take the short word: use (not utilize/leverage), help (not facilitate), more (not additional), to (not in order to), because (not due to the fact that).
- Take the precise verb: ship, not "launch"; resigned or was fired, not "left."
- Take the concrete: "cut deploy time from 40 minutes to 6," not "improved efficiency significantly."
- Order information old-to-new: open each sentence on something already known, end on the new point, then make that new point the known opener of the next. Put the word you want stressed last.

**Lists**

- Convert prose to a list for 3+ parallel items, sequential steps, or a set of criteria. Five to seven items is the sweet spot; split past eight.
- Keep items parallel and short, roughly one line. Don't bury a multi-sentence explanation in a bullet.
- Argument and nuance stay in prose. Over-listing chops reasoning into fragments and is itself a tell.

## POV, tense & locale

- **First person.** Use "I" for the author's own decisions and anecdotes ("I restructured the team..."); "we" for team actions where the author was one of several. Address the reader as "you."
- **Tense.** Past tense for the anecdote; present for the standing claim or principle it supports.
- **Spelling: US English** throughout (organize, behavior, optimize), for consistency across the site and the widest search match. Pick it once and hold it.

## Code, images & links to others

- **Code blocks.** Show real, runnable snippets when code makes the point faster than prose. Keep them short — the few lines that matter, not a whole file. Don't paste code only for decoration.
- **Images and diagrams.** Use one only when it carries information words can't. Every image needs descriptive alt text stating what it shows (a WCAG requirement; see project CLAUDE.md). No stock photos.
- **Citing other practitioners.** Quote or paraphrase a named peer (Larson, Majors, Fournier, Orosz) when they sharpen or counter your point, and link to the source. Engage the idea — agree, extend, or push back — rather than name-dropping for borrowed authority. External links to a primary source build E-E-A-T; they're separate from the internal-link rule below.

## Readability targets

- **Flesch Reading Ease 50–70 (Flesch-Kincaid grade 8–12).** Lean 50–60 for deep technical posts, 60–70 for broader leadership pieces. Below 50 reads academic; above 80 reads thin and undercuts seniority.
- **Cut hard.** Aim to say the same thing in roughly half the words a first draft uses. Concise copy is measurably more usable (see Sources, NN/g).
- **Line measure ~66 characters** (50–75 fine, never past 80). The blog CSS already targets this; don't fight it.
- **No word-count target.** Word count doesn't rank. Cover the topic, then stop. An opinion or framework piece runs ~800–2,000 words; go longer only for a genuine research synthesis, and only if every paragraph earns its place.

## SEO & E-E-A-T

Google rewards demonstrable, people-first value. Trust matters most, and firsthand experience is the signal generic AI content can't fake. Write for the reader first, then check the search fit.

- **Write from firsthand experience.** Include the specifics only someone who did the work would know: the real number, the decision, the tradeoff, what broke, the outcome. Strongest E-E-A-T signal there is, and the hardest to fake.
- **Match one search intent per post.** Identify the dominant intent (informational, commercial, navigational) and fit the format: how-to or explainer for informational queries, comparison framing for commercial. A format mismatch fails regardless of quality.
- **Front-load a direct answer.** Right after the H1 — and again under any question-phrased H2 — give a self-contained 40–55 word answer to the core question, then expand. This is the opening "payload" rendered as a snippet-ready paragraph; the two rules describe the same first move, one for humans scanning and one for featured snippets and AI summaries.
- **Phrase some headings as the questions readers actually search.** This serves SEO and screen-reader navigation with the same markup. (Heading order and semantic markup: see project CLAUDE.md.)
- **Comprehensiveness, not length.** Cover the relevant subtopics and follow-on questions, then stop.
- **Build topical authority.** Keep posts inside the three themes and interlink them.
- **Internal links: 2–5 per ~1,000 words**, in the body, with descriptive 2–5 word anchors that name the destination. Never "click here." Vary the anchor when pointing repeatedly to one page.

Good anchor: `restructured the team around ownership`. Bad anchor: `click here`.

## Engineering-leadership genre norms

The respected end of this genre — Larson, Majors, Fournier, Orosz — earns trust through lived specifics and honesty about limits, then edits hard.

- **Answer first.** Most readers want the answer, not the path you took to it. Conclusion or concrete situation up front, reasoning after.
- **Anchor every general claim in a lived instance.** The pattern: situation → tension or tradeoff → what you did → outcome. No section should be purely abstract.
- **Bound your conviction.** State what you actually believe, counterintuitive positions included, then bound it ("this helps in case X; for most teams, do Y"). Readers spot inauthenticity within two paragraphs.
- **Commit to one post shape:** framework, war-story-to-lesson, opinionated take, how-to/runbook, or research synthesis. Don't blend all of them into a shapeless essay.
- **Edit down.** Make at least one full pass purely to cut; a tight single-argument piece beats a sprawling one. Avoid 5,000-word monstrosities.
- **Respect the reader as a peer.** Reference the years of doing the thing; don't re-explain the basics (litmus under Audience & purpose).
- **Publish only if it adds something:** a non-obvious belief, a tradeoff you lived, an assumption you reject, a place your thinking changed. Restating conventional wisdom isn't worth publishing.

## Banned site phrases & framing

One canonical block. Other sections point here.

**Never write these (established site rules):** "let's connect," "create success together," stated client caps, urgency theatrics ("act now," "limited spots"), or any self-promotional sign-off.

**Provider-agnostic on AI tooling.** Lead with generic terms ("agent guide," "agent-instructions file"). Name CLAUDE.md or AGENTS.md sparingly, as examples among others, never as the only option. Never write as if one vendor is the whole field. This holds everywhere: drafting, examples, and the consistency editing pass.

## Avoiding AI-writing tells

Detectability runs on two layers. The lexical layer is over-used words. The structural layer — negated contrasts, forced triplets, formulaic intros and recaps, uniform rhythm — is the stronger fingerprint and survives word-swapping. Fix both. Specificity, deliberate rhythm variation, and asymmetric structure are the real defenses.

### Banned words & phrases

Cut or replace every instance:

> delve, delve into, dive into, deep dive, realm, tapestry, landscape (as in "the X landscape"), intricate, intricacies, underscore(s), showcase/showcasing, leverage, robust, seamless/seamlessly, elevate, unlock, harness, foster, pivotal, crucial, paramount, testament (to), navigate (as metaphor), game-changer, move the needle, low-hanging fruit, paradigm shift, secret sauce, north star, meticulous, commendable, vibrant, holistic, synergy, cutting-edge, groundbreaking, revolutionize, transformative, unparalleled, garner, resonate, unwavering, boast, empower, streamline, frictionless, supercharge, ever-evolving, rapidly evolving, in today's fast-paced world

Plain replacements: leverage → use; robust → strong, reliable, well-tested; seamless → smooth, or "no handoff gaps"; showcase → show; elevate → improve, raise; unlock → enable; foster → build, encourage; harness → use, put to work; delve into → look at, dig into; pivotal/crucial → important, or name *why* it matters; testament to → shows, proves; garner → earn, attract; resonate → land, ring true; empower → let, enable; streamline → simplify, speed up; supercharge → speed up, boost.

Also cut filler and windups: "it's important to note that," "it's worth noting," "needless to say," "that said," "when it comes to," "here's the thing," "here's the hard truth," "let's be honest," "great question," "most people don't realize."

### Banned structures

- **Negated contrast** — "it's not just X, it's Y," "not only... but also," "this isn't management, it's leadership." The most recognizable tell. Target zero per post. State Y on its own, or split into two sentences that each add information.
- **Forced rule-of-three** — "Fast. Simple. Effective." Triplets that always resolve into three balanced items. Use two, four, or five; let item lengths run uneven. One deliberate tricolon per post at most.
- **Hedge-opener intro** — "In today's fast-paced world," "In the world of," "When it comes to." Open on the concrete point.
- **Recap closer** — "In conclusion," "In summary," "Overall," "Ultimately," "At the end of the day," plus the resolution closer ("The companies that adapt will be the ones that lead"). End on the last real point.
- **Sycophantic / performative-honesty openers** — "Great question," "Let's be honest," "Here's the hard truth." Make the point.
- **Over-signposting** — "First, we'll look at... Second, we'll examine... Finally..." Let headings and content do it.
- **Five-paragraph scaffold** — intro, three symmetric body sections, recap. Vary section sizes; they shouldn't sit within ~20% of each other.
- **Applause lines** — short punchy standalone sentences that exist only as emotional punctuation and could pass as a social post on their own. Delete them.

### Rhythm and punctuation

- **Vary sentence length** per the one number set above (3–10 short, 15–20 average, up to ~30). Don't cluster three or more consecutive sentences at the same length; that metronome is the core statistical tell.
- **Vary paragraph length too.** Some one line, some five. Reject the topic-sentence → evidence → mini-conclusion template applied uniformly.
- **Em-dashes: one per ~3 paragraphs at most.** Use one only where a comma, period, or parenthesis can't do the job. The em-dash alone doesn't prove AI; clustering does. Vary the breaks.
- **Keep one human qualifier, don't stack them.** A single "in my experience" or "usually" humanizes. A stack ("while this may vary, generally speaking, in most cases...") is a tell. One qualifier per claim.

### Final stacking check

With every banned word gone, scan for accumulated moves: parallelism, symmetric sections, a resolution ending, applause lines. Detectability is structural; it surfaces when signals stack. Pull the stack apart.

**Don't over-polish.** The newest tell isn't a word — it's evenness. Measured against human writing, AI prose runs longer, more uniformly complex, more lexically diverse, and conspicuously *cleaner*, with every sentence sanded to the same finish (see Sources, Kobak et al.; Antislop; ScienceDirect 2026). The fix is not to insert errors. It's to leave the human texture in: a blunt three-word sentence next to a long one, a plain word repeated where a synonym would only preen, a digression, a section that runs short because the point was short. The lexical fingerprints (delve, underscore) are a moving target as models are retrained to suppress them; this structural over-smoothness is the more durable one.

## Editing & revision

Revise in separate single-purpose passes. The brain can't catch wording and logic and typos at once.

1. **Structure & cut.** Thesis up top? Does each section earn its place? Is the shape one recognizable type? Kill the darlings — anything kept because you like it rather than because it serves the reader.
2. **Needless words & intensifiers.** Delete very, really, quite, actually, basically, just, simply, in fact. Reread; if the meaning holds, the word was filler. Fix wordy connectives: "in order to" → "to," "due to the fact that" → "because," "the fact that" → cut. Collapse redundant pairs: "final outcome" → "outcome," "each and every" → one.
3. **Concrete vs. abstract.** Swap vague nouns and claims for names, numbers, dates, examples. One concrete example per substantive claim, or cut the claim. Run "so what?" on every paragraph.
4. **Cohesion.** Apply old-to-new: each sentence opens on the known, ends on the new. Use "this/that + noun" and real connectors (therefore, however, as a result), never a bare "This."
5. **Consistency.** Same term for the same concept. Keep AI language provider-agnostic (see Banned site phrases & framing). Confirm no distinctive phrase repeats inside the piece or across the blog.
6. **Read aloud.** Read the whole draft aloud (or text-to-speech), finger on each word. Every stumble or breath-run-out or reread marks a sentence to fix.
7. **Fact-check, skeptically.** Verify every name, date, number, quote, and link on its own.
8. **AI-tell pass.** Run the banned-words and banned-structures lists, then the final stacking check.

## Pre-publish checklist

- [ ] One debatable thesis, stated in the first one or two paragraphs.
- [ ] At least one reader assumption named and contested.
- [ ] Every non-obvious claim has a concrete proof point (number, case, firsthand detail, or source).
- [ ] At least one lived, specific anecdote; zero credential-dropping.
- [ ] The strongest counterargument is steelmanned, not strawmanned.
- [ ] Hands-on/IC credibility used where the point allows it.
- [ ] AI-tooling claims are provider-agnostic and explain the mechanism.
- [ ] Opening delivers the payload in the first one or two sentences; intro written last.
- [ ] Title alone, then subheadings alone, then first sentences alone — the argument lands at each level.
- [ ] Title ~50–60 chars, front-loaded, stands alone, no stray year. Meta description ~150–160 chars.
- [ ] Direct 40–55 word answer front-loaded after the H1; some headings phrased as searched questions.
- [ ] Average sentence 15–20 words; none over ~30; length varied (no metronome).
- [ ] Linked words kept close (subject–verb–object); no center-embedded/nested clauses.
- [ ] Paragraphs 2–4 sentences; one idea each; front-loaded.
- [ ] Active voice >90%; nominalizations converted to verbs.
- [ ] First person; US spelling; past tense for anecdote, present for principle.
- [ ] Flesch Reading Ease 50–70.
- [ ] 2–5 contextual internal links per ~1,000 words; descriptive anchors; at least two sibling posts linked; post stays inside the three themes.
- [ ] External links to named practitioners' primary sources where used; code snippets short and real; images carry information and have alt text.
- [ ] Banned words: zero. Banned structures: zero (negated contrast especially).
- [ ] Not over-polished — human texture left in (uneven sentence/section lengths, no uniform smoothness); no inserted errors.
- [ ] Em-dashes ≤1 per ~3 paragraphs; punctuation varied.
- [ ] No recap closer; ends on the last real point or one clear next step.
- [ ] Read aloud, fact-checked, no signature phrase repeated, no banned site phrase.
- [ ] Semantic HTML, heading order, WCAG AA contrast, no inline styles (see project CLAUDE.md).

## Sources

**Reading on the web & structure** — Nielsen Norman Group: *Inverted Pyramid: Writing for Comprehension*; *F-Shaped Pattern of Reading on the Web* (and *...Pattern Discovered*, 232-user eyetracking); *The Layer-Cake Pattern of Scanning* and *Text Scanning Patterns: Eyetracking* (F → spotted → layer-cake → commitment; F-pattern as a failure mode of weak formatting); *How Users Read on the Web*; *How Little Do Users Read?*; *Microcontent: How to Write Headlines, Page Titles, and Subject Lines*; *Headings Are Pick-Up Lines*. Orbit Media, *7 Ways to Write Better Opening Paragraphs*. Uplift Content, *How to End a Blog Post with Maximum Impact*.

**Sentence & readability mechanics** — plainlanguage.gov, *Federal Plain Language Guidelines*. CDC, *Plain Language Materials & Resources*. American Press Institute (comprehension vs. sentence length). Siteimprove (20-word flag). Gibson, *Linguistic complexity: locality of syntactic dependencies* (Cognition, 1998 — Dependency Locality Theory; center-embedding becomes unprocessable); Futrell, Gibson & Levy, *Lossy-Context Surprisal* (Cognitive Science, 2020 — information locality); Lewis, Vasishth & Van Dyke, *Computational principles of working memory in sentence comprehension* (Trends in Cognitive Sciences, 2006). Baymard Institute & UXPin (50–75 CPL line length). Yoast & Elite Editing (Flesch Reading Ease bands). Get It Write (parallel lists); ClickHelp (when to use lists).

**Voice & style** — Orwell, *Politics and the English Language*. Zinsser, *On Writing Well* (clutter-cutting; the bracket technique; cutting the warm-up opening). Williams & Bizup, *Style* (characters/actions, old-to-new cohesion). Strunk & White, *The Elements of Style* (Gotham Writers; Life Junctions). Pinker, *The Sense of Style* (the curse of knowledge). Heath & Heath, *Made to Stick* (concreteness = human action + sensory detail; the curse of knowledge).

**Substance & credibility** — 2025 Edelman-LinkedIn *B2B Thought Leadership Impact Report* and Edelman quality-gap analyses. HBR, *The Guru's Guide to Creating Thought Leadership* and *Contributor Guidelines for HBR Authors*. Thompson Editing (show, don't tell). Packard & Berger, *How Concrete Language Shapes Customer Satisfaction* (Journal of Consumer Research, 2021 — concreteness reads as listening/credibility). GIJN, *How to Write Openings That Hook the Reader* (concreteness as proof-of-work; hook-and-twist). Loewenstein, *The Psychology of Curiosity* and Golman & Loewenstein (the information-gap model of curiosity). Green & Brock, *The Role of Transportation in the Persuasiveness of Public Narratives* (JPSP, 2000 — narrative transportation reduces counterarguing). Speaking About Presenting (credibility without bragging). The Steelman Approach (ArguFight).

**SEO & E-E-A-T** — Google Search Central: *Creating Helpful, Reliable, People-First Content*; *E-A-T gets an extra E for Experience*; *Article structured data*; *SEO Link Best Practices*. W3C WAI, *Headings*. Zyppy & Destination Digital (title/meta length). Yoast (word count; headings). Backlinko (search intent; E-E-A-T). Seer Interactive (featured snippets). Semrush (internal links).

**Engineering-leadership genre** — Will Larson, *Making engineering strategies more readable* and *Unexpected anti-patterns for engineering leaders*. Charity Majors and Gergely Orosz on technical blogging (*Write that blog!*; Blogging for Devs). Instant Press (thought-leadership mistakes).

**AI-writing tells** — Kobak et al., *Delving into ChatGPT usage in academic writing through excess vocabulary* (Science Advances, 2025 — "delves" ~28×, "underscores" ~13.8×, "showcasing" ~10.7×; ≥13.5% of 2024 abstracts LLM-processed). Paech et al., *Antislop* (arXiv 2510.15061, 2025 — "slop" phrases appearing >1,000× human baseline; the "not just X but Y" construction named and suppressed). *AI vs. human prose* corpus comparison (ScienceDirect S2215039026000056, 2026 — AI text longer, more uniformly complex, higher lexical diversity, ~4× fewer errors; over-polish as a structural tell). FSU/ICCL "delve" study. Bloomberry, *AI Sentence DNA: 7,400+ AI Writing Patterns*. Wikipedia, *Signs of AI writing*. Matthew Vollmer, *A Field Guide to AI Tells*. The Conversation & FIU News (em-dash overuse).

**Editing & revision** — University of Chicago Harris Writing Workshop (pruning needless words). McPhee, *Draft No. 4* (revision as the essence; read-aloud; box-the-word; dictionary over thesaurus; the bad first draft). UNR, GMU, Yale (known-new contract / cohesion). UNC & Duke writing centers (reading aloud). Medium Handbook, *A Self-Editing Checklist From an Editor-in-Chief*. Writer's Digest (omit needless words). Writing Mastery (kill your darlings).
