# STATE

## Goal
Create an Architecture Options Paper (from Finalised Templates/PowerPoint/Architecture_Options_Paper_Template.pptx) for accessing the production Siebel database.

## Now
Deck generated and verified; awaiting user review of content/RAG scoring.

## Next
1. User reviews Siebel_Production_Database_Access_Options_Paper.pptx in PowerPoint (check table row heights / text fit).
2. Adjust option content, RAG ratings or add costings as user directs.

## Constraints
<none stated>

## Decisions
DECISION: 4 options — direct prod extract / backup restore to Oracle PaaS in Azure / continuous replication / defer to Nov 2026 — recommendation Option 2, because it adds zero load to fragile prod hardware and rehearses the Azure migration restore path.
DECISION: output pptx placed at repo root alongside other working docs (HLD_CQC.docx etc.).

## Facts
- Context: Siebel prod = Oracle DB managed by Computacenter, aging hardware, load = failure risk; Azure migration due Nov 2026; consumer = Microsoft Fabric; daily freshness suffices; supplier backup-restore-to-Oracle-PaaS option exists.
- Generator script: scratchpad build_siebel_options.py (session scratchpad); rerun with `python build_siebel_options.py` from repo root; requires python-pptx (v1.0.2, installed --break-system-packages).
- python-pptx trap: assigning "\v" to run.text escapes to literal _x000B_ — use separate paragraphs (deepcopy p element) for multi-line cells.

## Done
Options paper generated — RESULT: Siebel_Production_Database_Access_Options_Paper.pptx, all 11 slides populated (title, version, purpose/decision, background, summary table with RAG cell fills, 4 option slides with RAG ovals coloured, next steps); verified by re-opening with python-pptx and dumping content.

## Open items
- Title slide author role left as "[Role / job title]" — user to fill.
- Distribution list (slide 3) names left as [Name] placeholders.
- Cost columns are RAG-only; no £ figures included — add if ARB expects them.

## Failed attempts
<none>
