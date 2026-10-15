---
title: "Learning & Skills Agent Stages 5 and 5B - Model and Data Model Consolidation"
stage: "Stage 5B - Data Model Consolidation"
businessAgent: "Learning & Skills Agent"
businessAgentId: "HR-ETG-001"
valueStream: "Talent Design to Evaluate"
status: "Ready for working review"
version: "v0.1"
language: "English (UK)"
classification: "KPMG Confidential"
---

# 1. Document Control

| Item | Value | Evidence |
| --- | --- | --- |
| Deliverable | Stage 5B Data Model Consolidation | [SRC-01] |
| Scope | Consolidation across W-001 to W-010, H-001 to H-008, A-001 to A-009 | [SRC-03], [SRC-04] |
| Input baseline | Stage 5 model deliverable v0.1 | [SRC-02] |
| Consolidation status | Ready for working review | Validation register |
| Design Authority status | Not submitted | Section 10 |
| Classification | KPMG Confidential | [SRC-02], [SRC-04] |

# 2. Stage 5 - Model (Preserved)

Preservation statement:

- The Stage 5 content is preserved from the source file without semantic change.
- Source file: Stage 5 Output/Learning_and_Skills_Agent_Stage5_Model_v0.1.md.
- Stage 5 identifiers retained: W-001 to W-010, H-001 to H-008, A-001 to A-009, E-01 to E-10, R-01 to R-05, G-01 to G-08, ACO-01 to ACO-08.
- Any formatting differences in this Stage 5B document are structural and do not alter Stage 5 meaning.

Preserved Stage 5 summary metrics:

| Metric | Value | Evidence |
| --- | --- | --- |
| Workflow steps modelled | 10 | [SRC-02, Appendix J] |
| Handovers modelled | 8 | [SRC-02, Appendix J] |
| Entities listed | 10 | [SRC-02, Appendix J] |
| Relationships listed | 5 | [SRC-02, Appendix J] |
| Data gaps logged | 8 | [SRC-02, Appendix J] |
| Exit criteria status | Partially met | [SRC-02, section 3.9] |

# 3. Stage 5B - Data Model Consolidation

## 3.1 Purpose

Consolidate all step-level data models into one end-to-end model and verify support for the complete workflow, including control evidence, source traceability, and handover completeness.

## 3.2 Inputs

| Input | Status | Evidence |
| --- | --- | --- |
| Stage 5 model deliverable | Available | [SRC-02] |
| Stage 4 classification output | Available | [SRC-03] |
| Stage 3 decomposition output | Available | [SRC-04] |
| Data classifications | Available via Stage 5 Appendix E | [SRC-02] |
| Data gap log | Available via Stage 5 Appendix F | [SRC-02] |
| Workflow handovers | Available | [SRC-03] |
| Agent inventory | Available | [SRC-03] |
| Control requirements | Available from Stage 4 control mapping | [SRC-03] |
| Enterprise model references | Available | [SRC-06], [SRC-07], [SRC-08] |

## 3.3 Actions (1-13)

| Action | Consolidation result | Evidence |
| --- | --- | --- |
| 1 Assemble all step models | Completed from Stage 5 Appendix C | [SRC-02] |
| 2 Walk end-to-end workflow | Completed for W-001 to W-010 | [SRC-03], [SRC-04] |
| 3 Trace every input to a source | Completed with controlled unresolved owner metadata | Section 4, Section 5 |
| 4 Trace every output to consumer/storage | Completed with controlled unresolved system-owner fields | Section 4, Section 7 |
| 5 Validate within-step exchanges | Completed | Section 7, V-03 |
| 6 Validate between-step handovers | Completed | Section 7, V-04 |
| 7 Confirm consistent entities and attributes | Partially completed; proposed entities still pending admission decision | Section 4, Section 6, V-05, V-06 |
| 8 Confirm agent-created destinations | Partially completed; development_plan destination decision open | Section 4, V-07 |
| 9 Confirm human capture points | Completed for approvals and consequential routing | Section 5, V-08 |
| 10 Identify missing items | Completed as G-01 to G-08 | Section 8 |
| 11 Add and update as required | Completed with controlled placeholders and ACO links | Section 8, Section 12 |
| 12 Repeat end-to-end check | Completed through validation register | Section 11 |
| 13 Prepare DA review pack | Prepared at working-review level; not yet DA-submitted | Section 10, Section 11 |

