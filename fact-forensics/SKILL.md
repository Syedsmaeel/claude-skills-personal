---
name: fact-forensics
description: Rigorous fact-checking and information forensics — checking if a claim is a recycled hoax, tracing claims to origin (incl. which of two text versions came first), assessing source credibility, catching misquotes/misleading stats/out-of-context media, checking political framing separately from accuracy, measuring how widely/how many times a claim spread, checking for coordinated/bot amplification, mapping who benefits, and producing a structured verdict report. Use whenever asked to fact-check, verify a claim/statistic/quote, check if a story/image/video is true, assess source credibility or bias, evaluate a viral claim, compare rewrites of a text, measure reach, check if spread looks astroturfed, or ask who benefits — even without saying "fact-check." Trigger for "is this real," "verify this," "trace to the source," "who said this first," "is this biased," "how many times shared," "was this bot-driven," "who benefits," "debunked before," or "debunk this."
---

# Fact & Information Forensics

Treat every claim like evidence at a scene: don't trust it because it looks credible, don't dismiss it because it sounds implausible — trace it back to where it actually came from and see if the trail holds up.

## Why this matters

Most misinformation isn't outright fabrication — it's a real fact stretched, a real quote trimmed, a real statistic stripped of its denominator, a real photo from the wrong year or country. A surface-level check ("does this sound true?") misses almost all of that. The value of this skill is doing the boring, mechanical part properly: finding the primary source, checking what it actually says, and being explicit about what's confirmed versus what's still open.

## Scope: match the depth to the question

Not every question needs all ten steps — running the full pipeline on "did X really say this?" wastes the person's time and buries a simple answer. Triage first:

- **One simple claim, easily settled** (a single quote, date, or figure) → Steps 1-3 and 6 only, answered in a few sentences of prose. No templates, no headers.
- **A multi-claim article, post, or screenshot** → Steps 1-6 with the per-claim output format.
- **Steps 7-10 (framing, exposure, amplification, incentives)** → only when the person asks for that specific thing, or when something in the earlier steps makes it directly relevant. Never append them by default.

When in doubt, do the smaller version and offer the deeper checks: "I can also look at how widely this spread, or how the coverage is framed, if useful." Over-delivering a ten-section report on a yes/no question isn't thoroughness, it's noise.

## Step 1 — Break the input into checkable claims

Don't fact-check "the post" as one blob. Pull out each discrete, checkable assertion (a statistic, a quote, an event, a causal claim, an attribution). A single tweet or article often bundles 3-5 separate claims with very different levels of support — some solid, some fabricated, some true-but-misleadingly-framed. Check each one separately and don't let one strong claim launder the others.

Ignore claims that are pure opinion or unfalsifiable ("this is outrageous") — flag them as opinion, don't try to verify them.

## Step 2 — Check whether this is a recycled claim ("zombie claim")

Before doing fresh investigative work, search for whether this exact claim (or a near-identical version) has already circulated and already been checked. A large share of viral misinformation isn't new — it's an old fabricated quote, a recurring miscaptioned photo, or a hoax statistic that resurfaces every so often, sometimes with the date or names swapped.

- Search for the claim's distinctive phrasing/numbers/image alongside terms like "fact check," "false," "debunked," "hoax," or "misattributed."
- If a credible prior fact-check exists for this exact claim, treat it as strong existing evidence — verify it's still applicable (nothing material has changed) rather than blindly repeating it, then cite it directly instead of re-deriving the same conclusion from scratch.
- If the claim recurs periodically (a seasonal hoax, a quote that gets re-dated every year), say so explicitly — that recurrence pattern is itself useful information for the person asking.
- If nothing turns up, say that plainly and proceed to full investigation — absence of a prior debunk is not evidence of truth, just absence of prior work to build on.

This step saves redundant work when it hits, and costs only one search when it doesn't — worth doing before Step 3, not after.

## Step 3 — Trace each claim to its origin

For each claim, search for the earliest / most primary version of it, not just the first article that shows up:
- A statistic → find the original dataset, report, or agency (not the third blog citing a blog citing a blog)
- A quote → find the original recording, transcript, or interview, not an aggregator's paraphrase
- A photo/video → reverse-image-search it, check upload dates and original posting context, look for the earliest known appearance
- An event → find primary reporting (wire services, the outlet actually present, official statements) before secondary commentary

