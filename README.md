# Cybersecurity Program Library

An audit-style CISO/ISSO security program for a composite "Reference Enterprise"
(about 2,500 staff, greenfield, PII/PHI/PCI data, with an inactive federal/CUI track).
I am building it phase by phase with approval gates, the way a program would be
stood up in a real organization. No employer, client or personal data is used.

This repository shows the method and selected deliverables. The full working set is
private.

## Approach

- **One authoritative control library.** NIST SP 800-53 Rev. 5 is the single control
  catalog. NIST CSF 2.0, ISO/IEC 27001:2022, CIS Controls v8.1 and NIST SP 800-171
  Rev. 3 all map inward to it, so one requirement never appears three times with three
  different deadlines.
- **Gated phases.** Applicability and scoping come first (what applies, on what
  trigger, and what is out of scope and why), then the control library, then the
  policy and system packages that cite it.
- **Truth rules.** Documents never claim a control is implemented, evidenced or
  effective. Gaps carry visible markers and go to a POA&M.
- **Source-verified crosswalks.** Every framework mapping is generated from the
  publisher's own crosswalk (NIST OSCAL content, the NIST CSF 2.0 Reference Tool, NIST's
  OLIR crosswalk to ISO/IEC 27001:2022, and CIS's mapping to SP 800-53), not from memory.

## Phases

| Phase | Deliverable | State |
|---|---|---|
| 0 | Engagement charter and organization profile | Complete |
| 1 | Applicability, Scoping and Framework Selection Register | Complete (draft for Gate 1) |
| 2 | CSF profile, BIA, threat profile, risk register, roadmap | Planned |
| 3 | Unified Control Library: 18 Moderate-baseline families, 177 controls | Complete (draft for Gate 3) |
| 4-9 | Document register, CISO and ISSO packages, overlays, readiness, QA reviews | Planned |

## What is here

- [`deliverables/Phase1_Applicability_Scoping_Register.pdf`](deliverables/Phase1_Applicability_Scoping_Register.pdf):
  the Phase 1 register.
- [`deliverables/Phase3_Unified_Control_Library_excerpt.pdf`](deliverables/Phase3_Unified_Control_Library_excerpt.pdf):
  front matter, mapping method and verification results, the Access Control family,
  Gate 3 decisions and the mentor note.
- [`sample/`](sample/): the Access Control family as structured data (YAML) and a
  summary table, the format the documents are generated from.

## What verification found

The control records were drafted with help from an AI lab I built
([Multi-Agent Research Lab](https://github.com/sbsmith340/multi-agent-research-lab))
and then checked against the published crosswalks. Across all 177 controls:

| Framework | Drafted links confirmed | Removed as unsupported | Added from the source |
|---|---|---|---|
| NIST CSF 2.0 | 104 | 49 | 461 |
| ISO/IEC 27001:2022 Annex A | 108 | 59 | 248 |
| CIS Controls v8.1 | 68 | 40 | 187 |

The takeaway I apply in practice: crosswalks are only as good as their source. Treat
any mapping that cannot be traced to the publisher as unverified, whoever wrote it.

## Notes

Framework identifiers are cited; no standard text is reproduced. CIS Controls content
is used under CIS's license, and only safeguard identifiers appear here. Mappings
express relationships, not equivalence.