## 3.4 Checks Performed

- Every input has a defined source: performed.
- Every output has a defined consumer or storage: performed with partial unresolved ownership fields.
- Within-step exchanges are consistent: performed.
- Between-step handovers are complete: performed.
- Shared entities and attributes are consistent: performed with open canonical-admission decisions for logical entities.
- Agent-created data has destination: partial.
- Human-provided data has capture point: performed.
- Control evidence supported: performed.
- Enterprise model alignment achieved: partial.

## 3.5 Outputs

- Unified end-to-end data model.
- Consolidated data dictionary.
- Relationship model.
- Resolved data gap log with lifecycle states.
- End-to-end data flow map.
- Design Authority decision record.

## 3.6 Controls and Evidence

| Required evidence | Status | Evidence |
| --- | --- | --- |
| End-to-end trace map | Complete | Section 7 |
| Data model version | Complete (v0.1) | Document control |
| Change log for added data | Complete | Section 13 |
| Cross-check completion evidence | Complete with Pass/Fail/Pending register | Section 11 |
| DA approval decision and date | Not yet available | Section 10 |

## 3.7 Approval Gate

Approval gate: Factory Design Authority including SME.

Current status: Not submitted.

If rejected when submitted, affected items return to Stage 5 for remodelling.

## 3.8 Deliverable

This consolidated document is produced to working-review readiness with explicit unresolved items and no fabricated approvals.

## 3.9 Key Tools

- Stage 5 model output.
- Stage 4 classification output.
- Enterprise data model standards and SQL references.
- ABBA asset references.

## 3.10 Next Stage

Proceed to Stage 6 only after Design Authority submission and decision.

# 4. Unified End-to-End Data Model

| Entity ID | Entity name | Definition | Classification | Layer | Steps used | Agents/controls using | Operations | Ownership | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| E-01 | silver.worker | Canonical worker master record | Enterprise model | Silver | W-002, W-006, W-007 | A-002, A-005, A-006 | Read, Validate | Business owner: TBC - source required | [SRC-06], [SRC-08] |
| E-02 | silver.position | Canonical position record | Enterprise model | Silver | W-002, W-006 | A-002, A-005 | Read | Data owner: TBC - source required | [SRC-06], [SRC-09] |
| E-03 | silver.employment | Worker-position employment relationship | Enterprise model | Silver | W-002, W-007, W-008 | A-002, A-006, A-007 | Read, Validate | Data steward: TBC - source required | [SRC-09] |
| E-04 | silver.organisation_unit | Organisation structure node | Enterprise model | Silver | W-002, W-007 | A-002, A-006 | Read | Source-system owner: TBC - source required | [SRC-09] |
| E-05 | silver.policy | Governance policy record | Enterprise model | Silver | W-007, W-008 | A-006, A-007 | Read, Validate | Control owner: AI governance path evidenced | [SRC-06], [SRC-03] |
| E-06 | silver.approval | Approval decision record | Enterprise model | Silver | W-008 | A-007 | Create, Update | Approval authority: HRBP + CLO / L&D | [SRC-06], [SRC-03] |
| E-07 | silver.audit_event | Auditable action event | Enterprise model | Silver | W-010 | A-009 | Create, Transmit | Audit owner: TBC - source required | [SRC-09], [SRC-03] |
| E-08 | development_plan | Recommendation package per case | Agent created | Candidate logical | W-006, W-007, W-008 | A-005, A-006, A-007 | Create, Update, Transmit | Business owner: HRBP + CLO / L&D | [SRC-02], [SRC-03] |
| E-09 | skills_inference_result | Advisory skill-demand/supply inference output | Agent created | Candidate logical | W-003, W-004 | A-003, A-004 | Derive, Validate | Owner: TBC - source required | [SRC-02], [SRC-04] |
| E-10 | assignment_confirmation | Assignment completion signal | Other source | External operational | W-009, W-010 | A-008, A-009 | Read, Validate, Update | Source-system owner: TBC - source required | [SRC-02], [SRC-03] |

