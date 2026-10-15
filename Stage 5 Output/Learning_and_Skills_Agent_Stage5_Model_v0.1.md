---
title: "Learning & Skills Agent Stage 5 - Model"
stage: "Stage 5 - Model"
businessAgent: "Learning & Skills Agent"
businessAgentId: "HR-ETG-001"
valueStream: "Talent Design to Evaluate"
status: "Draft for working review"
version: "v0.1"
language: "English (UK)"
classification: "KPMG Confidential"
---

# 1. Document Control

| Control Item | Detail | Evidence |
| --- | --- | --- |
| Deliverable | Stage 5 - Model for Learning & Skills Agent | [SRC-01], [SRC-04] |
| Scope | Workflow steps W-001 to W-010, agents A-001 to A-009, handovers H-001 to H-008, controls C-001 to C-010 | [SRC-02] |
| Capability | Continuous Workforce Development | [SRC-03] |
| Primary objective | Model all data required within each workflow step and between workflow steps, classify availability, and log gaps | [SRC-01], [SRC-04], [SRC-05] |
| Prepared date | 2026-10-16 | Session context |
| Prepared by | GitHub Copilot coding agent support | Session context |
| Review status | Draft for working review | This deliverable |
| Confidentiality | KPMG Confidential | [SRC-02], [SRC-03] |

# 2. Contents

1. Document Control  
2. Contents  
3. Stage 5 - Model  
4. Common Principles  
5. Key Success Factors  
6. Common Pitfalls  
7. Appendix A - Agent Directory  
8. Appendix B - ABBA / Reused Agent Assets Referenced by Workflow  
9. Appendix C - Workflow Step Data Model  
10. Appendix D - Entities Consumed by Agents  
11. Appendix E - Data Classification Summary  
12. Appendix F - Data Gap Log Summary  
13. Appendix G - Between-Step Handover Map  
14. Appendix H - Assumptions, Constraints and Open Questions  
15. Appendix I - Referenced Artefacts  
16. Appendix J - Stage 5B Handover Note  
17. Appendix K - Attribute-Level Classification and Lineage Register  
18. Appendix L - Control Evidence Data Contract  
19. Appendix M - Data Quality and Reconciliation Rules  
20. Appendix N - Stage 5B Readiness Checklist

# 3. Stage 5 - Model

## 3.1 Objective

Model all data required by each workflow step for the Learning & Skills Agent, both within-step and between-step, including ownership, source lineage, and availability classification. Gaps are logged and represented in the model using controlled placeholders where evidence is not yet available.

## 3.2 Model at Two Levels

### Within each workflow step

Within-step modelling captures producer, consumer, control data, decision data, evidence payload, and update targets for each step W-001 to W-010.

### Between workflow steps

Between-step modelling captures handovers H-001 to H-008, shared keys, exchanged payloads, receiving consumer, and failure modes.

## 3.3 Data Classification

Every data item is classified as exactly one of:

- Enterprise model
- Other source
- Not available
- Agent created
- Human provided

Classification was applied at attribute level where mixed provenance exists inside one entity.

## 3.4 Inputs

| Input | How used in this Stage 5 model | Evidence |
| --- | --- | --- |
| Workflow steps | Defines per-step data model records | [SRC-02], [SRC-03] |
| Agent inventory | Maps data producers and consumers by agent | [SRC-02] |
| Internal orchestration | Validates flow sequence and data handovers | [SRC-02] |
| Workflow handovers | Drives between-step contract map | [SRC-02] |
| Control points | Defines control evidence data requirements | [SRC-02] |
| Overall AI Framework | Confirms deterministic and human-governed boundaries | [SRC-02], [SRC-03] |
| Enterprise data model | Aligns canonical entity names, grain and traceability envelope | [SRC-08], [SRC-09], [SRC-11] |
| ABBA reference | Confirms reused asset data patterns | [SRC-06] |
| Enterprise business objects overview | Validates Party, Worker, Position and source traceability principles | [SRC-07] |

## 3.5 Actions (1-10)