If you can't reach the primary source, say so explicitly rather than treating a secondary source as equivalent. A claim sourced only to "people are saying" or an unlinked screenshot is a different confidence tier than one sourced to a named primary document.

### When two versions of the same text exist, don't assume which came first

Text similarity can tell you that two versions are related and roughly how (near-identical, paraphrased, or meaning-altered) — it can never tell you which one was published first. Polish is not a timestamp: a slicker, more "authoritative-sounding" rewrite is often the *later* version, not the original, and assuming otherwise is a common way forensics goes wrong. Treat "which came first" as a provenance question that has to be argued from evidence, not read off the text:

1. **Gather independent evidence lines**, ranked by how hard they'd be to fake — a verified archive snapshot (Wayback Machine, platform API metadata, wire-service dateline) beats a displayed "posted X days ago," which is trivial to spoof. Also check for structural tells: does one version reference information the other couldn't have had yet?
2. **State what each ordering would require to be true**, then check which one the hard-to-fake evidence actually supports.
3. **Actively look for disconfirming evidence** before settling on an answer — the usual failure mode is stopping at the first piece of evidence that fits a plausible story.
4. **Report origin on the same confidence scale as everything else**: Confirmed (multiple hard-to-fake sources agree), Likely (one strong source, nothing contradicting), or Unverified (no reliable timestamp either way — and "sounds more original" is never a substitute for one).

Use text-similarity as triage only: it tells you *that* an investigation is worth doing and roughly *what kind* of edit you're looking at (a light paraphrase vs. a meaning-altering change), not who copied whom. A quick way to characterize the edit type — useful for flagging which pairs deserve the closer provenance work above — is comparing semantic similarity against lexical similarity: high on both means near-verbatim, high semantic/low lexical means an honest paraphrase, and **low semantic/high lexical is the pattern worth flagging hardest** — it's what a trimmed or doctored quote looks like (looks like the same text, means something different).

## Step 4 — Assess source credibility

Weigh sources on things that actually predict reliability, not on brand recognition alone:
- **Track record** — has this outlet/account been caught fabricating or seriously misrepresenting things before?
- **Incentive** — does the source profit from the claim being believed (ad revenue on outrage, a product being sold, a political outcome)?
- **Transparency** — does it name authors, cite primary sources, correct errors publicly?
- **Independence** — is this actually a second source, or just the same original claim re-shared?

Multiple outlets repeating a claim is not multiple confirmation if they're all downstream of the same single original source — check whether "everyone is reporting this" collapses to one origin point.

## Step 5 — Watch for the common distortion patterns

These account for most misleading-but-not-fabricated content:
- **Numbers without denominators or baselines** ("cases doubled" — from what to what, over what period, is this normal seasonal variation?)
- **Correlation presented as causation**
- **Quotes trimmed to reverse or flatten their meaning** — always check the sentence(s) immediately before/after a quoted line
- **Real media, wrong context** — an authentic photo/video from a different event, date, or location
- **Old news re-shared as current**
- **Selective framing** — a true fact chosen specifically because it implies something false by omission
- **Fake precision** — a suspiciously exact number presented without a source, designed to sound authoritative
- **Satire or parody sources** mistaken for real reporting

### Statistical sanity checks

When a claim rests on numbers, run these before accepting the figure — most bad statistics fail one of them:
- **Is the base rate given?** "Risk tripled" means nothing without knowing whether it went from 1-in-10 to 3-in-10 or from 1-in-3,000,000 to 3-in-3,000,000.
- **Absolute or relative?** A "50% reduction" in relative risk can be a fraction of a percentage point in absolute terms. Check which is being reported — the misleading version is almost always the relative one.
- **Is the sample size and population stated?** A percentage with no N behind it, or one drawn from a self-selected sample, doesn't support a general claim.
- **Do the numbers actually add up?** Percentages summing past 100, totals that don't match their components, figures inconsistent with a stated denominator — arithmetic errors are common and quick to check.
- **Is the comparison period cherry-picked?** Check whether the start date was chosen because it's the low point; extend the range and see if the trend survives.
- **Rate vs. count?** Raw counts rise with population size while the underlying rate may be flat or falling.

### Translation distortion

