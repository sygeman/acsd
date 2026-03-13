---
template_version: "1.0"
file_type: "adr"
cascade_level: variable
required_fields:
  - title
  - status
  - date
  - author
  - context
  - decision
  - consequences
  - parent_ref
cascade_children: []
---

# ADR-{{NUMBER}}: {{TITLE}}

| Meta | Value |
|------|-------|
| Status | {{Proposed|Accepted|Deprecated|Superseded}} |
| Date | {{YYYY-MM-DD}} |
| Author | {{AUTHOR}} |
| Parent Ref | {{VISION_REF|ARCHITECTURE_REF}} |

## 1. Context
{{Problem statement. Why this decision was needed. What constraints existed.}}

## 2. Decision
We will {{DECISION_STATEMENT}}

### Implementation Guidelines
- {{GUIDELINE_1}}
- {{GUIDELINE_2}}
- {{GUIDELINE_3}}

## 3. Consequences

### Positive
- {{POSITIVE_1}}
- {{POSITIVE_2}}
- {{POSITIVE_3}}

### Trade-offs & Risks
| Risk | Mitigation | Owner |
|------|------------|-------|
| {{RISK_1}} | {{MITIGATION_1}} | {{OWNER}} |
| {{RISK_2}} | {{MITIGATION_2}} | {{OWNER}} |

### Impact on Cascade
| Artifact | Required Change |
|----------|-----------------|
| architecture.md | {{CHANGE}} |
| interface.md | {{CHANGE}} |
| tests | {{CHANGE}} |
| code | {{CHANGE}} |

## 4. Alternatives Considered

| Alternative | Pros | Cons | Why Rejected |
|-------------|------|------|--------------|
| {{ALT_1}} | {{PROS}} | {{CONS}} | {{REASON}} |
| {{ALT_2}} | {{PROS}} | {{CONS}} | {{REASON}} |

## 5. Related Records

| ADR ID | Title | Relationship |
|--------|-------|--------------|
| {{ADR-XXX}} | {{TITLE}} | {{supersedes|related-to|conflicts-with}} |

## Checklist

- [ ] status is valid enum (Proposed|Accepted|Deprecated|Superseded)
- [ ] parent_ref points to existing vision.md or architecture.md
- [ ] Decision is specific and actionable (not vague)
- [ ] At least one alternative was considered
- [ ] Impact on cascade artifacts is documented

## LLM Instructions

- Validate: Check status enum, parent_ref exists, decision is actionable
- Generate: If Accepted, update downstream files listed in Impact section
- Conflict: Flag if code violates accepted ADR decisions
- Context: Read parent_ref first, ensure decision aligns with vision/architecture