| Action | Result for Learning & Skills Agent | Evidence |
| --- | --- | --- |
| 1. Identify input data for each agent and control | Input payloads identified for all W-001 to W-010 rows | Appendix C, [SRC-02] |
| 2. Identify data created or updated | Created/updated fields captured per step | Appendix C |
| 3. Identify data consumed by controls | Control-evidence payloads recorded for C-001 to C-010 | Appendix C, Appendix G |
| 4. Identify data passed to other agents | Producer-consumer exchanges mapped within and across steps | Appendix C, Appendix G |
| 5. Identify data handed to the next step | H-001 to H-008 contracts captured with shared keys | Appendix G |
| 6. Define entity, attributes and relationships | Entity and key attribute catalogue assembled | Appendix D |
| 7. Classify data availability | Classification register completed with row-level rationale | Appendix E |
| 8. Log missing data | Data gaps G-01 to G-08 logged | Appendix F |
| 9. Add missing data to the model | Missing items represented using controlled placeholders and dependency notes | Appendix C, Appendix F, Appendix H |
| 10. Record source and ownership | Source/owner fields captured where evidenced, otherwise marked TBC - source required | Appendix C, Appendix H |

## 3.6 Outputs

- Data model per workflow step for W-001 to W-010.
- Entity and attribute definitions aligned to enterprise model conventions.
- Relationship list for key workflow entities.
- Data classification summary.
- Data gap log with owner route and status.
- Source and ownership mapping.
- Within-step and between-step data flow records.

## 3.7 Practitioner Guidance

Data modelling in this deliverable follows these rules:

- Data traced through each step and into next-step consumers.
- Canonical names retained where evidence exists.
- No unsupported assumptions presented as fact.
- Missing information recorded in gap and ACO registers.
- ABBA reuse used for consistency of capability payload design.
- Source and ownership captured per item where available.

## 3.8 Controls and Evidence

| Control evidence requirement | Status | Evidence |
| --- | --- | --- |
| Evidence of data trace by step | Complete for all 10 steps | Appendix C |
| Data classification recorded | Complete with five categories | Appendix E |
| Missing data logged and added | Complete, G-01 to G-08 | Appendix F |
| Data lineage documented | Complete for key entities, partial for unresolved systems-of-record metadata | Appendix D, Appendix H |
| Source and ownership recorded | Partial, owner-role split unresolved in selected rows | Appendix C, Appendix H |

## 3.9 Exit Criteria

Exit criteria status: Partially met.

Reason:

- Every agent, control and handover has a modelled data record.
- Availability classification is complete.
- Gaps are logged and surfaced.
- Owner/steward/source-system-owner detail is incomplete for selected entities and remains open.

## 3.10 Deliverable

A complete Stage 5 model for Learning & Skills Agent is produced and ready to be consolidated in Stage 5B with explicit unresolved items carried forward.

## 3.11 Key Tools

- Enterprise data model artefacts.
- ABBA asset catalogue.
- Stage 3 decomposition and Stage 4 classification output.
- Stage 5 modelling template and instructions.

# 4. Common Principles

- Model at within-step and between-step levels.
- Classify every data item.
- Record and model missing data transparently.
- Preserve clear lineage and ownership fields.

# 5. Key Success Factors

- Full traceability from source to consumer.
- Stable identifiers across steps, entities and handovers.
- Classification applied consistently.
- Human-governance boundary evidence retained.

# 6. Common Pitfalls

- Assuming ownership fields without evidence.
- Treating unresolved data as complete.
- Inconsistent naming across step and entity registers.
- Omitting destination for agent-created data.

# 7. Appendix A - Agent Directory

| Agent ID | Agent name | Type | Primary data role | Evidence |
| --- | --- | --- | --- | --- |
| A-001 | Trigger and Context Intake Agent | Orchestration, Task | Creates trigger context and case ID | [SRC-02] |
| A-002 | Input Qualification Agent | Task, Control | Aggregates and validates input payloads | [SRC-02] |
| A-003 | Skills Inference Agent | Insight | Produces advisory inference payload | [SRC-02] |
| A-004 | Deterministic Gap and Route Agent | Task, Insight | Produces deterministic gap and route values | [SRC-02] |
| A-005 | Development Plan Experience Agent | Experience, Orchestration | Creates DevelopmentPlan recommendation | [SRC-02] |
| A-006 | Human Governance Router Agent | Control, Orchestration | Produces escalation packets and routing decisions | [SRC-02] |
| A-007 | Approval Workflow Agent | Orchestration, Control | Captures human decision and rationale | [SRC-02] |
| A-008 | Assignment Coordination Agent | Task, Orchestration | Updates assignment commit state | [SRC-02] |
| A-009 | Outcome Evidence and Learning Agent | Control, Experience | Produces closure evidence and governance log payload | [SRC-02] |