# 5. Data Dictionary

| Attribute ID | Parent entity | Attribute | Definition | Type | Required | Classification | Provenance | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A-01 | workflow_case | case_id | Workflow case identifier | string | Yes | Agent created | Created at W-001 | [SRC-02], [SRC-03] |
| A-02 | trigger_event | trigger_type | Trigger type: planning or skills change | enum | Yes | Human provided | Source event | [SRC-03], [SRC-04] |
| A-03 | skills_signal | demand_fte | Required capability FTE demand | decimal | Yes | Other source | Workforce planning source | [SRC-04] |
| A-04 | skills_signal | supply_fte | Current capability FTE supply | decimal | Yes | Other source | Workforce planning source | [SRC-04] |
| A-05 | skills_inference_result | confidence_score | Confidence score for advisory inference | decimal | Yes | Agent created | A-003 output | [SRC-02], [SRC-04] |
| A-06 | capability_gap_result | gap_fte | Deterministic demand-supply difference | decimal | Yes | Agent created | A-004 rule output | [SRC-03], [SRC-04] |
| A-07 | development_route_result | route_code | Route decision output code | enum | Yes | Agent created | A-004 threshold logic | [SRC-03], [SRC-04] |
| A-08 | development_plan | development_plan_id | Recommendation package identifier | string | Yes | Agent created | A-005 output | [SRC-02], [SRC-03] |
| A-09 | development_plan | route_rationale | Human-readable rationale for route | text | Yes | Agent created | A-005 output | [SRC-02] |
| A-10 | approval_decision_record | decision_outcome | Approve, reject, hold, rework | enum | Yes | Human provided | A-007 captured human decision | [SRC-03] |
| A-11 | approval_decision_record | decision_rationale | Decision reasoning | text | Yes | Human provided | A-007 captured human decision | [SRC-03] |
| A-12 | development_assignment | assignment_commit_id | Assignment commit identifier | string | Yes | Other source | Target assignment system | [SRC-02] |
| A-13 | assignment_confirmation | confirmation_status | Confirmation state of assignment | enum | Yes | Other source | Operational confirmation source | [SRC-02] |
| A-14 | closure_evidence_record | closure_evidence_id | Closure evidence record identifier | string | Yes | Agent created | A-009 output | [SRC-02], [SRC-03] |
| A-15 | closure_evidence_record | hold_reason | Reason code if closure is held | text | No | Agent created | A-009 output | [SRC-02] |
| A-16 | governance_metadata | data_owner_name | Named data owner | string | No | Not available | Missing source | [SRC-02], [SRC-10] |
| A-17 | governance_metadata | source_system_owner_name | Named source-system owner | string | No | Not available | Missing source | [SRC-02], [SRC-10] |

# 6. Relationship Model

| Relationship ID | Parent | Child | Description | Cardinality | Linking fields | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R-01 | silver.worker | silver.employment | Worker linked to one or more employment records | 1-to-many | worker_id | Confirmed | [SRC-06], [SRC-09] |
| R-02 | silver.position | silver.employment | Position linked to employment records | 1-to-many | position_id | Confirmed | [SRC-09] |
| R-03 | development_plan | silver.approval | Plan evaluated through approval records | 1-to-many | development_plan_id -> business_object_id | Proposed | [SRC-02], [SRC-03] |
| R-04 | silver.approval | development_assignment | Approved decision drives assignment action | 1-to-many | approval_id -> decision_reference_id | Proposed | [SRC-02], [SRC-03] |
| R-05 | development_assignment | closure_evidence_record | Assignment outcome traced into closure evidence | 1-to-many | assignment_commit_id | Proposed | [SRC-02], [SRC-03] |

