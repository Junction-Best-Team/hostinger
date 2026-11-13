# Propaganda / disinformation symptom taxonomy (text-only)

Source of truth: NotebookLM notebook **Propaganda symtopms** (`4acaafe1-83b3-4315-84c5-97635431df75`).
Query date: 2026-11-13. Grounded via `notebooklm ask` against the notebook's six imported sources (SemEval-2020 Task 11 PDF, NLP4IF/arXiv 1910.09982, Sahitaj et al. 2025 HTML, EU DisinfoLab glossary, NAFO techniques guide, First Draft "Fake news. It's complicated.").

Wayfinder ticket: [Extract high-level propaganda symptom taxonomy from NotebookLM](https://github.com/Junction-Best-Team/hostinger/issues/2)

## Families of text-observable propaganda techniques

Recent NLP sources in the notebook (SemEval-2020; Sahitaj et al. 2025) group span-level techniques into **three families**.

### 1. Emotional appeals

| Technique | Meaning | Agreement |
| --- | --- | --- |
| Loaded language | Words/phrases with strong emotional charge to sway perception | Strong across SemEval, Sahitaj, NLP4IF, NAFO |
| Name calling / labeling | Derogatory or praise labels to trigger emotion | Strong |
| Appeal to fear / prejudice | Build support by anxiety, panic, or prejudice | Strong |
| Flag-waving | Appeal to national/group identity to justify a claim | In SemEval/Sahitaj/NLP4IF; weaker as distinct NAFO entry |
| Slogans | Short striking phrases as cognitive/emotional shortcuts | SemEval/Sahitaj; NAFO overlaps "glittering generalities" |

### 2. Simplification and distortion

| Technique | Meaning | Agreement |
| --- | --- | --- |
| Exaggeration or minimization | Overstate threat or downplay significance | Core in SemEval/Sahitaj |
| Causal oversimplification (incl. scapegoating) | Complex events blamed on one cause or target | Broad consensus |
| Black-and-white fallacy | Only two extreme options presented | SemEval/NLP4IF/Sahitaj |
| Thought-terminating clichés | Generic phrases that shut down debate | SemEval/Sahitaj; not in NAFO |
| Repetition | Repeat a claim/phrase to force acceptance | Textual in SemEval; NAFO stresses cross-platform "firehose" |

### 3. Trust, authority, and discourse manipulation

| Technique | Meaning | Agreement |
| --- | --- | --- |
| Doubt | Attack credibility without substantive evidence | SemEval/Sahitaj; related NAFO FUD |
| Appeal to authority | Claim true because an authority (or fake expert) said so | Strong |
| Whataboutism (+ red herring / straw man) | Deflect via hypocrisy charge, misrepresentation, or irrelevance | SemEval/Sahitaj **merge** these; NLP4IF/NAFO keep separate |
| Reductio ad Hitlerum (+ bandwagon) | Discredit via hated association, or "everyone does it" | SemEval/Sahitaj **merge**; NLP4IF/NAFO separate |

## Broader information-disorder concepts (not span techniques)

From First Draft / EU DisinfoLab in the notebook:

- **Misinformation** — false, shared without intent to harm
- **Disinformation** — false, deliberate, to deceive/harm
- **Malinformation** — true info weaponized out of context

First Draft's seven problematic-content types (satire, false connection, misleading, false context, imposter, manipulated, fabricated) describe **content situation**, not local rhetoric spans.

## Needs non-text signals (out of a pure text classifier)

Coordinated inauthentic behaviour / botnets, astroturfing, firehose-of-falsehood across platforms, doppelgänger sites/DNS, and fact verification / card stacking (SemEval excluded techniques needing external comparison).

## 48h honesty / false-positive notes (from notebook)

1. Style ≠ truth: emotional language can be true; calm tone can be fabricated.
2. Legitimate political criticism often looks like loaded language / clichés → high FP risk.
3. Fine-grained fallacies (whataboutism, doubt, straw man) have weak human/model agreement vs surface cues like loaded language.
4. Spans often multi-label / nested — single-label classifiers mislead.

## Practical shortlist for a later build discussion

If a later effort picks **Name the technique**, start with high-agreement surface techniques: **loaded language, name calling/labeling, appeal to fear/prejudice, exaggeration/minimization, appeal to authority, doubt**, plus one merged deflection class (**whataboutism family**). Treat swarm/traffic/provenance as separate lanes needing non-text evidence.