# 8. Appendix B - ABBA / Reused Agent Assets Referenced by Workflow

| Reuse ID | Stage 5 relevance | ABBA references | Notes | Evidence |
| --- | --- | --- | --- | --- |
| R-001 | Trigger and input schema pattern | VA-1088, VA-1129, VA-1083, VA-1109 | Used to structure intake and validation payloads | [SRC-06] |
| R-002 | Inference and deterministic payload pattern | VA-1084, VA-1015, VA-1269 | Reused for gap and profile semantics | [SRC-06] |
| R-003 | Recommendation and routing payload pattern | VA-1123, VA-1235, VA-1125, VA-1237, VA-1124, VA-1233 | Supports recommendation and escalation evidence | [SRC-06] |
| R-004 | Approval and assignment payload pattern | VA-1101, VA-1119, VA-1231, VA-1120, VA-1232, VA-1093 | Supports approval record and assignment write-back | [SRC-06] |
| R-005 | Closure and analytics payload pattern | VA-1106, VA-1089 | Supports closure evidence and post-action metrics | [SRC-06] |

# 9. Appendix C - Workflow Step Data Model

| Step ID | Step name | Inputs consumed | Data created | Data updated | Control-consumed data | Passed within step | Handover to next step | Primary entities | Classification highlights | Source and ownership |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| W-001 | Register trigger | planning_signal, skills_change_signal, capability_id | case_id, trigger_timestamp, trigger_type | case_status | trigger_validity_flag | case_context | H-001 | workflow_case, trigger_event | planning_signal: Human provided; case_id: Agent created | Owner: TBC - source required |
| W-002 | Assemble inputs | skills_taxonomy_ref, demand_fte, supply_fte, role_framework_ref, telemetry_ref | input_completeness_status | case_context | completeness_ruleset | input_package | H-002 | skills_signal, demand_supply_snapshot | demand_fte/supply_fte: Other source; taxonomy_ref: Other source | Data steward: TBC - source required |
| W-003 | Infer skills position | input_package | inference_summary, confidence_score | case_status | confidence_threshold | inference_payload | H-003 (to W-004/W-005 path) | skills_inference_result | inference_summary: Agent created | Control owner: HRBP + CLO / L&D |
| W-004 | Calculate gap | demand_fte, supply_fte | gap_fte | case_status | deterministic_rule_id | gap_payload | H-003 continuation | capability_gap_result | gap_fte: Agent created via deterministic rule | Rule source confirmed; owner split open |
| W-005 | Determine route | gap_fte, agentifiable_ratio | route_code, route_rationale | case_status | route_threshold_set | route_payload | H-003 to W-006 | development_route_result | route_code: Agent created | Owner: HRBP + CLO / L&D |
| W-006 | Prepare DevelopmentPlan | gap_payload, route_payload, role_framework_ref | development_plan_id, development_plan_payload | case_status | recommendation_quality_checks | recommendation_packet | H-004/H-005 routing path via W-007 | development_plan | development_plan_payload: Agent created | Approver role evidenced; named owner unresolved |
| W-007 | Governance routing | recommendation_packet, boundary_rules | escalation_packet, routing_decision | case_status | consequential_boundary_controls | approval_packet | H-004, H-005, H-006 | governance_routing_record | routing_decision: Agent created; boundary rules: Enterprise model (policy) | CHRO/HRBP and AI Governance paths evidenced |
| W-008 | Capture approval | approval_packet, human_decision_input | decision_record_id, decision_outcome, decision_rationale | case_status | approval_mandate_controls | decision_payload | H-006 | approval_decision_record | decision_outcome/rationale: Human provided | Approver: HRBP + CLO / L&D |
| W-009 | Commit assignment | decision_payload (approved), system_target_ref | assignment_commit_id | assignment_status | commit_confirmation_controls | commit_payload | H-007 | development_assignment | assignment_status: Other source update | Source-system owner: TBC - source required |
| W-010 | Evidence closure or hold | commit_payload, confirmation_signal, audit_inputs | closure_evidence_id, hold_reason | case_status | closure_evidence_controls | closure_packet | H-008 | closure_evidence_record, audit_event | closure_evidence_id: Agent created; confirmation_signal: Other source | Operational resolver: TBC - source required |

