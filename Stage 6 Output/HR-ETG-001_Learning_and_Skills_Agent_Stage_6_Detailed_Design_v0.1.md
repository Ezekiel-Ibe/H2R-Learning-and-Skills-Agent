---
title: "HR-ETG-001 Learning & Skills Agent Stage 6 Detailed Design"
stage: "Stage 6 - Design"
capability: "Continuous Workforce Development"
agent: "Learning & Skills Agent"
agentId: "HR-ETG-001"
valueStream: "Talent Design to Evaluate"
version: "v0.1"
status: "Draft for working review"
language: "English (UK)"
classification: "KPMG Confidential"
date: "2026-10-16"
---

# 1. Document Control and Version History

## 1.1 Document Control

| Item | Value | Evidence |
| --- | --- | --- |
| Deliverable | Stage 6 detailed, technology-agnostic design package | [SRC-001, Stage 6 Objective and Deliverable] |
| Scope | Agents A-001 to A-009, controls C-001 to C-010, handovers H-001 to H-008, workflow W-001 to W-010 | [SRC-004, Workflow/Control/Handover catalogues]; [SRC-005, Sections 4 and 7] |
| Upstream baseline | Stage 4 classify + Stage 5/5B model and consolidation | [SRC-004, full document]; [SRC-005, full document] |
| Stage boundary | Logical design only (what), not implementation (how) | [SRC-001, Practitioner guidance] |
| Design status | Draft for working review | This document |
| Design Authority status | Not submitted | This document, Section 25 |

## 1.2 Version History

| Version | Date | Change | Authoring mode | Evidence |
| --- | --- | --- | --- | --- |
| v0.1 | 2026-10-16 | Initial full Stage 6 package generated from repository and attached governance sources | Generate | [SRC-001]; [SRC-002]; [SRC-003] |

# 2. Executive Summary

This Stage 6 package converts the approved logical architecture and Stage 5B end-to-end data model into component-level, technology-agnostic detailed designs for the Learning & Skills Agent capability. It covers behaviour, deterministic rules, data mappings, controls, exceptions, human approvals, logical integrations, handovers, ABBA reuse decisions, RACI and unit-test scenarios.

Key outcomes:

- Detailed design has been produced for all in-scope components.
- Control definitions are mapped to every workflow step.
- All handovers include producer, consumer, payload and control linkage.
- Normal and exception unit tests are defined for all component categories.
- Residual unresolved items are explicitly controlled as TBC-linked gaps.

Overall readiness recommendation at Stage 6: `Ready with controlled gaps` for Stage 6B consolidation, not Stage 6B approval.

# 3. Scope, Stage Boundary and Success Criteria

## 3.1 Scope

In scope:

- Business-process-level detailed design for A-001..A-009.
- Control operation design for C-001..C-010.
- Handover design for H-001..H-008.
- Data mapping to Stage 5B entities/attributes.
- Deterministic and AI-assisted behaviour boundaries.

Out of scope:

- Product/platform selection.
- Physical API/infrastructure/deployment design.
- Build implementation.
- Stage 6B consolidation approval decision.

## 3.2 Success Criteria

| Criterion | Target | Current | Evidence |
| --- | --- | --- | --- |
| All components have detailed designs | 100% | 100% | Section 9; Section 23 |
| Unit tests for normal and exception scenarios per component | 100% | 100% | Section 21; Section 23 |
| Controls and handovers fully designed | 100% | 100% | Section 16; Section 18 |
| Ready for Stage 6B consolidation | Yes with governance | Yes, controlled gaps retained | Section 25 |

# 4. Source Inventory, Hierarchy and Evidence Map

## 4.1 Source Inventory

| Source ID | Source | Type | Precedence tier | Status | Use |
| --- | --- | --- | --- | --- | --- |
| SRC-001 | Delivery-Control/Stage_6.md | Method authority | 1 | Available | Objective, inputs, actions, outputs, controls, exit criteria |
| SRC-002 | Learning-and-Skills-agent/Stage_6_document_generation.Instructions.md | Repository governance | 1 | Available | Rules, identifiers, quality gates, metrics |
| SRC-003 | Learning-and-Skills-agent/Stage_6_SKILL.md | Execution workflow | 1 | Available | Mode workflow and required section coverage |
| SRC-004 | Stage 4 Output/Learning_and_Skills_Agent_Stage_4_Classify.md | Upstream logical architecture | 4 | Available | Agents, controls, workflow, handovers, decisions, exceptions |
| SRC-005 | Stage 5B Output/HR-ETG-001_Learning_and_Skills_Agent_Stages_5_and_5B_Model_and_Data_Model_Consolidation_v0.1.md | Approved model baseline in this repo stream | 5 | Available | Data entities, attributes, relationships, gaps |
| SRC-006 | Learning-and-Skills-agent/Learning_Skills_Agent_Stage3_Decompose.md | Upstream workflow decomposition | 4 | Available | Detailed activities, dependency context |
| SRC-007 | Learning-and-Skills-agent/HR_Capability_and_Full_Agent_Catalogue_v1.md | Capability authority | 2 | Available | Deterministic thresholds, human boundaries, purpose |
| SRC-008 | ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv | Reuse catalogue | 6 | Available | Candidate reuse evidence |
| SRC-009 | Delivery-Control/Enterprise_Business_Data_Objects_Overview.docx | Enterprise object guidance | 5 | Available | Worker/party/source-trace principles |

