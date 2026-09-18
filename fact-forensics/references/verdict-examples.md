# Worked Examples

Three end-to-end walkthroughs showing how the pipeline in SKILL.md applies in practice. Use these as a template for structure and tone, not as content to copy — every real case needs its own search and evidence.

---

## Example 1 — A statistic in a shared post

**Input:** A post claims "Youth unemployment has doubled since last year."

**Step 1 (claim extraction):** One checkable claim: youth unemployment rate, this year vs. last year, doubled.

**Step 3 (trace to origin):** Search for the national statistics agency's release covering both periods, not a news aggregator's restatement.

**Step 4 (credibility):** Statistics office = high-reliability primary source. If only a partisan blog is citing "government data" without a link, that's a lower tier — flag it and keep looking for the primary release.

**Step 5 (distortion check):** Classic denominator problem — check the actual percentage-point change, not just the ratio. "Doubled" from 2% to 4% reads very differently in a headline than it does as raw numbers, even though both are literally accurate.

**Step 6 (verdict):**
```
## Claim: Youth unemployment has doubled since last year
**Verdict:** Partially true / missing context
**What the evidence shows:** The rate did rise from 2.1% to 4.3% over the period — arithmetically "doubled," but starting from a historically low base, and still below the 5-year average.
**Primary source:** [national statistics office release]
**Distortion, if any:** Numbers-without-baseline — true ratio, misleading absolute-scale impression
```

No Step 2, 7, or 8 needed here — nothing in the post signals partisan framing or viral spread that the user asked about.

---

## Example 2 — A quote + photo pairing, with a provenance question

**Input:** A screenshot shows a quote attributed to a public figure alongside a dramatic photo, both allegedly from "last week."

**Step 1:** Two claims bundled: (a) the quote's authenticity/completeness, (b) the photo's date and context.

**Step 3:**
- Quote: locate the original recording/transcript. Check the sentence(s) immediately surrounding the quoted line for a reversal-by-trimming pattern (Step 5 distortion check).
- Photo: reverse-image-search. Suppose it turns up on a stock/news archive from three years earlier — that's a verified, hard-to-fake timestamp (archive metadata), which outweighs the screenshot's own displayed "last week" caption.

**Provenance reasoning (Step 3 sub-section):** The screenshot's caption is *not* independent evidence of date — it's the same claim being dated, not a check on it. The archive listing is independent and predates the screenshot by years, so it wins. State this as Confirmed, not Likely, since it's a hard-to-fake source with no contradicting evidence found.

**Step 6 (verdict):**
```
## Claim: Photo shows a recent event
**Verdict:** Out of context
**What the evidence shows:** Reverse image search traces this photo to a news archive dated three years prior to an unrelated event. No evidence it depicts anything from "last week."
**Primary source:** [archive listing with original date]
**Distortion, if any:** Real media, wrong context

## Claim: Quote as presented
**Verdict:** False (as characterized)
**What the evidence shows:** The full transcript shows the quoted sentence is immediately followed by a qualifying clause omitted from the screenshot, which reverses its apparent meaning.
**Primary source:** [original transcript/recording]
**Distortion, if any:** Quote trimmed to reverse meaning
```

---

## Example 3 — A viral claim, checked for spread and framing

**Input:** User asks "how far has this claim actually spread, and is the coverage slanted?"

This is the case where Steps 6 and 7 both apply, in addition to the base verdict.

**Step 6 (base verdict):** Say the core claim checks out as Confirmed against a primary source.

**Step 7 (framing):** Coverage on one side uses "leaked" and quotes only anonymous critics; coverage on the other uses "released" and quotes only an official spokesperson. Both are covering the same confirmed fact, framed to imply different things about legitimacy.
```
## Framing check
**Rightward-leaning indicators:** none found in the sample checked
**Leftward-leaning indicators:** "leaked," exclusively critical anonymous sourcing in outlet A
**Compared against:** outlet B's neutral-wire-style version, outlet C's official-source version
**Assessment:** Underlying fact confirmed by all three; outlet A's framing implies impropriety the confirmed facts don't establish.
```
(Note this example could equally have gone the other direction — the point is checking both, not assuming one.)

**Step 8 (exposure):**
```
## Exposure check
**Total mentions found:** 63
**Independent origins:** 4
**Redundancy ratio:** ~16 — highly redundant: most reposts trace to 4 original threads, not 63 independent confirmations
**Reach-weighted exposure:** not computed — follower data unavailable for most accounts
**First seen:** 9 days ago (archive-confirmed)
**Trend:** fading — no new independent origins in the last 3 days
```

The two checks stay in separate blocks. Nothing about the framing bears on the exposure numbers, and nothing about the spread size bears on whether the claim is true.