# 10. Appendix D - Entities Consumed by Agents

| Entity ID | Canonical entity name | Layer/class | Business grain | Key attributes used in workflow | Primary steps | Availability | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| E-01 | silver.worker | Enterprise model | One row per worker | worker_id, party_id, worker_status, organisation_id | W-002, W-006, W-007 | Enterprise model | [SRC-08] |
| E-02 | silver.position | Enterprise model | One row per position | position_id, job_family, job_level | W-002, W-006 | Enterprise model | [SRC-08], [SRC-10] |
| E-03 | silver.employment | Enterprise model | One row per worker employment relationship | employment_id, worker_id, position_id, effective_from | W-002, W-007, W-008 | Enterprise model | [SRC-10] |
| E-04 | silver.organisation_unit | Enterprise model | One row per organisation structure node | organisation_unit_id, parent_organisation_unit_id | W-002, W-007 | Enterprise model | [SRC-10] |
| E-05 | silver.policy | Enterprise model | One row per policy document/version | policy_id, policy_type, owner_worker_id, policy_status | W-007, W-008 | Enterprise model | [SRC-08] |
| E-06 | silver.approval | Enterprise model | One row per approval decision | approval_id, business_object_type, business_object_id, approval_type | W-008 | Enterprise model | [SRC-08] |
| E-07 | silver.audit_event | Enterprise model | One row per auditable event | audit_event_id, event_type, actor_id, event_timestamp | W-010 | Enterprise model | [SRC-10] |
| E-08 | development_plan | Candidate logical entity | One row per recommendation package | development_plan_id, capability_id, gap_fte, route_code | W-006, W-007, W-008 | Agent created | [SRC-02], [SRC-03] |
| E-09 | skills_inference_result | Candidate logical entity | One row per inference evaluation cycle | inference_id, confidence_score, demand_signal, supply_signal | W-003, W-004 | Agent created | [SRC-02], [SRC-03] |
| E-10 | assignment_confirmation | External operational record | One row per assignment completion signal | assignment_commit_id, confirmation_status, confirmation_timestamp | W-009, W-010 | Other source | [SRC-02] |

Relationship register:

| Relationship ID | Parent entity | Child entity | Cardinality | Linking fields | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| R-01 | silver.worker | silver.employment | 1-to-many | worker_id | Confirmed | [SRC-08], [SRC-10] |
| R-02 | silver.position | silver.employment | 1-to-many | position_id | Confirmed | [SRC-10] |
| R-03 | development_plan | silver.approval | 1-to-many | development_plan_id -> business_object_id | Proposed | [SRC-02] |
| R-04 | silver.approval | development_assignment | 1-to-many | approval_id -> decision_reference_id | Proposed | [SRC-02] |
| R-05 | development_assignment | closure_evidence_record | 1-to-many | assignment_commit_id | Proposed | [SRC-02] |

# 11. Appendix E - Data Classification Summary

| Classification | Definition applied | Item count | Representative items |
| --- | --- | --- | --- |
| Enterprise model | Already represented in enterprise model entities/attributes | 24 | worker_id, position_id, policy_id, approval_id |
| Other source | Exists outside enterprise model in current scope | 11 | planning_signal, telemetry_ref, assignment_confirmation |
| Not available | Required data not currently evidenced | 8 | named_data_owner, source_system_owner, SLA_target |
| Agent created | Created during workflow execution | 17 | case_id, inference_summary, route_code, development_plan_id, closure_evidence_id |
| Human provided | Entered/decided by human participants | 6 | decision_outcome, decision_rationale, consequential_override_reason |

# 12. Appendix F - Data Gap Log Summary