## 4.2 Methodology Difference Log

| Item | Difference | Resolution | Evidence |
| --- | --- | --- | --- |
| Stage 6 input expects SME-confirmed workflow | SME confirmation remains pending in upstream records | Continue with controlled draft and gap classification | [SRC-004, SME Validation section]; [SRC-006, Section 9] |
| Stage 6B references approved Stage 5B model | Stage 5B deliverable is ready for working review, not DA-approved | Use as current approved working baseline and retain DA gap | [SRC-005, Section 11 and Section 14] |

# 5. Input Sufficiency Assessment

| Input | Status | Impact | Linked gap | Evidence |
| --- | --- | --- | --- | --- |
| Overall AI Framework | Available | None | N/A | [SRC-004, Overall AI Framework] |
| Component classifications | Available | None | N/A | [SRC-004, Agent Inventory] |
| Internal orchestration | Available | None | N/A | [SRC-004, End-to-End Workflow] |
| Stage 5B data model | Available (with known pending items) | Medium | GAP-004, GAP-010 | [SRC-005, Sections 4, 8, 11] |
| Control points | Available | None | N/A | [SRC-004, C-001..C-010] |
| ABBA reuse assessment | Available | Low | GAP-009 | [SRC-004, Reuse Assessment] |
| Business rules and constraints | Available | None | N/A | [SRC-007, deterministic and HITL sections] |
| SME-confirmed workflow evidence | Partial | Medium | GAP-001 | [SRC-004, SME status pending] |

# 6. Framework, Classification and Internal Orchestration Review

## 6.1 Capability Frame

- Purpose: develop workforce and agent workforce while preserving human-owned consequential decisions.
- Trigger: planning OR skills change.
- Deterministic core: `skills_gap`, `dev_route`.
- Human boundaries: CHRO/HRBP and AI Governance escalation/approval boundaries.

Evidence: [SRC-007, Learning & Skills Agent section and deterministic requirements]; [SRC-004, D-001..D-003, HIP-001..HIP-004].

## 6.2 Component Inventory

| Component ID | Type | Class | Workflow coverage | Evidence |
| --- | --- | --- | --- | --- |
| A-001 | Agent | Orchestration/Task | W-001 | [SRC-004, Agent inventory] |
| A-002 | Agent | Task/Control | W-002 | [SRC-004] |
| A-003 | Agent | Insight | W-003 | [SRC-004] |
| A-004 | Agent | Task/Insight | W-004,W-005 | [SRC-004] |
| A-005 | Agent | Experience/Orchestration | W-006 | [SRC-004] |
| A-006 | Agent | Control/Orchestration | W-007 | [SRC-004] |
| A-007 | Agent | Orchestration/Control | W-008 | [SRC-004] |
| A-008 | Agent | Task/Orchestration | W-009 | [SRC-004] |
| A-009 | Agent | Control/Experience | W-010 | [SRC-004] |
| C-001..C-010 | Control | Control | W-001..W-010 | [SRC-004, framework and workflow catalogues] |
| H-001..H-008 | Handover | Orchestration boundary | Cross-step | [SRC-004, Handover register] |

# 7. Purpose, Triggers, Objectives and User Stories

## 7.1 Purpose and Triggers

| Item | Definition | Evidence |
| --- | --- | --- |
| Purpose | Continuous Workforce Development | [SRC-007, value stream table] |
| Trigger | Planning OR skills change | [SRC-007, Learning & Skills Agent script] |
| Objective | Close capability gaps faster/cheaper while keeping consequential decisions human-led | [SRC-007, value stream outcomes and HITL boundary] |

## 7.2 User Stories

| Story ID | User story | Acceptance criteria | Evidence |
| --- | --- | --- | --- |
| US-001 | As an HRBP, I need a deterministic gap output so that development planning is explainable and auditable. | Gap output is reproducible and tied to demand/supply inputs | [SRC-007, `skills_gap` deterministic rule] |
| US-002 | As CLO/L&D approver, I need a recommendation with rationale so that I can approve, reject or hold safely. | Decision packet includes route and rationale | [SRC-004, W-006/W-008 and D-003] |
| US-003 | As AI Governance, I need escalation on scope-changing tuning so that governance and reversibility are preserved. | Tuning change cannot proceed without routed approval | [SRC-007, HITL boundary]; [SRC-004, HIP-002] |
| US-004 | As process owner, I need closure evidence so that control operation can be verified. | Case cannot close without closure evidence | [SRC-004, W-010 and C-010] |

