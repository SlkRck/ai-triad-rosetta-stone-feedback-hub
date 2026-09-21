# AI Rosetta Stone — Feedback Hub

A central place for participants to (1) learn how to use the **AI Rosetta Stone**,
(2) launch the tool, and (3) submit structured feedback that lands in GitHub for
the tool's creator.

## What's here

```
docs/
  index.html            ← the hub (GitHub Pages serves this)
  images/               ← UI screenshots (drop yours in; placeholders show until then)
  FEEDBACK-SUMMARY.md   ← auto-generated weekly by a workflow (created on first run)
.github/
  ISSUE_TEMPLATE/
    feedback.yml        ← structured feedback issue form
  workflows/
    deploy-pages.yml    ← auto-publish docs/ to GitHub Pages
    label-and-notify.yml← auto-label new feedback + optional Teams/Slack ping
    feedback-digest.yml ← weekly rolling FEEDBACK-SUMMARY.md
USER-MANUAL.md          ← the manual as standalone Markdown
index.html              ← original standalone (offline) feedback app; superseded by docs/index.html
```

## How feedback flows

Both entry points end up as **GitHub Issues** labeled `feedback`:

- **Public path:** anyone opens the Pages URL, fills the form, clicks **Post to
  GitHub** → a pre-filled new-issue page opens → they submit.
- **Boeing/internal path:** give people an internal link that simply points at
  the same Pages URL (or the repo). Most Boeing GitHub accounts can open an
  issue. No account? The hub's **Export** button saves a file to email instead.

On a new issue, `label-and-notify.yml` ensures the `feedback` label and can ping a
webhook. `feedback-digest.yml` compiles open feedback into `docs/FEEDBACK-SUMMARY.md`
weekly. The creator gets email by **Watching** the repo (Custom → Issues).

## Notes & caveats

- **Public repo = public feedback.** Issues are world-readable. PLEASE DO NOT
  paste anything internal/sensitive; crop screenshots accordingly. If any
  feedback must stay private, send to jsnover@gmail.com.
- The hub is a single static file with no dependencies; it also works opened
  directly from disk (`file://`) for a quick local preview, though **Post to
  GitHub** needs the `REPO` value set.
- GitHub ignores a pre-filled `&body` when an issue **template** is forced, so the
  hub links to the plain new-issue page with the body pre-filled. The
  `feedback.yml` template still helps people who start an issue manually.

## The tool being reviewed

- Live app: `https://taxonomy-editor.yellowbush-aeda037d.eastus.azurecontainerapps.io/`
  (use "Browse without an account" for read-only access)
- Framing doc: `jpsnover/ai-triad-research` →
  `research/comp-linguist/analyses/epistemic-infrastructure-framing-concise.md`