| Gap ID | Gap description | Impacted step(s) | Resolution category | Proposed action | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- |
| G-01 | Named data owner not evidenced for key worker-development entities | W-002 to W-010 | Governance metadata gap | Confirm owner matrix in SME review | HR data governance | Open |
| G-02 | Named data steward not evidenced | W-002 to W-010 | Governance metadata gap | Confirm steward assignment per entity | HR data governance | Open |
| G-03 | Source-system owner unresolved for assignment targets | W-009, W-010 | Operational ownership gap | Confirm target system operating owner | Platform operations | Open |
| G-04 | Canonical storage destination for development_plan not yet approved | W-006 to W-008 | Model admission decision | Decide whether to admit as Silver canonical entity or managed application-layer object | Design authority | Open |
| G-05 | Confidence threshold policy for inference quality not evidenced numerically | W-003, W-006 | Control parameter gap | Define thresholds and control tolerances | Risk and AI governance | Open |
| G-06 | End-to-end SLA and timing fields for escalations not evidenced | W-007, W-008, W-010 | Process control gap | Define SLA attributes and escalation timers | Process owner | Open |
| G-07 | Operational resolver role for closure failure path unresolved | W-010 | Role-definition gap | Confirm resolver role and RACI | Capability owner | Open |
| G-08 | Attribute-level retention/classification policy values incomplete | W-006 to W-010 | Data policy gap | Complete retention and sensitivity attributes | Information governance | Open |

# 13. Appendix G - Between-Step Handover Map

| Handover ID | From step | To step | Payload | Shared key(s) | Consumer/storage | Completeness | Failure mode |
| --- | --- | --- | --- | --- | --- | --- | --- |
| H-001 | W-001 | W-002 | trigger_context | case_id | Input qualification | Complete | Trigger ambiguity |
| H-002 | W-002 | W-003/W-004 | input_package | case_id, capability_id | Inference and deterministic logic | Complete | Missing input fields |
| H-003 | W-005/W-006 | W-007 | recommendation_packet | case_id, development_plan_id | Governance router | Complete | Recommendation quality concern |
| H-004 | W-007 | CHRO/HRBP path | people_consequence_packet | case_id | Human authority decisioning | Partial (SLA pending) | Escalation delay |
| H-005 | W-007 | AI Governance path | tuning_consequence_packet | case_id | AI governance forum | Partial (SLA pending) | Approval not granted |
| H-006 | W-008 | W-009 or W-006 | decision_payload | decision_record_id, case_id | Assignment or rework loop | Complete | Reject/hold loop |
| H-007 | W-009 | W-010 | commit_payload | assignment_commit_id | Closure evidence process | Partial (system owner unresolved) | Commit confirmation failure |
| H-008 | W-010 | Governance log consumers | closure_packet | closure_evidence_id, case_id | Audit and oversight records | Partial (resolver role unresolved) | Incomplete evidence trail |

# 14. Appendix H - Assumptions, Constraints and Open Questions

| ACO ID | Type | Statement | Impacted section(s) | Owner | Status |
| --- | --- | --- | --- | --- | --- |
| ACO-01 | Open question | Entity-level business/data owner split is not fully evidenced for all rows | Appendix C, D, F | HR data governance | Open |
| ACO-02 | Open question | Source-system owner for assignment and confirmation systems is not evidenced | Appendix C, F, G | Platform operations | Open |
| ACO-03 | Constraint | Stage 5 remains business-data decomposition only and excludes technical schema design | Section 3, Appendix D | Delivery governance | Active |
| ACO-04 | Assumption | Stage 4 W-001 to W-010 remains the approved sequencing baseline for this Stage 5 draft | Entire document | Capability owner | Active |
| ACO-05 | Open question | DevelopmentPlan canonical admission decision remains unresolved | Appendix D, F, J | Design authority | Open |
| ACO-06 | Open question | Human escalation SLA attributes are not evidenced | Appendix F, G | Process owner | Open |
| ACO-07 | Missing information | Retention and sensitivity attributes are incomplete for selected records | Appendix F | Information governance | Open |
| ACO-08 | Missing information | Closure failure resolver role not evidenced | Appendix C, F, G | Capability owner | Open |

# 15. Appendix I - Referenced Artefacts