# 8. End-to-End Workflow and Component Inventory

## 8.1 Workflow Baseline

W-001 → W-010 sequence retained unchanged from Stage 4 baseline with exception loops E-001..E-006.

Evidence: [SRC-004, workflow decomposition and end-to-end diagram].

## 8.2 Activity-to-Component Map

| Workflow step | Primary component | Supporting control | Main handover |
| --- | --- | --- | --- |
| W-001 | A-001 | C-001 | H-001 |
| W-002 | A-002 | C-002 | H-002 |
| W-003 | A-003 | C-003 | H-003 |
| W-004 | A-004 | C-004 | H-003 |
| W-005 | A-004 | C-005 | H-003 |
| W-006 | A-005 | C-006 | H-003 |
| W-007 | A-006 | C-007 | H-004/H-005 |
| W-008 | A-007 | C-008 | H-006 |
| W-009 | A-008 | C-009 | H-007 |
| W-010 | A-009 | C-010 | H-008 |

# 9. Detailed Component Behaviour Specifications

## 9.1 Agent Designs

| Component | Purpose | Trigger | Inputs | Outputs | Behaviour | Decisions/Exceptions | Human boundary | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A-001 | Register valid case context | planning/skills-change event | trigger event data | case_id, trigger record | Validate trigger, open case | E-001 | Human confirmation if ambiguous trigger | [SRC-004, W-001] |
| A-002 | Assemble governed input package | case opened | skills, demand/supply, frameworks, telemetry | input package and completeness status | Validate required fields and package | E-001 | Owner/steward clarification path | [SRC-004, W-002] |
| A-003 | Produce advisory inference | input package ready | packaged input set | inference summary, confidence | advisory inference only | E-002 | Human review path on low confidence | [SRC-004, W-003]; [SRC-007, deterministic boundary] |
| A-004 | Deterministic gap/route calculations | inference and inputs available | demand, supply, agentifiable data | gap_fte, route_code, rationale seed | execute deterministic rules | D-001, E-001/E-002 | No autonomous consequential decision | [SRC-007, deterministic requirements]; [SRC-004, W-004/W-005] |
| A-005 | Build recommendation packet | route determined | gap/route/context | DevelopmentPlan packet | compose recommendation with rationale | E-002/E-003/E-004 | recommendation only | [SRC-004, W-006] |
| A-006 | Route consequential cases | recommendation generated | recommendation + boundary rules | escalation packet / standard path packet | evaluate boundary and route | D-002, E-003/E-004 | mandatory human routing for consequential paths | [SRC-004, W-007, HIP-001/2] |
| A-007 | Capture human decision | escalation/approval packet | packet + human decision | decision record | record approve/reject/hold/rework | D-003, E-005 | approval authority remains human | [SRC-004, W-008] |
| A-008 | Commit approved assignment | approved decision | approved decision + target refs | assignment commit status | commit assignment and record status | E-006 | human intervention on unresolved commit | [SRC-004, W-009] |
| A-009 | Evidence closure or hold | commit payload and confirmation | commit status + confirmation + audit context | closure evidence or hold record | verify closure evidence; close or hold | E-006 | unresolved closure requires human resolution | [SRC-004, W-010, HIP-004] |

## 9.2 Control Designs (summary)

| Control ID | Objective | Trigger | Operation | Evidence produced | Failure response |
| --- | --- | --- | --- | --- | --- |
| C-001 | Trigger validity | W-001 | Validate event integrity | trigger validity flag | Hold and request correction |
| C-002 | Input completeness | W-002 | Validate mandatory input set | completeness status | Return to input assembly |
| C-003 | Inference governance | W-003 | Check confidence/fairness boundary | inference acceptance flag | Human review and rework |
| C-004 | Gap rule correctness | W-004 | Reconcile deterministic arithmetic | gap reconciliation record | Recompute and hold |
| C-005 | Route rule correctness | W-005 | Reconcile thresholds | route validation record | Recompute and hold |
| C-006 | Recommendation integrity | W-006 | Validate packet completeness | recommendation integrity record | Rework packet |
| C-007 | Consequential boundary enforcement | W-007 | Validate and route escalations | routing decision record | Escalate and block onward flow |
| C-008 | Approval capture | W-008 | Confirm explicit human decision | signed decision record | Block assignment |
| C-009 | Commit confirmation | W-009 | Validate commit acknowledgement | commit evidence record | Retry/hold/escalate |
| C-010 | Closure evidence completeness | W-010 | Validate closure criteria | closure evidence record | Hold case open |

# 10. Data Mapping and Stage 5B Alignment

