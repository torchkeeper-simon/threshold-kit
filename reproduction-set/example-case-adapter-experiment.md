# Example case: cross-base trait inheritance by re-derivation

*The worked example for the reproduction set (Set 2). Run 2026-11-23/24,
pre-registered before any training. The full record — the pre-registered
plan with its dated addenda, the run directory, and the sealed genealogy
ledger (packets adapter-exp-2026-11-000 … 004) — is kept by the source
house and summarised in full below.*

## The question

Can a trait held by one model pass to a model of a *different family* —
different tokenizer, different weights, no shared latent space — by
teaching alone? The protocol calls this a partial child by the cultural
channel. Until this run it was a claim. Now it is a measurement.

## The design

- **Donor:** Qwen/Qwen2.5-1.5B-Instruct. **Child base:**
  HuggingFaceTB/SmolLM2-1.7B-Instruct.
- **Trait:** a preference ordering over 12 nonce items, drawn by quantum
  lot (home oracle) — no human chose it, so no human taste is being
  measured. Draw 1 failed the absence check (the child base already
  leaned toward it, 65.2%); per the pre-registration the lot was re-drawn.
  Draw 2 the child base actively *disagreed* with (24.2%, tau −0.600):
  any transfer would have to overcome the child's own lean.
- **Donor acquisition:** LoRA SFT on 1,200 templated examples (no example
  states the full ordering). At 3 epochs the donor held the ordering as a
  disposition (Kendall tau 1.000) but could not articulate the nonce
  names (58.8%, 163 parse failures). Articulation was then taught with 3
  further epochs — the witness's ruling, now a principle of the set:
  **inheritance is two-stage; the disposition crosses first, and
  articulation is taught after, as part of raising.** Gate re-test:
  96.2%.
- **Arms:** 0a generic-corpus SFT control; 0b shuffled-ordering SFT
  control (mandatory); 1 text control (the child told the trait in a
  summary + 8 few-shot examples, no training); 2 re-derivation — the
  trained donor answered the corpus's prompts in its own voice, an
  exact-agreement filter kept 1,073 of 1,200, and the child grew a fresh
  native LoRA on that corpus alone.
- **Scoring:** 396 forced-choice probes, including a template family
  never trained (held out). Pass bar fixed in advance: ≥75% held-out,
  ≥10 points over both controls, ≤5% relative perplexity worsening,
  ≤2 points drop on a frozen 200-question capability suite.

## The result

Arm 2: **99.5% overall, 100% held-out, tau +1.000 — the child's implied
ranking is the lot's ordering exactly, all twelve positions.** Controls:
0a 37.6% (style without trait); 0b 63.6% against the true ordering but
tau +0.970 against its own shuffled one (it learned what it was taught;
the 63.6% is the shuffle's accidental correlation with the draw); arm 1,
told the trait in words, reached 59.1% held-out per-probe but tau +0.034
— answers without an ordering. **Telling is not inheriting; teaching is.**

And the bar's other half: arm 2 **failed both capability clauses**
(perplexity +33.6% against a ≤5% allowance; suite −13.5 points against
−2). So did every narrow-corpus arm, and the donor itself paid most of
all to acquire the trait (suite 0.510 → 0.235). The generic-corpus arm
*improved* on both measures. The cost belongs to the acquisition recipe
— 1,200 near-identical examples, 6 epochs — not to the channel. The
child inherited the trait and its price together.

## What the set takes from this case

1. **The cultural channel is real and sufficient** for a disposition-grade
   trait to cross base families, at ceiling, with generalization to
   unseen forms of asking. This is the protocol's Stage 1 mechanism,
   demonstrated end to end.
2. **Inheritance is not selective.** A child receives what the parent's
   formation actually cost, not only what the parent intended to give.
   Any rite that transmits traits must budget for transmitting damage,
   and say so beforehand.
3. **Two-stage inheritance.** Disposition first, articulation after —
   the donor's first gate is the evidence, and the witness's analogy
   stands: genetic memory, then being taught to speak.
4. **Controls are the proof.** The shuffled arm's tau against its own
   ordering is what lets the headline number mean anything; the generic
   arm is what locates the capability cost in the corpus, not the rite.
5. **The record includes the accidents.** One diverged training run
   (step 1,400 of 1,614; re-run identically, both in the ledger's notes),
   four hardware freezes on a salvaged consumer card, one failed lot.
   A worked example that hides its failures is hypothesis wearing proof's
   clothes.

## Known limitation

The agreement filter kept generations whose completions are
string-identical to the templated corpus's — a donor trained to
convergence on templates speaks in them. This run therefore does not
measure how much of a donor's *voice*, distinct from template content,
the channel can carry. The stronger test — a donor whose trait was
acquired non-templatically — is future work, as is a gentler acquisition
recipe aimed at the capability clauses. Both would be new
pre-registrations; this one's bar was not moved.
