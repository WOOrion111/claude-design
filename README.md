# claude-design

Marketplace personale di skill di **design, taste e UI/UX** per Claude (Claude.ai, app desktop e Claude Code).

Ogni plugin punta al repository originale dell'autore: non c'è nulla da sincronizzare a mano, gli aggiornamenti upstream arrivano quando Claude aggiorna i plugin.

## Plugin

| Plugin | Upstream | Cosa fa |
|---|---|---|
| `impeccable` | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Quality floor e 24 comandi `/impeccable ...` per il frontend |
| `make-interfaces-feel-better` | [jakubkrehel/make-interfaces-feel-better](https://github.com/jakubkrehel/make-interfaces-feel-better) | Dettagli di design engineering (raggi, ombre, hit area, motion restraint) |
| `transitions-dev` | [jakubantalik/transitions.dev](https://github.com/jakubantalik/transitions.dev) | Transizioni CSS con motion token + `transitions-polish` + `transitions-ui-generation` |
| `gsap-skills` | [greensock/gsap-skills](https://github.com/greensock/gsap-skills) | 8 skill ufficiali GSAP (core, timeline, ScrollTrigger, plugin, utils, React, framework, performance) |
| `hallmark` | [Nutlope/hallmark](https://github.com/Nutlope/hallmark) | Anti-slop web design per pagine nuove, `/hallmark redesign`, `/hallmark audit` |
| `diagram-design` | [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design) | Diagrammi brandizzati HTML/SVG/PNG, import drawio/Mermaid/excalidraw |

## Installazione

**Claude.ai / app desktop**
Customize → Plugins → Add → Add marketplace → *Add from a repository* → `WOOrion111/claude-design`, poi installa i plugin che vuoi. I plugin installati si sincronizzano anche in Claude Code (stesso account, v2.1.273+).

**Claude Code (da terminale)**
```bash
claude plugin marketplace add WOOrion111/claude-design
claude plugin install impeccable@claude-design
claude plugin install make-interfaces-feel-better@claude-design
claude plugin install transitions-dev@claude-design
claude plugin install gsap-skills@claude-design
claude plugin install hallmark@claude-design
claude plugin install diagram-design@claude-design
```

## Aggiungere un plugin

Aggiungi una voce in `.claude-plugin/marketplace.json`:

- repo che è già un plugin (ha `.claude-plugin/plugin.json`) → `"source": { "source": "github", "repo": "owner/repo" }`
- repo con solo `skills/<nome>/SKILL.md` → stessa cosa, più `"skills": "./skills/"`
- sottocartella di un repo → `"source": { "source": "git-subdir", "url": "owner/repo", "path": "cartella" }`, con `"skills": "./"` se le skill sono direttamente lì dentro

Poi `claude plugin validate .` prima di fare push.

## Licenze

Ogni skill resta sotto la licenza del suo repository originale; questo marketplace contiene solo i riferimenti.