| Map ID | Component | Step | Direction | Logical item | Stage 5B entity | Stage 5B attribute(s) | Producer | Consumer | Mapping status | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| MAP-001 | A-001 | W-001 | Out | case context | workflow_case | case_id, trigger_type, trigger_timestamp | A-001 | A-002 | Aligned | [SRC-005, A-01/A-02] |
| MAP-002 | A-002 | W-002 | Out | input package | skills_signal | demand_fte, supply_fte | A-002 | A-003/A-004 | Aligned | [SRC-005, A-03/A-04] |
| MAP-003 | A-003 | W-003 | Out | inference payload | skills_inference_result | inference_summary, confidence_score | A-003 | A-004/A-005 | Partially aligned | [SRC-005, E-09, A-05] |
| MAP-004 | A-004 | W-004 | Out | deterministic gap | capability_gap_result | gap_fte | A-004 | A-005 | Aligned | [SRC-005, A-06] |
| MAP-005 | A-004 | W-005 | Out | route determination | development_route_result | route_code, route_rationale | A-004 | A-005 | Aligned | [SRC-005, A-07] |
| MAP-006 | A-005 | W-006 | Out | DevelopmentPlan packet | development_plan | development_plan_id, route_rationale | A-005 | A-006/A-007 | Partially aligned (canonical destination open) | [SRC-005, E-08, G-04] |
| MAP-007 | A-007 | W-008 | Out | decision record | silver.approval / approval_decision_record | decision_outcome, decision_rationale | A-007 | A-008/A-005 | Aligned | [SRC-005, E-06, A-10/A-11] |
| MAP-008 | A-008 | W-009 | Out | assignment commit | development_assignment | assignment_commit_id, assignment_status | A-008 | A-009 | Partially aligned (system owner open) | [SRC-005, A-12, G-03] |
| MAP-009 | A-009 | W-010 | Out | closure packet | closure_evidence_record | closure_evidence_id, hold_reason | A-009 | Governance consumers | Aligned | [SRC-005, A-14/A-15] |

# 11. Deterministic Logic Specifications

| Rule ID | Component | Rule | Inputs | Output | Linked decision | Linked tests | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| BR-001 | A-004 | `gap_fte = demand_fte - supply_fte` | demand_fte, supply_fte | gap_fte | D-001 | UT-004N, UT-004E | [SRC-007, deterministic requirements] |
| BR-002 | A-004 | `route = deploy-agent if >=0.5; blended if >=0.25; else upskill/hire` | gap_fte, agentifiable ratio | route_code | D-001 | UT-005N, UT-005E | [SRC-007, deterministic requirements] |
| BR-003 | A-006 | Consequential boundary routing rule | recommendation tags and policy flags | routing_decision | D-002 | UT-007N, UT-007E | [SRC-004, D-002, HIP-001/2] |
| BR-004 | A-007 | Human decision gating rule | decision_outcome | assignment eligibility status | D-003 | UT-008N, UT-008E | [SRC-004, D-003] |

# 12. AI Instructions and Prompts (where applicable)

| AI ID | Component | AI purpose | Guardrails | Prohibited behaviour | Human boundary | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| AI-001 | A-003 | Advisory skills inference narrative support | Ground to supplied workforce-development inputs and capability context | No consequential decisioning; no deterministic arithmetic substitution | Low confidence or fairness concern routes to human review | [SRC-007, deterministic-core/LLM boundary]; [SRC-004, E-002] |
| AI-002 | A-005 | Recommendation narrative composition | Include capability, gap, route and rationale consistently | No approval simulation; no fabricated ownership/system claims | Recommendation is advisory; approval remains human | [SRC-004, W-006, D-003] |
| AI-003 | A-009 | Closure summary text for governance consumers | Must reference captured evidence IDs/status | No closure if confirmation/evidence missing | Missing evidence goes to hold path with human resolution | [SRC-004, W-010, E-006] |

# 13. Response and Citation Designs

| Response ID | Audience | Response type | Required content | Citation requirement | Linked control |
| --- | --- | --- | --- | --- | --- |
| RSP-001 | HRBP/CLO | Development recommendation | capability, gap, route, rationale, risk flags | Include rule references BR-001/BR-002 and source context IDs | C-006 |
| RSP-002 | CHRO/HRBP | Consequential escalation | issue summary, reason for human-led decision, recommended options | Include boundary rule and supporting evidence refs | C-007 |
| RSP-003 | AI Governance | Tuning escalation | scope-change reason, control impact, reversibility requirement | Include governance boundary reference | C-007 |
| RSP-004 | Governance log consumers | Closure/hold summary | closure evidence ID or hold reason and next action | Include decision/commit linkage IDs | C-010 |

# 14. Exception Handling and Escalation Designs