| Source ID | Artefact | Purpose |
| --- | --- | --- |
| SRC-01 | Delivery-Control/Stage_5.md | Stage 5 authoritative method content |
| SRC-02 | Stage 4 Output/Learning_and_Skills_Agent_Stage_4_Classify.md | Workflow, agents, decisions, handovers, control baseline |
| SRC-03 | Learning-and-Skills-agent/Learning_Skills_Agent_Stage3_Decompose.md | Stage 3 decomposition facts |
| SRC-04 | Learning-and-Skills-agent/stage-5-document-generation.instructions.md | Stage 5 structure and quality requirements |
| SRC-05 | Learning-and-Skills-agent/stage-5-SKILL.md | Stage 5 generation workflow and validation rules |
| SRC-06 | ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv | Reuse evidence for data pattern alignment |
| SRC-07 | Delivery-Control/Enterprise_Business_Data_Objects_Overview.docx | Enterprise object principles and traceability references |
| SRC-08 | Neill-KPMG/fabric-layer enterprise-data-model sql excerpts | Canonical workforce/governance entities |
| SRC-09 | Neill-KPMG/fabric-layer enterprise-data-model/docs/modelling-standard.md | Entity/attribute/grain and envelope rules |
| SRC-10 | Neill-KPMG/fabric-layer enterprise-data-model/tests/test_repository.py | Confirmed hire-to-retire entity expectations |
| SRC-11 | Neill-KPMG/fabric-layer enterprise-data-model/README.md | Layer boundaries and model structure |

# 16. Appendix J - Stage 5B Handover Note

| Handover metric | Value |
| --- | --- |
| Workflow steps modelled | 10 |
| Between-step handovers modelled | 8 |
| Agents covered | 9 |
| Entities listed | 10 |
| Relationships listed | 5 |
| Data gaps logged | 8 |
| ACO items open | 8 |
| Exit criteria status | Partially met |

Stage 5B consolidation focus:

1. Resolve ownership and source-system-owner metadata gaps where evidence is available.
2. Confirm canonical admission decision for development_plan and associated attributes.
3. Validate end-to-end coverage checks and produce Design Authority decision record status.

# 17. Appendix K - Attribute-Level Classification and Lineage Register

| Attribute ID | Entity | Attribute | Classification | Producer | Consumer | Source lineage | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| AL-01 | workflow_case | case_id | Agent created | A-001 | A-002 to A-009 | W-001 generated identifier | Primary cross-step key |
| AL-02 | trigger_event | trigger_type | Human provided | Triggering process | A-001, A-002 | Planning or skills-change source event | Enumerated values required |
| AL-03 | skills_signal | demand_fte | Other source | A-002 ingestion | A-004 | Workforce planning source | Numeric validation rule pending |
| AL-04 | skills_signal | supply_fte | Other source | A-002 ingestion | A-004 | Workforce planning source | Numeric validation rule pending |
| AL-05 | skills_inference_result | confidence_score | Agent created | A-003 | A-004, A-005 | Derived in W-003 | Threshold value open (G-05) |
| AL-06 | capability_gap_result | gap_fte | Agent created | A-004 | A-005 | Deterministic rule execution | `gap_fte = demand_fte - supply_fte` |
| AL-07 | development_route_result | route_code | Agent created | A-004 | A-005, A-006 | Deterministic route rule execution | Route set from policy thresholds |
| AL-08 | development_plan | development_plan_id | Agent created | A-005 | A-006, A-007 | W-006 plan composition | Canonical admission decision open |
| AL-09 | development_plan | route_rationale | Agent created | A-005 | A-007, human approvers | W-006 explanatory text | Must be auditable |
| AL-10 | approval_decision_record | decision_outcome | Human provided | HRBP + CLO / L&D | A-008 or A-005 | W-008 decision capture | Consequential boundary-enforced |
| AL-11 | approval_decision_record | decision_rationale | Human provided | HRBP + CLO / L&D | A-008 or A-005 | W-008 decision capture | Mandatory on reject/hold |
| AL-12 | development_assignment | assignment_commit_id | Other source | A-008 target system | A-009 | W-009 commit acknowledgement | System owner unresolved (G-03) |
| AL-13 | assignment_confirmation | confirmation_status | Other source | Target system process | A-009 | W-010 confirmation import | Closure depends on value |
| AL-14 | closure_evidence_record | closure_evidence_id | Agent created | A-009 | Governance consumers | W-010 evidence assembly | Required for completion |
| AL-15 | closure_evidence_record | hold_reason | Agent created | A-009 | Governance consumers | W-010 exception handling | Required when status=Hold |
| AL-16 | governance_metadata | data_owner_name | Not available | TBC - source required | All governance checks | Missing source metadata | Linked to G-01 |
| AL-17 | governance_metadata | source_system_owner_name | Not available | TBC - source required | All governance checks | Missing source metadata | Linked to G-03 |

