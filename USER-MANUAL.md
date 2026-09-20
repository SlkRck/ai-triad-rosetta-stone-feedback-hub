# AI Rosetta Stone — User Manual & Feedback Guide

*A practical guide to using the AITriad Taxonomy Editor ("AI Rosetta Stone"),
and to giving its creator feedback that actually helps.*

> Live tool: `https://taxonomy-editor.yellowbush-aeda037d.eastus.azurecontainerapps.io/`
> Framing doc: `jpsnover/ai-triad-research` → `research/comp-linguist/analyses/epistemic-infrastructure-framing-concise.md`

---

## 1. What this tool is (and is not)

The AI Rosetta Stone is **epistemic infrastructure for multi-perspective
AI-policy analysis**. It is not a chatbot and not a search engine.

It does three things:

1. Holds **three fixed worldviews** — *accelerationist, safetyist, skeptic* — as
   structured **BDI taxonomies** (every node tagged **B**elief, **D**esire, or
   **I**ntention).
2. Runs **adversarial debates** between those three perspectives under formal
   rules, with a procedural moderator.
3. Distills debate results into **cruxes** — the single points whose resolution
   would move the most minds.

**The core promise, in the tool's own words:** its output is *structural, not
veridical*. It shows **where** disagreement lives and **what would resolve it** —
not **what is true**. A claim can dominate the argument graph and still be false.

> Keep this front of mind. It changes how you should read everything the tool
> produces.

---

## 2. Who it's for

- Policy analysts, researchers, and strategists working through **contested,
  normative AI questions**.
- People who want to **map an argument** and find its blind spots, not people
  looking up facts.

If your question is "what is X?", this is the wrong instrument. If your question
is "should we do X, and what would change my mind?", it's the right one.

---

## 3. Getting started

| Step | What to do |
|---|---|
| 1 | Open the tool URL. You'll land on a sign-in page. |
| 2 | Choose **"Browse without an account"** to start in **read-only** mode. This is enough to explore the full taxonomy and debate archive. |
| 3 | Only **sign in** (GitHub / Google / Microsoft) when you need to **run a debate** or **propose an edit**. |

**Capabilities by mode**
- *Anonymous:* read-only. Browse taxonomy, debates, cruxes. No AI runs, no writes.
- *Signed in:* can run debates and submit taxonomy edits (via review/PR flow).

---

## 4. How to use it well

**Come with a genuine policy tension, not a fact question.**
The tool shines on contested normative questions ("Should frontier AI
development slow down?"). Vague or purely factual prompts produce activity
without insight.

**Read the taxonomy first, debates second.**
The three-camp taxonomy is the map. Before running a full debate, skim how each
camp frames the same situation — e.g. "AI governance" reads as an *innovation
bottleneck* (accelerationist), *essential gating* (safetyist), or a *capture
risk* (skeptic). That contrast is often the whole insight.

**Treat cruxes as the payoff.**
The most valuable artifact isn't the debate transcript — it's the crux. Use it
as a "go consult the real world here" pointer. That's exactly its intended role.

**Never read "won the argument" as "true."**
Survival in the argument graph ≠ truth. Use the tool to structure your thinking
and surface blind spots, not to settle debates.

**Mind the register.**
When a disagreement turns out to be *definitional* (e.g. "accountability
(market)" vs. "(institutional)" vs. "(algorithmic)"), that's a feature. Lean
into disambiguating rather than arguing past each other.

---

## 5. How to interact with it

- **Phrase inputs as normative/strategic questions** so the BDI decomposition
  has something to work with.
- **Expect a human-in-the-loop editing model.** The taxonomy data embeds its own
  workflow: *edit nodes, open a PR, bump the taxonomy version.* Contributions go
  through review queues, not direct writes.
- **Budget for heavy, slow, rich responses.** This is deep-analysis tooling.
  Individual debate records can be multiple megabytes; the taxonomy per
  perspective is several MB. Interactions are not quick and conversational.
- **Explore edge states patiently.** As an anonymous user you may hit empty
  sections; that doesn't mean the tool is broken.

---

## 6. Quick reference — content you can browse

*(Observed via the read-only anonymous session. Exact availability varies.)*

| Area | What it contains |
|---|---|
| Taxonomy (per perspective) | Structured BDI nodes for accelerationist / safetyist / skeptic |
| Debates archive | Completed and in-progress multi-perspective debates |
| Cruxes | Distilled decision points across the debate corpus |
| Organizations | Profiles of orgs referenced in the discourse |
| Lineage / theory | Topic lineage and background summaries |
| Community library | Shared debates and chat threads |

---

## 7. Troubleshooting

- **"I only see the sign-in page."** The app renders client-side; use a real
  browser. For read-only, click "Browse without an account."
- **A section looks empty.** Some areas are sparse in anonymous mode or not yet
  populated. Try signing in, or check the community library.
- **A confusing error appears.** Note the exact step and message — that's useful
  feedback (see below).

---

## 8. Giving the creator useful feedback

The creator is explicitly trying to learn whether this can become **adopted
infrastructure**. The most valuable feedback is specific, reproducible, and
honest about adoption. Focus on these areas:

**Mental model / onboarding**
- Did the tool successfully reset your "chatbot" expectation *before* first use?
- Did the *structural, not veridical* distinction actually land, or did you still
  read winning claims as "true"?

**Content & empty states**
- Where did you hit empty or confusing sections? At what exact step?

**Trust & provenance**
- Could you trace *why* a claim or number scored the way it did, or did it feel
  like a black box?

**Performance & scale**
- Where did the UI stall or feel heavy? On which view?

**Fitness for purpose (the key question)**
- Would you actually adopt this into a real workflow?
- What is the **single biggest thing** blocking that?

**How to package it**
1. One clear statement: did it change how you think about a real question?
2. 3–5 concrete friction points, each with the exact step where it occurred.
3. An honest **adopt / not-adopt** verdict with the top blocker.

Specific, reproducible observations beat general impressions every time.

**Submitting your feedback (in the app)**
The feedback app can either export a file or submit directly:
- **Rosetta Stone community endpoint** — POSTs to the tool's own
  `/api/community/submit` (payload `{type, data, note}`, the shape the app itself
  uses). You need an active session in the same browser (open the tool and choose
  "Browse without an account" or sign in) for it to be accepted.
- **Custom webhook / form service** — paste any HTTPS endpoint (Power Automate,
  a Forms connector, Slack, etc.) and the app POSTs JSON containing both a
  Markdown rendering and the structured feedback object.

If a direct submit fails (network, CORS, or session), your answers are never
lost — the app tells you and you can fall back to **Export Markdown/JSON**.

---

*This manual was assembled from the tool's public framing document and hands-on
exploration of its read-only interface. It reflects observed behavior, which may
change as the tool evolves.*