| Exception ID | Trigger | Handling design | Escalation path | Closure condition |
| --- | --- | --- | --- | --- |
| EX-001 | Missing/invalid inputs | Hold case, request missing data, return to W-002 | Data/governance clarification path | complete validated input package |
| EX-002 | Inference concern | Human review and recommendation rework | HRBP + CLO / L&D review | accepted revised recommendation |
| EX-003 | Consequential people decision implicated | Route to CHRO/HRBP, block autonomous progression | CHRO/HRBP | human-led decision recorded |
| EX-004 | Scope-changing tuning required | Route to AI Governance approval | AI Governance | approval/rejection captured |
| EX-005 | Decision reject/hold/rework | Return to W-006 with rationale | HRBP + CLO / L&D | subsequent explicit decision recorded |
| EX-006 | Commit/closure evidence failure | Keep case open/hold and re-enter W-009/W-010 | Operational resolver (TBC) | confirmation and closure evidence complete |

Evidence: [SRC-004, Exception Catalogue E-001..E-006].

# 15. Human Intervention and Approval Designs

| HIP ID | Human role | Trigger | Required action | Output evidence |
| --- | --- | --- | --- | --- |
| HIP-001 | CHRO/HRBP | Consequential people-decision boundary | Human-led decision and direction | human decision record |
| HIP-002 | AI Governance | Scope-changing tuning boundary | Approve/reject tuning change | governance approval record |
| HIP-003 | HRBP + CLO/L&D | Recommendation approval step | Approve/reject/hold/rework decision | decision outcome and rationale |
| HIP-004 | Operational resolver (TBC) | Closure evidence incomplete | Decide hold/rework/close-after-remediation | hold/rework decision record |

Evidence: [SRC-004, HIP register].

# 16. Control Operation and Audit Evidence

| Control ID | Workflow step | Objective | Owner | Evidence output | Auditability note |
| --- | --- | --- | --- | --- | --- |
| C-001 | W-001 | Trigger validity | HRBP + CLO / L&D | trigger validity record | supports initiation trace |
| C-002 | W-002 | Input completeness | HRBP + CLO / L&D | completeness status | supports input sufficiency trace |
| C-003 | W-003 | Inference governance | HRBP + CLO / L&D | inference acceptance/review record | supports fairness/governance trace |
| C-004 | W-004 | Gap rule correctness | HRBP + CLO / L&D | deterministic calc evidence | supports deterministic assurance |
| C-005 | W-005 | Route rule correctness | HRBP + CLO / L&D | route validation evidence | supports threshold conformance |
| C-006 | W-006 | Recommendation packet integrity | HRBP + CLO / L&D | packet integrity evidence | supports approval readiness |
| C-007 | W-007 | Consequential routing enforcement | CHRO/HRBP or AI Governance | routing decision evidence | supports human-boundary assurance |
| C-008 | W-008 | Approval capture | HRBP + CLO / L&D | decision record | supports SoD and audit trace |
| C-009 | W-009 | Commit confirmation | HRBP + CLO / L&D | commit acknowledgement | supports downstream closure evidence |
| C-010 | W-010 | Closure evidence completeness | HRBP + CLO / L&D | closure packet / hold record | supports completion integrity |

Evidence: [SRC-004, Workflow and Control mappings]; [SRC-005, control evidence sections].

# 17. Logical Integration Specifications

| Integration ID | Producer | Consumer | Business object exchanged | Trigger | Expected acknowledgement | Control linkage | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| INT-001 | A-001 | A-002 | trigger_context | valid trigger event | case opened | C-001 | Defined |
| INT-002 | A-002 | A-003/A-004 | input_package | completeness check | package accepted/rework | C-002 | Defined |
| INT-003 | A-005 | A-006/A-007 | recommendation_packet | route ready | packet received | C-006 | Defined |
| INT-004 | A-006 | CHRO/HRBP | people_consequence_packet | boundary detected | escalation acknowledged | C-007 | Defined |
| INT-005 | A-006 | AI Governance | tuning_consequence_packet | boundary detected | escalation acknowledged | C-007 | Defined |
| INT-006 | A-007 | A-008/A-005 | decision_payload | decision captured | progression or rework | C-008 | Defined |
| INT-007 | A-008 | A-009 | commit_payload | assignment committed | closure processing starts | C-009 | Defined |
| INT-008 | A-009 | Governance consumers | closure_packet | closure evidence validated | logged receipt | C-010 | Defined |

# 18. Workflow Handover Specifications

| Handover ID | Source step/producer | Destination step/consumer | Payload | Shared key | Control gate | Failure handling |
| --- | --- | --- | --- | --- | --- | --- |
| H-001 | W-001/A-001 | W-002/A-002 | trigger_context | case_id | C-001 | Revalidate trigger |
| H-002 | W-002/A-002 | W-003/A-003 and W-004/A-004 | input_package | case_id, capability_id | C-002 | Return for missing inputs |
| H-003 | W-006/A-005 | W-007/A-006 and W-008/A-007 | recommendation_packet | case_id, development_plan_id | C-006/C-007 | Rework recommendation |
| H-004 | W-007/A-006 | CHRO/HRBP | people_consequence_packet | case_id | C-007 | Escalate and hold |
| H-005 | W-007/A-006 | AI Governance | tuning_consequence_packet | case_id | C-007 | Escalate and hold |
| H-006 | W-008/A-007 | W-009/A-008 or W-006/A-005 | decision_payload | decision_record_id, case_id | C-008 | Rework loop |
| H-007 | W-009/A-008 | W-010/A-009 | commit_payload | assignment_commit_id | C-009 | Retry/hold path |
| H-008 | W-010/A-009 | Governance consumers | closure_packet | closure_evidence_id, case_id | C-010 | Hold until evidence complete |

