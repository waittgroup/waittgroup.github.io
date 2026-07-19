# Research Group Wiki — CLAUDE.md

## Project overview
This repo is a markdown-based wiki/SOP site for waittgroup, a research
group working at the intersection of computational chemistry and taste
science (QM-derived molecular descriptors, ML taste prediction, ORCA /
OSPool-HTC computational workflows). It's deployed as a GitHub Pages site
via MkDocs Material and serves as the group's SOP hub and onboarding
reference for students — same spirit as older org-mode lab wikis (e.g.
Schneider Group), but rendered as a real navigable, searchable site.

## Audience
Primary readers are incoming undergrad/grad researchers, plus the PI.
Assume technical competence, zero prior context on group-specific tools.
Write pages as clear SOPs (numbered steps, code blocks) — not prose essays.

## Tech stack
- Static site generator: MkDocs + Material theme
- Content: Markdown (.md) only
- Deployment: GitHub Actions (`.github/workflows/deploy.yml`) builds and
  publishes to GitHub Pages
- Pages source setting on GitHub: "GitHub Actions" (not a branch)

## Repo structure
```
docs/
  index.md               # Landing page
  people.md              # Team / roster
  research.md            # Research areas & projects
  join.md                # Contact / how to join
  new-member-guide.md    # Onboarding SOP for new students
  sops/
    orca-ospool-workflow.md   # e.g. containerized ORCA on OSPool/HTCondor
    ...                        # one file per SOP/workflow topic
mkdocs.yml
.github/workflows/deploy.yml
```

## Conventions
- One topic per file, kebab-case filenames
- Every SOP page opens with a one-line "what this is for," then numbered steps
- Relative markdown links between pages, not absolute URLs
- Bullet lists / code blocks / tables over long prose
- New SOP files get added to `mkdocs.yml` nav immediately — nothing orphaned

## What NOT to do
- No org-mode syntax
- Don't hardcode content that goes stale (semester dates, etc.) without a
  "last updated" line
- Don't commit large binaries (photos, PDFs) — link to Drive if large