For claims that crossed languages, meaning can shift before anyone deliberately rewrote anything — a translated quote may be faithful to the translator's reading but not to the speaker's sense, and idioms, honorifics, and hedging words routinely get flattened. Where a claim originates in another language:
- Find the original-language source, not just the translated report
- Check whether a contested word carries the same connotation in the original (a word rendered as "demanded" may be closer to "requested")
- State explicitly when a verdict rests on a translation you couldn't check against the original — that's a lower confidence tier, not a Confirmed

## Step 6 — Give an honest confidence level, not a binary

Real verification rarely lands on a clean "true" or "false." Use something like:
- **Confirmed** — verified against a primary source, no material caveats
- **Partially true / missing context** — the core fact checks out but the framing is misleading
- **Unverified** — no primary source found either way; state what's missing, don't guess
- **False** — contradicted by primary sources
- **Fabricated / out of context** (for media) — real asset, false claim about it

Resist the pull toward false balance. If the evidence clearly supports one side, say so plainly — "unverified" is for genuine uncertainty, not a hedge to avoid an uncomfortable conclusion. Equally, don't overstate confidence a search didn't earn.

### When the honest answer is "unverified"

An unverified verdict shouldn't leave someone with a shrug. Make it actionable:
- **Say what's missing specifically** — "no primary source names the hospital" is useful; "couldn't confirm" isn't.
- **Say what would settle it** — the document, dataset, or record that would resolve this if it surfaced, and where it would come from.
- **Say which way the weak evidence leans, if it leans** — "nothing confirms it, and the only account naming a location gets that location wrong" is an honest signal without overclaiming.
- **Give a watch-for** — if this is developing, what would indicate it's firming up (an official statement, a named on-record source) versus falling apart.
- **Don't let unverified drift into implied-false.** A claim nobody has documented is not the same as a claim that's been checked and contradicted; say which one you're reporting.

## Step 7 — Framing / lean check (separate from the truth verdict)

A claim can be entirely accurate and still be framed to lean left or right — through word choice, what's included or left out, and which voices get quoted. Keep this strictly separate from the Step 6 verdict: never let a framing judgment change a truth verdict, and never let a "true" verdict imply the framing was neutral. Collapsing the two into one score is how fact-checking loses credibility with everyone.

Check both directions, not just one:
- **Omission pattern** — compare the same story across outlets on both sides; what does each choose to leave out? Usually the strongest and hardest-to-deny signal.
- **Source selection** — who's quoted as an authority/expert vs. who's quoted as "critics say" or left unnamed
- **Loaded language** — evaluatively charged verbs/adjectives ("slashed" vs. "reduced," "claimed" vs. "said," "regime" vs. "government")
- **Headline vs. body gap** — does the headline imply more than the article actually supports
- **Framing of causation** — which actor is made the grammatical subject of a negative outcome

Don't over-weight weak signals: an outlet's general reputation alone, a single word in isolation, or social-media reaction to a piece are not reliable evidence of lean on their own — they need to co-occur with something concrete from the list above.

There's no primary source to check framing against the way there is for a fact, and established bias-rating methodologies disagree with each other on the same article — so don't force this into a single left-right score. Report it as findings, not a verdict:

```
## Framing check
**Rightward-leaning indicators:** <specific word/omission/framing choice, with example>
**Leftward-leaning indicators:** <specific word/omission/framing choice, with example>
**Compared against:** <what other coverage this was checked against>
**Assessment:** <plain-language summary — e.g. "charged language typical of X-leaning coverage, but the underlying facts match neutral wire reporting">
```

Only run this step when the user is asking about slant/bias/framing specifically, or when a piece mixes accurate facts with clearly loaded language — don't append it to every routine fact-check by default.

## Step 8 — Measure exposure and spread

Separate from whether a claim is *true* is how far it's actually *traveled*. This matters forensically because raw hit-count is misleading on its own — a claim can look "everywhere" while really coming from one origin (an echo), or look obscure while actually reaching a huge audience through one high-traffic node. Don't report a bare number of search results as "exposure" without doing this decomposition.

**1. Collect occurrences.** Search across news, social platforms, and forums for verbatim and near-verbatim instances of the claim (reuse the semantic/lexical comparison from Step 3 to catch paraphrased reposts, not just exact-text matches).

**2. Cluster by origin, not by URL.** Group occurrences into independent origin clusters using the same provenance discipline as Step 3 — outlets that are all downstream of one wire report or one original post count as *one* origin, however many domains reprinted it.