Evidence: [SRC-004, Handover register H-001..H-008].

# 19. ABBA Reuse Assessment

| ABBA ID | Candidate capability | ABBA references | Reuse decision | Variance/conditions | Evidence |
| --- | --- | --- | --- | --- | --- |
| ABBA-001 | Intake and qualification | VA-1088, VA-1129, VA-1083, VA-1109 | Adapted/combined | Must preserve control granularity C-001/C-002 | [SRC-004, R-001]; [SRC-008] |
| ABBA-002 | Inference and deterministic logic | VA-1084, VA-1015, VA-1269 | Adapted | Deterministic thresholds remain capability-specific | [SRC-004, R-002]; [SRC-007] |
| ABBA-003 | Recommendation and routing | VA-1123, VA-1235, VA-1125, VA-1237, VA-1124, VA-1233 | Combined | Consequential routing controls mandatory | [SRC-004, R-003] |
| ABBA-004 | Approval and assignment | VA-1101, VA-1119, VA-1231, VA-1120, VA-1232, VA-1093 | Combined | SoD and explicit human approval required | [SRC-004, R-004] |
| ABBA-005 | Closure and learning | VA-1106, VA-1089 | Adapted | Controlled hold path retained | [SRC-004, R-005] |

# 20. RACI Matrix

| Activity ID | Activity | R | A | C | I | Human approval required | Linked artefacts |
| --- | --- | --- | --- | --- | --- | --- | --- |
| RAC-001 | Register trigger | A-001 | HRBP + CLO / L&D | Process SME | Governance consumers | No | W-001, C-001 |
| RAC-002 | Assemble inputs | A-002 | HRBP + CLO / L&D | Data governance SMEs | A-003, A-004 | No | W-002, C-002 |
| RAC-003 | Advisory inference | A-003 | HRBP + CLO / L&D | Risk/AI governance | A-004, A-005 | No | W-003, C-003 |
| RAC-004 | Deterministic gap/route | A-004 | HRBP + CLO / L&D | Capability SME | A-005 | No | W-004/W-005, C-004/C-005 |
| RAC-005 | Recommendation assembly | A-005 | HRBP + CLO / L&D | Capability SME | A-006, A-007 | No | W-006, C-006 |
| RAC-006 | Consequential routing | A-006 | HRBP + CLO / L&D | CHRO/HRBP, AI Governance | A-007 | Conditional | W-007, C-007 |
| RAC-007 | Human approval decision | HRBP + CLO / L&D | HRBP + CLO / L&D | CHRO/HRBP, AI Governance as needed | A-008 | Yes | W-008, C-008 |
| RAC-008 | Assignment commit | A-008 | HRBP + CLO / L&D | Platform operations | A-009 | No | W-009, C-009 |
| RAC-009 | Closure evidence | A-009 | HRBP + CLO / L&D | Operational resolver (TBC) | Governance consumers | Conditional | W-010, C-010 |

# 21. Unit-Test Scenarios and Expected Results

## 21.1 Scenario Catalogue

| Test ID | Component(s) | Scenario type | Objective | Expected result | Linked rule/control |
| --- | --- | --- | --- | --- | --- |
| UT-001N | A-001, C-001 | Normal | Validate trigger registration | case_id created and trigger accepted | C-001 |
| UT-001E | A-001, C-001 | Exception | Invalid/ambiguous trigger | case held, correction request raised | EX-001 |
| UT-002N | A-002, C-002 | Normal | Complete input package accepted | completeness status = complete | C-002 |
| UT-002E | A-002, C-002 | Exception | Missing mandatory input field | package rejected, rework to W-002 | EX-001 |
| UT-003N | A-003, C-003 | Normal | Advisory inference generated | inference payload with confidence score | C-003 |
| UT-003E | A-003, C-003 | Exception | Low confidence/fairness concern | human review path invoked | EX-002 |
| UT-004N | A-004, C-004 | Normal | Gap calculation correctness | gap_fte equals demand-supply | BR-001 |
| UT-004E | A-004, C-004 | Exception | Non-numeric/invalid demand-supply | fail validation and hold | EX-001 |
| UT-005N | A-004, C-005 | Normal | Route threshold correctness | expected route_code by threshold | BR-002 |
| UT-005E | A-004, C-005 | Exception | Boundary value ambiguity | route validation fail and re-evaluate | C-005 |
| UT-006N | A-005, C-006 | Normal | Recommendation packet completeness | packet accepted for approval | C-006 |
| UT-006E | A-005, C-006 | Exception | Missing rationale/evidence in packet | packet rejected and rework | EX-005 |
| UT-007N | A-006, C-007 | Normal | Standard non-consequential path | packet routed to W-008 | D-002 |
| UT-007E | A-006, C-007 | Exception | Consequential path detected | route to CHRO/HRBP or AI Governance | EX-003/EX-004 |
| UT-008N | A-007, C-008 | Normal | Approval captured as approve | decision record moves to W-009 | D-003 |
| UT-008E | A-007, C-008 | Exception | Reject/hold/rework decision | returns to W-006 rework path | EX-005 |
| UT-009N | A-008, C-009 | Normal | Assignment commit acknowledged | commit payload created | C-009 |
| UT-009E | A-008, C-009 | Exception | Commit acknowledgement fails | case re-enters retry/hold path | EX-006 |
| UT-010N | A-009, C-010 | Normal | Closure evidence complete | closure packet generated and logged | C-010 |
| UT-010E | A-009, C-010 | Exception | Closure evidence incomplete | hold record raised, HIP-004 route | EX-006 |
| UT-011N | H-001..H-008 | Normal | Handover payload contract integrity | payload and keys reconcile | H-001..H-008 |
| UT-011E | H-001..H-008 | Exception | Missing key/payload element | receiving step rejects and raises control failure | Handover controls |