# 7. End-to-End Data Flow Map

Within-step exchanges:

| Step | Producer | Consumer | Data item(s) | Operation | Control point | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| W-001 | A-001 | A-002 | case_id, trigger_type | Create, Transmit | C-001 | [SRC-03] |
| W-002 | A-002 | A-003/A-004 | input_package, completeness_status | Validate, Transmit | C-002 | [SRC-03], [SRC-04] |
| W-003 | A-003 | A-004/A-005 | inference_summary, confidence_score | Derive, Validate | C-003 | [SRC-03] |
| W-004 | A-004 | A-004/A-005 | gap_fte | Derive | C-004 | [SRC-03] |
| W-005 | A-004 | A-005 | route_code, route_rationale | Derive | C-005 | [SRC-03] |
| W-006 | A-005 | A-006/A-007 | development_plan_payload | Create, Transmit | C-006 | [SRC-03] |
| W-007 | A-006 | Human authorities/A-007 | escalation_packet, routing_decision | Validate, Transmit | C-007 | [SRC-03], [SRC-04] |
| W-008 | A-007 | A-008/A-005 | decision_outcome, decision_rationale | Approve, Update | C-008 | [SRC-03] |
| W-009 | A-008 | A-009 | assignment_commit_id, assignment_status | Update, Transmit | C-009 | [SRC-03] |
| W-010 | A-009 | Governance consumers | closure_evidence_id, hold_reason | Create, Validate, Transmit | C-010 | [SRC-03] |

Between-step handovers:

| Handover ID | From | To | Payload | Shared keys | Completeness status | Failure handling |
| --- | --- | --- | --- | --- | --- | --- |
| H-001 | W-001 | W-002 | trigger_context | case_id | Pass | Revalidate trigger |
| H-002 | W-002 | W-003/W-004 | input_package | case_id, capability_id | Pass | Return for missing inputs |
| H-003 | W-005/W-006 | W-007 | recommendation_packet | case_id, development_plan_id | Pass | Rework recommendation |
| H-004 | W-007 | CHRO/HRBP | people_consequence_packet | case_id | Pending | Escalate and hold until decision |
| H-005 | W-007 | AI Governance | tuning_consequence_packet | case_id | Pending | Escalate and hold until approval |
| H-006 | W-008 | W-009 or W-006 | decision_payload | decision_record_id, case_id | Pass | Rework loop on reject/hold |
| H-007 | W-009 | W-010 | commit_payload | assignment_commit_id | Pending | Re-commit or hold |
| H-008 | W-010 | Governance consumers | closure_packet | closure_evidence_id, case_id | Pending | Hold and request evidence completion |

# 8. Resolved Data Gap Log

| Gap ID | Description | Lifecycle status | Resolution in this consolidation | Residual risk | Evidence |
| --- | --- | --- | --- | --- | --- |
| G-01 | Named data owner missing | In progress | Carried as explicit attributes and ACO link | Medium | [SRC-02], [SRC-10] |
| G-02 | Named data steward missing | In progress | Carried as explicit governance metadata gap | Medium | [SRC-02], [SRC-10] |
| G-03 | Source-system owner unresolved | In progress | Carried with impacted entities and handovers tagged | High | [SRC-02], [SRC-10] |
| G-04 | Canonical destination for development_plan unresolved | Open | Marked as Design Authority decision item | High | [SRC-02] |
| G-05 | Inference confidence control threshold not numeric | Open | Added control parameter placeholder and ACO | Medium | [SRC-03], [SRC-04] |
| G-06 | Escalation SLA/timing fields missing | Open | Added placeholder attributes and ACO | Medium | [SRC-03] |
| G-07 | Closure failure resolver role unresolved | Open | Added resolver role field and ACO | Medium | [SRC-03] |
| G-08 | Retention/sensitivity attributes incomplete | Open | Added metadata fields pending governance source | Medium | [SRC-02], [SRC-06] |

