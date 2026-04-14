# Guild of Systems Weavers

> Systems Weavers are practitioners who connect systems, teams, data, workflows and institutional realities across boundaries where formal ownership is fragmented or absent.

The **Guild of Systems Weavers** is an open, independent professional commons for a neglected but vital kind of cross-boundary infrastructure practitioner.

**Website:** [Guild of Systems Weavers](https://adamvialsmoore.github.io/GuildSysWeavers/) *(GitHub Pages)*

---

## What is this?

Many infrastructure and transformation projects depend on people who can work across technical, organisational, and procedural boundaries. These practitioners are often described informally as "glue people", "plumbers", "Swiss army knives", or "jacks of all trades" — but those labels fail to capture the sophistication of the work.

This guild exists to:

- **Recognise** this cross-boundary practice as a distinct professional discipline
- **Codify** tacit, experience-based knowledge into shared patterns and methods
- **Professionalise** through portable, contribution-led peer recognition

The guild is independent, practice-based, and not tied to any employer, vendor, or methodology. It is a public professional commons for a neglected kind of practitioner.

## What is in this repository

This repository is both the guild's working knowledge commons and the source for its public website.

### Site content (`docs/`)

| Page | Description |
|---|---|
| [Home](docs/index.md) | Overview and introduction |
| [About](docs/about.md) | What is a Systems Weaver? |
| [Manifesto](docs/manifesto.md) | Why this work matters |
| [Charter](docs/charter.md) | Purpose, principles, governance |
| [Code of Practice](docs/code-of-practice.md) | Ethical and professional standards |
| [Competencies](docs/competencies.md) | Competency framework for the craft |
| [Recognition](docs/recognition.md) | Contribution-based recognition pathways |
| [Role Glossary](docs/roles/index.md) | Definitions of terms and labels |
| [Pattern Library](docs/patterns/index.md) | Recurring situations and approaches |
| [Case Studies](docs/case-studies/index.md) | Real-world practice examples |
| [Governance](docs/governance/index.md) | How the guild is run |
| [Join](docs/join.md) | How to participate |

### Patterns

The pattern library documents recurring situations in cross-boundary work:

- [When no single system owns the whole process](docs/patterns/no-single-system-owns-the-process.md)
- [When the data aligns structurally but not semantically](docs/patterns/data-aligns-structurally-not-semantically.md)
- [When the workflow depends on one person's memory](docs/patterns/workflow-depends-on-one-persons-memory.md)
- [When the API exists but the organisation does not](docs/patterns/api-exists-but-organisation-does-not.md)
- [When teams use the same term for different things](docs/patterns/same-term-different-meanings.md)
- [When automation obscures responsibility](docs/patterns/automation-obscures-responsibility.md)
- [When manual work is carrying architectural debt](docs/patterns/manual-work-carrying-architectural-debt.md)
- [When reporting outputs hide broken joins upstream](docs/patterns/reporting-hides-broken-joins.md)

### Templates

- [Pattern template](templates/pattern-template.md) — for contributing new patterns
- [Case study template](templates/case-study-template.md) — for documenting practice examples
- [Member profile template](templates/member-profile-template.md) — for practitioner profiles

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to participate. Contributions of patterns, case studies, glossary terms, and improvements to existing content are welcome.

## Publishing the site

The site is built with [Jekyll](https://jekyllrb.com/) using the Minima theme and published via [GitHub Pages](https://pages.github.com/).

### To enable GitHub Pages

1. Go to **Settings > Pages** in this repository
2. Under **Build and deployment**, set **Source** to "Deploy from a branch"
3. Set **Branch** to `main` and folder to `/docs`
4. Save — the site will be available at `https://adamvialsmoore.github.io/GuildSysWeavers/`

### To preview locally

```bash
cd docs
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/GuildSysWeavers/` in your browser.

## Repository structure

```
.
├── README.md                   # This file
├── CONTRIBUTING.md             # Contribution guide
├── CODE_OF_CONDUCT.md          # Community standards
├── LICENSE                     # Apache 2.0
├── NOTICE                      # Attribution
├── docs/                       # GitHub Pages site (Jekyll)
│   ├── _config.yml             # Jekyll configuration
│   ├── index.md                # Homepage
│   ├── about.md                # About the craft
│   ├── manifesto.md            # Manifesto
│   ├── charter.md              # Guild charter
│   ├── code-of-practice.md     # Code of practice
│   ├── competencies.md         # Competency framework
│   ├── recognition.md          # Recognition pathways
│   ├── join.md                 # How to participate
│   ├── alternative-labels.md   # Alternative names considered
│   ├── roles/
│   │   └── index.md            # Role glossary
│   ├── patterns/
│   │   ├── index.md            # Pattern library index
│   │   └── *.md                # Individual patterns
│   ├── case-studies/
│   │   └── index.md            # Case studies index
│   ├── governance/
│   │   ├── index.md            # Governance overview
│   │   └── decisions.md        # Decision-making model
│   └── assets/
│       └── main.scss           # Custom styles (Minima override)
├── templates/                  # Reusable contribution templates
│   ├── pattern-template.md
│   ├── case-study-template.md
│   └── member-profile-template.md
└── .github/
    ├── PULL_REQUEST_TEMPLATE.md
    └── ISSUE_TEMPLATE/
        ├── new-pattern.yml
        ├── case-study.yml
        ├── glossary-suggestion.yml
        └── governance-suggestion.yml
```

## Licence

Content is published under the [Apache License 2.0](LICENSE). See [NOTICE](NOTICE) for attribution.

## Status

This is a founding-phase project. The initial structure, content, and patterns are a starting point intended to be built upon through community contribution.

---

*We value practical synthesis over silo purity, working systems over ornamental diagrams, and the often invisible craft of keeping complexity connected.*