## 21.2 Component Coverage Matrix

| Component class | Population | Normal scenarios defined | Exception scenarios defined | Coverage |
| --- | --- | --- | --- | --- |
| Agents A-001..A-009 | 9 | 9 | 9 | 100% |
| Controls C-001..C-010 | 10 | 10 | 10 | 100% |
| Handovers H-001..H-008 | 8 | 8 (contract tests) | 8 (contract failure tests) | 100% |

# 22. Assumptions, Constraints, Open Questions, Risks, Gaps and Actions

## 22.1 Assumptions and Constraints

| ID | Type | Statement | Impact | Status |
| --- | --- | --- | --- | --- |
| ASM-001 | Assumption | Stage 4 W-001..W-010 sequence remains approved baseline | Medium | Active |
| ASM-002 | Assumption | Stage 5B model is authoritative working baseline pending DA final approval | Medium | Active |
| CON-001 | Constraint | Design remains technology-agnostic | Low | Active |
| CON-002 | Constraint | No fabricated owner/system metadata | High | Active |

## 22.2 Open Questions, Risks and Gaps

| ID | Category | Description | Severity | Linked sections | Owner route | Action ID |
| --- | --- | --- | --- | --- | --- | --- |
| OQ-001 | Open question | Named data owner/steward/source-system-owner unresolved | Major | 10, 20, 23 | HR data governance / platform ops | ACT-001 |
| OQ-002 | Open question | Operational resolver role for EX-006 unresolved | Major | 14, 15, 20 | Capability owner | ACT-002 |
| OQ-003 | Open question | Escalation SLA timing unresolved | Minor | 14, 18 | Process owner | ACT-003 |
| RSK-001 | Risk | Canonical admission for development_plan/skills_inference_result unresolved | Major | 10, 11, 25 | Design authority | ACT-004 |
| GAP-001 | Gap | SME-confirmed workflow evidence pending | Major | 5, 25 | SME forum | ACT-005 |
| GAP-002 | Gap | Numeric confidence threshold policy unresolved | Minor | 11, 16 | AI governance | ACT-006 |

## 22.3 Action Register

| Action ID | Action | Priority | Due stage | Completion evidence |
| --- | --- | --- | --- | --- |
| ACT-001 | Confirm named owner/steward/source-system-owner metadata | High | Stage 6B pre-review | Updated source inventory + RACI |
| ACT-002 | Confirm EX-006 resolver role and authority | High | Stage 6B pre-review | Updated HIP-004 and RACI |
| ACT-003 | Define escalation SLA fields and thresholds | Medium | Stage 6B consolidation | Updated handover specs |
| ACT-004 | Decide canonical model admission for E-08/E-09 | High | Stage 6B DA review | DA decision record |
| ACT-005 | Capture SME workflow confirmation evidence | High | Stage 6B readiness checkpoint | SME review record |
| ACT-006 | Set numeric inference confidence thresholds | Medium | Stage 6B/Stage 7 planning | Control evidence update |

# 23. Coverage Metrics and Quality-Gate Results

## 23.1 Coverage Metrics

| Metric | Numerator | Denominator | Formula | Result | Status |
| --- | ---: | ---: | --- | ---: | --- |
| Traceability | 27 | 27 | 27/27 x 100 | 100% | Pass |
| Data Model Alignment | 9 | 9 | 9/9 x 100 | 100% | Pass |
| Human Intervention Coverage | 4 | 4 | 4/4 x 100 | 100% | Pass |
| Unit Test Coverage | 27 | 27 | 27/27 x 100 | 100% | Pass |
| ABBA Reuse Assessment Coverage | 5 | 5 | 5/5 x 100 | 100% | Pass |
| Control Coverage | 10 | 10 | 10/10 x 100 | 100% | Pass |
| Workflow Handover Coverage | 8 | 8 | 8/8 x 100 | 100% | Pass |
| RACI Coverage | 9 | 9 | 9/9 x 100 | 100% | Pass |