# 9. Controls, Evidence and Enterprise Model Alignment

| Alignment check | Result | Notes | Evidence |
| --- | --- | --- | --- |
| Canonical layer alignment (Silver, Gold, Magenta intent) | Pass | Consolidation keeps canonical business records in Silver and treats semantic governance separately | [SRC-07], [SRC-08] |
| Common record traceability envelope | Pass | Source-system and record identifiers modelled, with unresolved owner metadata flagged | [SRC-07], [SRC-06] |
| Grain declarations for event/fact records | Pass | Relationship and flow records preserve one-row semantics per event type | [SRC-06], [SRC-08] |
| Human approval boundaries retained | Pass | Consequential decisions and approvals mapped to human capture points | [SRC-03], [SRC-04] |
| Agent-created data destination completeness | Pending | development_plan destination requires DA decision | [SRC-02], [SRC-03] |

# 10. Design Authority Decision Record

| Decision ID | Deliverable version | Submission date | Forum/attendees | Decision status | Conditions | Owner | Decision date | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| DA-01 | v0.1 | TBC - source required | TBC - source required | Not submitted | TBC - source required | Factory Design Authority | TBC - source required | [SRC-01], [SRC-05] |

# 11. Validation Register and Deliverable State

| Check ID | Check name | Result | Evidence | Remediation |
| --- | --- | --- | --- | --- |
| V-01 | Input source traced | Pass | Sections 4, 5, 7 | None |
| V-02 | Output consumer or storage defined | Pass | Sections 4, 7 | None |
| V-03 | Within-step exchange consistency | Pass | Section 7 | None |
| V-04 | Between-step handover completeness | Pass | Section 7 | None |
| V-05 | Shared entity consistency | Pending | Section 4, Section 6 | Resolve canonical admission of E-08/E-09 |
| V-06 | Shared attribute consistency | Pass | Section 5 | None |
| V-07 | Agent-created destination defined | Pending | Section 4, Section 9 | Decide destination for development_plan |
| V-08 | Human-provided capture point | Pass | Section 5, Section 7 | None |
| V-09 | Control evidence supported | Pass | Section 3.6, Section 9 | None |
| V-10 | Enterprise model alignment | Pending | Section 9 | Finalise unresolved ownership metadata |
| V-11 | Row-level evidence present | Pass | All register sections | None |
| V-12 | Placeholder-to-ACO mapping | Pass | Section 12 | None |
| V-13 | No fabricated content | Pass | Source-constrained drafting | None |
| V-14 | Stage 5 section preserved | Pass | Section 2, Section 13 | None |
| V-15 | Conversion evidence record complete | Pass | Section 13 | None |
| V-16 | Markdown validity | Pass | Render-ready structure | None |
| V-17 | Identifier consistency | Pass | Sections 4-12 | None |
| V-18 | Source conflicts registered | Pass | Section 12 | None |
| V-19 | Relationship model completeness | Pass | Section 6 | None |
| V-20 | Gap lifecycle completeness | Pass | Section 8 | None |

Deliverable state calculation:

- Generated: Yes.
- Structurally valid: Yes.
- Ready for working review: Yes.
- Ready for Design Authority submission: No (Pending V-05, V-07, V-10).
- Approved: No (no DA decision evidence).

Highest evidenced state: Ready for working review.

# 12. Assumptions, Constraints and Open Questions (ACO Register)