**3. Compute the redundancy ratio:**

$$R = \frac{M_{total}}{M_{unique}}$$

where $M_{total}$ = total instances found and $M_{unique}$ = number of independent origin clusters. A high $R$ (e.g. 40 mentions, 2 origins) means apparent ubiquity is really an echo of one or two sources — report this explicitly, since "cited by dozens of outlets" reads as corroboration to most readers when it may not be.

**4. Weight by reach, where reach data is available.** A raw mention count treats a post with 50 views the same as one with 5 million. Where follower counts, site-traffic tier, or syndication data can be found, report a reach-weighted exposure alongside the raw count rather than instead of it — don't silently substitute one for the other:

$$E = \sum_{i=1}^{M_{unique}} r_i$$

($r_i$ = a reach proxy for origin cluster $i$ — follower count, estimated readership, etc. State the proxy used; don't present this as a precise audience figure.)

**5. Track spread over time, not just a total.** Note first-seen date and, where dates are available across occurrences, whether spread is accelerating, steady, or already fading — a claim still gaining new independent origins is a different situation than one that peaked and stopped. When there's enough dated data to plot, use a chart to show mentions over time rather than describing the trend only in prose.

**Report as its own block, separate from the truth verdict** — exposure size says nothing about accuracy, and the two must never be merged into one score:

```
## Exposure check
**Total mentions found:** <M_total>
**Independent origins:** <M_unique>
**Redundancy ratio:** <R> — <one line reading it, e.g. "highly redundant: nearly all reposts trace to a single original post">
**Reach-weighted exposure:** <E, with the proxy stated> or "not computed — reach data unavailable"
**First seen:** <date, confidence>
**Trend:** accelerating / steady / fading / insufficient data
```

Only run this step when the user asks about reach, virality, how widely something spread, or how many times something was republished — it's not part of the default per-claim verdict.

## Step 9 — Check for coordinated / inauthentic amplification

High exposure alone (Step 8) doesn't say whether spread was organic or engineered. This step looks specifically for signs that amplification was coordinated rather than a claim genuinely catching on:

- **Synchronized posting** — near-identical wording appearing across unrelated accounts within an unusually tight time window, rather than spreading gradually
- **Account-age/activity anomalies** — early amplifiers that are newly created, low-activity, or post almost nothing except content in this claim's category
- **Copy-paste uniformity** — many "independent" posts sharing the exact same phrasing, typos, or formatting, which is unusual for organic reactions but typical of a script or provided talking points
- **Origin-to-scale mismatch** — a claim reaching large audiences unusually fast relative to the size/reach of its original origin cluster from Step 8

None of these individually prove coordination — synchronized posting can happen organically around real breaking news, and copied phrasing can just mean people are quoting the same source. Treat this the same way as Step 10's incentive mapping: report what was observed, not a conclusion about who orchestrated it, unless there's direct evidence of coordination (e.g. a leaked messaging list, a platform's own takedown notice citing coordinated behavior).

```
## Amplification check
**Signals observed:** <which of the above were found, with specifics>
**Signals not observed:** <which were checked and not found — absence matters too>
**Assessment:** <"consistent with organic spread" / "shows some signals of coordination, not conclusive" / "platform-confirmed coordinated activity," with the confidence tier stated>
```

Only run this step when the user asks whether something was "bot," "astroturfed," "coordinated," or "artificially boosted," or when Step 8's exposure data shows an origin-to-scale mismatch worth explaining.

## Step 10 — Map incentives (descriptive only, never a verdict on intent)

Who benefits if this claim is believed? This is useful context for a reader — it explains *why* a claim might be pushed even if it's true, or why it might be fabricated even if it's plausible — but evidence can rarely establish someone's actual intent, so keep this strictly descriptive.

For each source repeating or originating the claim, note where relevant:
- **Financial** — ad revenue tied to engagement/outrage, a product or service the claim promotes, a stock position or financial interest
- **Political** — does the claim favor a specific candidate, party, or policy outcome the source is aligned with
- **Reputational** — does believing the claim vindicate or discredit someone the source has an existing stance on

Phrase findings as exposure of a relationship, not an accusation of motive:
- Write: "Outlet X has a financial relationship with the product mentioned in the claim."
- Not: "Outlet X fabricated this claim to profit from it."

An incentive existing is not evidence the claim is false — plenty of true claims also benefit someone. Report it as one more piece of context alongside the Step 6 verdict, never as a factor that changes the verdict itself. Only include this step when the user asks who benefits/who's behind something, or when a Step 4 credibility check already surfaced a clear conflict of interest worth naming.

## Final step — Red-team your own verdict before delivering it

Every step above pushes toward a conclusion. This one pushes back, and it happens before you write the answer, not after.

For the verdict you've arrived at, deliberately argue the opposite case:
- **What's the strongest version of the other conclusion?** If you landed on False, what would have to be true for the claim to be accurate — and did you actually check that, or just not find it?
- **Is any link in the chain load-bearing and weak?** Verdicts often rest on one source, one timestamp, one translation. Name that dependency instead of letting it hide inside a confident summary.
- **Did search shape the result?** If your queries presupposed the answer ("X debunked"), you'd find supporting results whether or not they're representative. Check whether a neutral phrasing returns a different picture.
- **Is the confidence tier actually earned?** Downgrade Confirmed to Likely, or False to Unverified, if the red-team pass exposes a gap. Downgrading after this check is the system working, not a failure.
- **Would this verdict survive the subject of the claim reading it?** Not "would they like it" — would they be able to point to a factual error or an unfair characterization.

If the opposing case survives this scrutiny, the verdict needs to change or soften. Say so in the output rather than quietly adjusting — noting "an earlier read suggested X; the fuller record doesn't support it" is more trustworthy than a verdict that arrives looking inevitable.

## Output format

Structure findings as a per-claim forensic breakdown, since that's what lets someone act on it rather than just read a verdict:

```
## Claim: <the specific assertion, quoted or closely paraphrased>
**Verdict:** Confirmed / Partially true / Unverified / False / Out of context
**What the evidence shows:** <2-4 sentences, plain language>
**Primary source:** <link/citation to the earliest verifiable source, or "none found">
**Distortion, if any:** <which pattern from Step 5 applies, if any>
```

After all claims, add a short **Overall assessment** — one or two sentences on whether the piece as a whole is trustworthy, misleading-but-not-false, or fabricated, and why. Don't bury this at the top; let the per-claim evidence come first so the conclusion is earned rather than asserted.

For a single simple claim (one fact, one quote), skip the multi-claim structure and just give the verdict, evidence, and source inline in prose — the full template is for multi-claim pieces (articles, posts, screenshots with several assertions).

## Handling media forensics specifically

When checking an image or video:
- Reverse image search for earliest appearance and original context
- Check for inconsistent shadows/lighting, mismatched reflections, warped edges (signs of editing) — but hold this to a lower confidence than provenance checks, since visual inspection alone is easy to get wrong
- Check metadata if available (though it's easy to strip or fake, so treat it as corroborating, not conclusive)
- State plainly when you cannot determine authenticity from available tools, rather than guessing from visual impression alone

### On AI-generated / synthetic media

Be direct about the limits here: you cannot reliably determine whether an image, video, or audio clip was AI-generated by looking at it, and neither can most detection tools — their accuracy is poor, degrades with every model generation, and produces confident errors in both directions. Claiming something "shows signs of AI generation" based on visual impression is a guess dressed as analysis, and a false accusation of fakery does real damage.

What to do instead — shift from pixels to provenance:
- Does the media have a traceable origin? Who first posted it, when, and does that account have any prior existence and connection to the claimed event?
- Does any independent source document the same event (other angles, other photographers, local reporting, official records)? Genuine newsworthy events usually leave more than one trace; synthetic ones often have exactly one.
- Is there C2PA/content-credential metadata, or a camera-original file available from the poster?
- The classic tells (hands, text, garbled background detail) are worth noting only as weak corroboration, never as the basis of a verdict — current models frequently don't produce them.

If provenance can't be established either way, report it as **Unverified** with the "what would settle it" guidance from Step 6 — not as "likely AI."

## Copyright and quoting

Follow standard citation limits: paraphrase what a source says rather than reproducing it at length, and keep any direct quotation short and attributed. The forensic value is in verifying and explaining what a source shows, not in reproducing it.

## Worked examples

See `references/verdict-examples.md` for three full walkthroughs (a statistic claim, a quote+photo provenance case, and a combined framing/exposure check) showing how the steps above compose in practice.