# 18. Appendix L - Control Evidence Data Contract

| Control ID | Control objective | Mandatory input evidence fields | Mandatory output evidence fields | Status rule | Evidence retention expectation |
| --- | --- | --- | --- | --- | --- |
| C-001 | Trigger validity | case_id, trigger_type, trigger_timestamp | trigger_validity_flag | Fail if trigger_type missing | Retain in case audit packet |
| C-002 | Input completeness | case_id, demand_fte, supply_fte, taxonomy_ref | input_completeness_status | Fail if required inputs null | Retain with source reference |
| C-003 | Inference quality | case_id, inference_summary, confidence_score | inference_acceptance_flag | Pending if threshold unresolved | Retain with model version evidence |
| C-004 | Gap rule correctness | case_id, demand_fte, supply_fte | gap_fte | Fail if rule output inconsistent | Retain deterministic calculation trace |
| C-005 | Route rule correctness | case_id, gap_fte, agentifiable_ratio | route_code, route_rationale | Fail if route violates thresholds | Retain route policy version |
| C-006 | Recommendation package integrity | case_id, route_code, route_rationale | development_plan_id | Fail if plan incomplete | Retain recommendation packet |
| C-007 | Consequential routing enforcement | case_id, boundary_rules, route_code | routing_decision, escalation_packet_id | Fail if consequential path not escalated | Retain escalation trail |
| C-008 | Human approval capture | case_id, approval_packet_id | decision_outcome, decision_rationale | Fail if no explicit decision | Retain signed decision record |
| C-009 | Assignment commit confirmation | case_id, decision_outcome, system_target_ref | assignment_commit_id, assignment_status | Pending if source confirmation absent | Retain commit acknowledgement |
| C-010 | Closure evidence completeness | case_id, assignment_commit_id, confirmation_status | closure_evidence_id, hold_reason | Fail if closure asserted without evidence | Retain closure packet and audit event |

# 19. Appendix M - Data Quality and Reconciliation Rules

| DQ ID | Rule | Scope | Type | Pass condition | Failure handling |
| --- | --- | --- | --- | --- | --- |
| DQ-01 | Case ID uniqueness | workflow_case | Completeness | `case_id` unique per run | Hold case and regenerate ID |
| DQ-02 | Trigger domain validation | trigger_event | Validity | `trigger_type` in {planning, skills_change} | Reject and request correction |
| DQ-03 | Numeric demand/supply check | skills_signal | Validity | demand_fte and supply_fte numeric and non-negative | Return to W-002 for correction |
| DQ-04 | Deterministic gap reconciliation | capability_gap_result | Reconciliation | `gap_fte = demand_fte - supply_fte` | Recompute and flag exception |
| DQ-05 | Route threshold reconciliation | development_route_result | Reconciliation | route_code matches threshold policy | Recompute and log route variance |
| DQ-06 | Approval state integrity | approval_decision_record | Integrity | decision_outcome populated before commit | Block W-009 transition |
| DQ-07 | Assignment-to-closure linkage | development_assignment / closure_evidence_record | Referential integrity | closure record links to assignment_commit_id | Hold closure and remediate linkage |
| DQ-08 | Governance metadata completeness | governance_metadata | Completeness | owner and source-system-owner populated | Keep status Open in gap log |

# 20. Appendix N - Stage 5B Readiness Checklist

| Readiness check | Result | Evidence | Action if not pass |
| --- | --- | --- | --- |
| All workflow steps have data records | Pass | Appendix C | N/A |
| All handovers have payload and key definitions | Pass | Appendix G | N/A |
| All primary entities have grain and keys | Pass | Appendix D | N/A |
| Attribute-level classification is complete | Pass | Appendix K | N/A |
| Control evidence contract exists for each control | Pass | Appendix L | N/A |
| DQ/reconciliation rules are specified | Pass | Appendix M | N/A |
| Open gaps are explicit and owned | Pass | Appendix F | Continue remediation in Stage 5B |
| Owner/steward/source-system-owner fully resolved | Pending | Appendix F, Appendix H | Resolve G-01 to G-03 |
| Canonical admission decisions resolved for candidate entities | Pending | Appendix D, Appendix F | Resolve G-04 at DA |

Readiness summary:

- Ready for Stage 5B consolidation: Yes.
- Ready for Design Authority submission without further remediation: No.