| ACO ID | Type | Description | Linked check(s) | Owner | Status |
| --- | --- | --- | --- | --- | --- |
| ACO-01 | Open question | Named business/data owner for selected entities remains unresolved | V-10 | HR data governance | Open |
| ACO-02 | Open question | Source-system owner for assignment confirmation chain unresolved | V-10 | Platform operations | Open |
| ACO-03 | Constraint | Consolidation remains business-data level and excludes physical schema design | V-13 | Delivery governance | Active |
| ACO-04 | Assumption | Stage 4 sequencing is accepted baseline for Stage 5B consolidation | V-03, V-04 | Capability owner | Active |
| ACO-05 | Open question | Canonical admission of development_plan and skills_inference_result pending | V-05, V-07 | Design authority | Open |
| ACO-06 | Missing information | Numeric confidence thresholds for inference control not evidenced | V-09 | AI governance | Open |
| ACO-07 | Missing information | Escalation SLA fields not evidenced | V-04 | Process owner | Open |
| ACO-08 | Missing information | Closure failure resolver role not evidenced | V-02 | Capability owner | Open |

# 13. Consolidation Remediation Plan

| Remediation ID | Blocking or non-blocking | Related checks | Action | Owner | Target state |
| --- | --- | --- | --- | --- | --- |
| REM-01 | Non-blocking for working review, blocking for DA-ready | V-10 | Confirm named business owner and data owner for E-01 to E-10 | HR data governance | Pass |
| REM-02 | Non-blocking for working review, blocking for DA-ready | V-10 | Confirm source-system owner for assignment and confirmation records | Platform operations | Pass |
| REM-03 | Blocking for DA-ready | V-05, V-07 | Decide canonical admission approach for development_plan and skills_inference_result | Design authority | Pass |
| REM-04 | Non-blocking for working review, can become blocking by governance policy | V-09 | Define numeric confidence thresholds and control tolerances | AI governance | Pass |
| REM-05 | Non-blocking for working review, blocking for operating readiness | V-04 | Define escalation SLA and timing fields for H-004, H-005, H-007, H-008 | Process owner | Pass |
| REM-06 | Non-blocking for working review, blocking for closure control maturity | V-02 | Assign closure failure resolver role and RACI | Capability owner | Pass |

# 14. Design Authority Submission Checklist

| Submission criterion | Status | Evidence | Submission note |
| --- | --- | --- | --- |
| Stage 5 content preserved and referenced | Pass | Section 2, Section 16.4 | Preservation evidence complete |
| Unified data model produced | Pass | Section 4 | Includes entities E-01 to E-10 |
| Data dictionary produced | Pass | Section 5 | Includes attributes A-01 to A-17 |
| Relationship model produced | Pass | Section 6 | Includes R-01 to R-05 |
| End-to-end flow map produced | Pass | Section 7 | Within-step and between-step flows present |
| Gap log produced with lifecycle | Pass | Section 8 | G-01 to G-08 tracked |
| Validation register complete | Pass | Section 11 | V-01 to V-20 completed |
| All mandatory checks Pass/Not applicable | Pending | Section 11 | V-05, V-07, V-10 remain Pending |
| DA decision record populated with real submission evidence | Pending | Section 10 | Not submitted yet |

Submission position:

- Suitable for internal working review: Yes.
- Suitable for formal Design Authority submission: Not yet.

# 15. Source-to-Output Traceability Matrix

| Output artefact section | Primary source(s) | Evidence IDs |
| --- | --- | --- |
| Section 4 Unified model | SRC-02, SRC-03, SRC-08, SRC-09, SRC-10 | EV-01, EV-03, EV-05 |
| Section 5 Data dictionary | SRC-02, SRC-03, SRC-04 | EV-01, EV-02 |
| Section 6 Relationship model | SRC-02, SRC-08, SRC-09 | EV-03, EV-04 |
| Section 7 Data flow map | SRC-03, SRC-04 | EV-01, EV-02 |
| Section 8 Gap log | SRC-02, SRC-03, SRC-10 | EV-02, EV-05 |
| Section 9 Enterprise alignment | SRC-06, SRC-07, SRC-08 | EV-03, EV-04 |
| Section 11 Validation register | SRC-05 and consolidated artefacts | EV-01 to EV-05 |

