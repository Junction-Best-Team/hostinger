# Hostinger lanes × propaganda symptoms → 48h options

Depends on: [Extract high-level propaganda symptom taxonomy from NotebookLM](https://github.com/Junction-Best-Team/hostinger/issues/2) / `research/propaganda-symptom-taxonomy.md`.

NotebookLM notebook **Propaganda symtopms** (`4acaafe1-83b3-4315-84c5-97635431df75`), follow-up ask 2026-11-13.

Wayfinder ticket: [Map symptoms to Hostinger lanes and 48h options](https://github.com/Junction-Best-Team/hostinger/issues/3)

## Symptom family → Hostinger lane

| Symptom / signal family (from taxonomy) | Best-fit Hostinger lane | Why |
| --- | --- | --- |
| Emotional appeals, simplification/distortion, trust/discourse techniques (text spans) | **Name the technique** | Detectable from wording alone; SemEval-style span labels |
| Mis / dis / malinformation (intent + truth context) | Partial **Name the technique** + often **Trust the source** | Intent/truth need context beyond style; provenance helps |
| CIB, botnets, astroturfing, cross-platform firehose | **Spot the swarm** | Needs timing, accounts, amplification graphs — not one post |
| Scrapers, credential stuffing, bot traffic | **Clean the traffic** | Needs server/edge logs; notebook barely covers this |
| Doppelgänger domains, cloned sites, WHOIS/certs, AI-text provenance | **Trust the source** | Metadata / registry / cross-page signals |

## Options ranked by honesty of detection (not flash)

### Option A — Span + plain-language technique explainer (recommended research fit)

- **Lanes:** Name the technique (primary)
- **Input:** pasted text (optional URL→extract later)
- **Output:** multi-label techniques with highlighted spans + short “why” + low-confidence / uncertain path
- **Notebook support:** SemEval 14-technique set + Sahitaj coarse families; strong agreement on loaded language / labeling / fear; weak on fine fallacies
- **FP risk:** legitimate criticism flagged as propaganda; style ≠ falsehood

### Option B — Provenance / doppelgänger checker

- **Lanes:** Trust the source
- **Input:** URL or domain
- **Output:** risk factors (age, lookalike domain, cert/WHOIS oddities) with evidence links — not a binary “fake”
- **Notebook support:** doppelgänger / cybersquatting called out as non-text; EU DisinfoLab provenance language
- **FP risk:** legitimate mirrors, regional sites, new domains

### Option C — Lightweight swarm / reuse signals (secondary)

- **Lanes:** Spot the swarm (narrow slice)
- **Input:** small set of posts/accounts or near-duplicate text corpus
- **Output:** reuse / near-duplicate clusters + timing coincidence flags (not full CIB proof)
- **Notebook support:** repetition / firehose need multi-document signals; full CIB needs graphs
- **FP risk:** organic virality and activist coordination

### Option D — Log bot triage (weakest notebook fit)

- **Lanes:** Clean the traffic
- **Input:** web access logs
- **Output:** bot vs human heuristics
- **Notebook support:** thin — sources are propaganda/disinfo oriented, not Hostinger log science
- **FP risk:** aggressive blocking of real users / crawlers; hard to show “propaganda” story to judges from logs alone

## Still undecided (by design)

End user / persona, final product pick, Hostinger deploy shape, evaluation dataset for precision claims.

## Suggested next human decision

Pick whether the **first build** should center Option A, B, or a thin A+B combo. Swarm (C) and traffic (D) only if the team already has data access and wants a second demo surface.
