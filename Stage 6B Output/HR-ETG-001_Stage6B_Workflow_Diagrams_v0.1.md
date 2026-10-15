# HR-ETG-001 Stage 6B Workflow Diagrams (v0.1)

## End-to-End Workflow

```mermaid
flowchart TD
    WF01[WF-01 Register trigger] --> WF02[WF-02 Assemble inputs]
    WF02 --> WF03[WF-03 Advisory inference]
    WF03 --> WF04[WF-04 Calculate gap]
    WF04 --> WF05[WF-05 Determine route]
    WF05 --> WF06[WF-06 Prepare development plan]
    WF06 --> WF07[WF-07 Governance routing]
    WF07 --> WF08[WF-08 Human decision]
    WF08 -->|Approve| WF09[WF-09 Commit assignment]
    WF08 -->|Reject or hold| WF06
    WF09 --> WF10[WF-10 Closure evidence or hold]
```

Evidence Reference: [SRC-06, End-to-End Workflow Diagram]; [SRC-04, section 8.1].

## Exception and Escalation Overlay

```mermaid
flowchart LR
    WF02[WF-02] --> EXC01[EXC-01 Input completeness failure]
    WF03[WF-03] --> EXC02[EXC-02 Inference concern]
    WF07[WF-07] --> EXC03[EXC-03 Consequential people decision]
    WF07 --> EXC04[EXC-04 Scope-change tuning]
    WF08[WF-08] --> EXC05[EXC-05 Decision reject or hold]
    WF09[WF-09] --> EXC06[EXC-06 Commit or closure evidence failure]
    WF10[WF-10] --> EXC06
```

Evidence Reference: [SRC-04, section 14]; [SRC-06, Exception Catalogue].

Classification: KPMG confidential