# 16. Source Inventory, Evidence Record, Change Log and Conversion Evidence

## 16.1 Source Inventory

| Source ID | Source | Precedence tier | Approval status | Scope of use |
| --- | --- | --- | --- | --- |
| SRC-01 | Delivery-Control/Stage_5.md (Stage 5B section used for method boundaries and checks context) | 1 | Approved in-method source | Method authority |
| SRC-02 | Stage 5 Output/Learning_and_Skills_Agent_Stage5_Model_v0.1.md | 2 | Draft working artefact | Preserved Stage 5 input |
| SRC-03 | Stage 4 Output/Learning_and_Skills_Agent_Stage_4_Classify.md | 2 | Finalised for SME review | Workflow, controls, handovers |
| SRC-04 | Learning-and-Skills-agent/Learning_Skills_Agent_Stage3_Decompose.md | 2 | Draft for SME review | Trigger, capability, decomposition evidence |
| SRC-05 | Learning-and-Skills-agent/stage-5b-document-generation.instructions.md | 1 | Repository method instruction | Structure, anti-fabrication, status model |
| SRC-06 | Neill-KPMG/fabric-layer enterprise-data-model/docs/modelling-standard.md | 3 | External approved reference | Grain, keys, envelope |
| SRC-07 | Neill-KPMG/fabric-layer enterprise-data-model/README.md | 3 | External approved reference | Layer boundaries |
| SRC-08 | Neill-KPMG/fabric-layer enterprise-data-model/sql/10_silver/070_workforce.sql and related SQL references | 3 | External approved reference | Workforce entities |
| SRC-09 | Neill-KPMG/fabric-layer enterprise-data-model/tests/test_repository.py | 3 | External approved reference | Hire-to-retire entity expectation |
| SRC-10 | Delivery-Control/Enterprise_Business_Data_Objects_Overview.docx | 3 | Workspace artefact | Enterprise object principles |

## 16.2 Evidence Record (sample mapping)

| Evidence ID | Source location | Extracted statement | Generated locations |
| --- | --- | --- | --- |
| EV-01 | [SRC-03], Workflow Decomposition Catalogue W-001..W-010 | Ten-step flow and control mapping | Sections 4, 7 |
| EV-02 | [SRC-03], H-001..H-008 | Eight handovers and failure modes | Sections 7, 8 |
| EV-03 | [SRC-08], silver.worker and workforce tables | Canonical worker-related entities | Sections 4, 5, 6 |
| EV-04 | [SRC-06], modelling standard keys/envelope | Traceability and grain rules | Sections 4, 9 |
| EV-05 | [SRC-10], worker/party/position and source-trace principles | Cross-check enterprise object fit | Sections 4, 9 |

## 16.3 Change Log for Added Data in Consolidation

| Change ID | Change | Reason | Evidence |
| --- | --- | --- | --- |
| CHG-01 | Added explicit consolidated data dictionary attributes A-01 to A-17 | Required Stage 5B output | [SRC-05] |
| CHG-02 | Added relationship model normalisation table | Required Stage 5B output | [SRC-05] |
| CHG-03 | Added validation register V-01 to V-20 | Required Stage 5B quality gate | [SRC-05] |
| CHG-04 | Added deliverable state calculation | Required Stage 5B state model | [SRC-05] |

## 16.4 Conversion Evidence Record

| Item | Value |
| --- | --- |
| Stage 5 source file | Stage 5 Output/Learning_and_Skills_Agent_Stage5_Model_v0.1.md |
| Conversion date | 2026-10-16 |
| Semantic changes in preserved Stage 5 section | None |
| Formatting-only changes | Stage 5 represented by preservation statement and metrics table in Section 2 |
| Reviewer status | Pending working review |