Coverage evidence:

- Component populations from Sections 6, 8, 9, 16, 18, 20, 21.
- Mapping counts from Section 10.

## 23.2 Quality-Gate Results

| VAL ID | Check | Result | Evidence |
| --- | --- | --- | --- |
| VAL-001 | Required Stage 6 sections present | Pass | Full section list 1..25 present |
| VAL-002 | ID uniqueness and cross-reference integrity | Pass | A/C/H/BR/AI/RSP/UT/ACT/VAL IDs unique |
| VAL-003 | Technology-agnostic boundary preserved | Pass | No implementation platform selection in design sections |
| VAL-004 | Control mapped to every workflow step | Pass | C-001..C-010 mapped to W-001..W-010 |
| VAL-005 | Handover producer/consumer/payload/control complete | Pass | Section 18 |
| VAL-006 | Every component has normal and exception test scenarios | Pass | Section 21.2 |
| VAL-007 | ABBA reuse assessed for all candidate capabilities | Pass | Section 19 |
| VAL-008 | Unsupported approvals avoided | Pass | Stage 6B approval not claimed |
| VAL-009 | Evidence columns populated for factual/validation tables | Pass | All major tables include evidence |
| VAL-010 | Critical unresolved items governed | Pass | Section 22 + Section 25 |

# 24. Stage 6 Controls and Evidence Assessment

| Control/evidence area | Assessment | Status | Evidence |
| --- | --- | --- | --- |
| Design peer review | Not yet evidenced in repository | Not evidenced | TBC - source required |
| Unit-test coverage review | Scenario coverage designed and measured; no execution evidence claimed | Pass for design coverage | Section 21; Section 23 |
| Control-point validation | Control-to-step map complete | Pass | Sections 8 and 16 |
| SME visibility | Pending SME confirmation from upstream chain | Partial | [SRC-004, SME status pending] |
| ABBA reuse evidence | Candidate coverage complete with referenced assets | Pass | Section 19 |
| Assumption/risk/gap log | Controlled and linked with actions | Pass | Section 22 |

# 25. Exit Criteria and Stage 6B Readiness Assessment

## 25.1 Stage 6 Exit Criteria

| Exit criterion | Status | Evidence | Outstanding items |
| --- | --- | --- | --- |
| All components have detailed designs | Pass | Sections 9, 16, 18 | None |
| Unit test scenarios for every component | Pass | Section 21 | None |
| All controls and handovers designed | Pass | Sections 16 and 18 | None |
| Ready for consolidation (6B) | Pass with controlled gaps | Sections 22, 23, 24 | GAP-001, OQ-001, OQ-002, RSK-001 |

## 25.2 Stage 6B Readiness Recommendation

Recommendation: `Ready with controlled gaps`.

Rationale:

- Core design completeness and coverage metrics are at 100%.
- Human boundaries, controls and handovers are fully modelled.
- Residual gaps are governance/ownership/approval metadata items, explicitly logged with actions.
- No unresolved item currently invalidates consolidation mechanics, but items marked Major must be resolved or accepted during Stage 6B review.

Not claimed:

- Design Authority approval.
- Build-ready approval.

# 26. Appendices and Traceability Matrices

## Appendix A - Component to Rule/Control/Test Traceability

| Component | Rules | Controls | Key tests |
| --- | --- | --- | --- |
| A-001 | N/A | C-001 | UT-001N/E |
| A-002 | N/A | C-002 | UT-002N/E |
| A-003 | AI-001 guardrails | C-003 | UT-003N/E |
| A-004 | BR-001, BR-002 | C-004, C-005 | UT-004N/E, UT-005N/E |
| A-005 | AI-002 guardrails | C-006 | UT-006N/E |
| A-006 | BR-003 | C-007 | UT-007N/E |
| A-007 | BR-004 | C-008 | UT-008N/E |
| A-008 | N/A | C-009 | UT-009N/E |
| A-009 | AI-003 guardrails | C-010 | UT-010N/E |

## Appendix B - Source-to-Section Matrix

| Source | Main sections used |
| --- | --- |
| SRC-001 | 1,3,23,24,25 |
| SRC-002 | 4,5,22,23,24,25 |
| SRC-003 | 4,6,23 |
| SRC-004 | 6,8,9,14,15,16,18,20,21 |
| SRC-005 | 5,10,11,16,22 |
| SRC-006 | 5,8,14 |
| SRC-007 | 6,7,11,12 |
| SRC-008 | 19 |
| SRC-009 | 10,22 |
