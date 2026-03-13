---
template_version: "1.0"
file_type: "vision"
cascade_level: 0
required_fields:
  - purpose
  - core_value
  - scope_includes
  - scope_excludes
  - primary_actors
  - core_capabilities
  - system_invariants
  - non_goals
  - success_criteria
cascade_children:
  - "acsd/architecture/index.md"
  - "acsd/data_model.md"
---

# Vision: {{PROJECT_NAME}}

## 1. Purpose

The system {{PROJECT_NAME}} exists to {{CORE_VALUE}} for {{TARGET_AUDIENCE}} via {{PRIMARY_MECHANISM}}.

## 2. Core Value Proposition

| Aspect | Description |
|--------|-------------|
| Problem | {{PROBLEM_STATEMENT}} |
| Solution | {{SOLUTION_SUMMARY}} |
| Unique Value | {{UNIQUE_VALUE}} |
| Success Metric | {{SUCCESS_METRIC}} |

## 3. System Scope

### In-Scope
- {{SCOPE_ITEM_1}}
- {{SCOPE_ITEM_2}}
- {{SCOPE_ITEM_3}}

### Out-of-Scope (Non-Goals)
- {{NON_GOAL_1}}
- {{NON_GOAL_2}}
- {{NON_GOAL_3}}

## 4. Primary Actors

| Actor | Goal | Success Scenario | Failure Scenario |
|-------|------|-----------------|------------------|
| {{ACTOR_NAME}} | {{ACTOR_GOAL}} | {{SUCCESS_FLOW}} | {{FAILURE_FLOW}} |

## 5. Core Capabilities

### 5.1 {{CAPABILITY_NAME}}
- Trigger: {{EVENT_OR_CONDITION}}
- Input: {{DATA_REQUIRED}}
- Processing: {{LOGIC_DESCRIPTION}}
- Output: {{RESULT_OR_EFFECT}}
- Constraints: {{PERFORMANCE_OR_SECURITY_REQUIREMENTS}}

## 6. System Invariants

1. Never: {{INVARIANT_1}}
2. Always: {{INVARIANT_2}}
3. Must: {{INVARIANT_3}}

## 7. Non-Functional Requirements

| Category | Requirement | Verification Method |
|----------|-------------|---------------------|
| Performance | {{PERF_REQUIREMENT}} | {{TEST_METHOD}} |
| Security | {{SEC_REQUIREMENT}} | {{TEST_METHOD}} |
| Reliability | {{REL_REQUIREMENT}} | {{TEST_METHOD}} |

## 8. Success Criteria

- [ ] {{CRITERION_1}}
- [ ] {{CRITERION_2}}
- [ ] {{CRITERION_3}}

## 9. Architecture Constraints

- Data Storage: {{STORAGE_CONSTRAINT}}
- API Style: {{API_CONSTRAINT}}
- Deployment: {{DEPLOY_CONSTRAINT}}
- Language: {{LANG_CONSTRAINT}}

## LLM Instructions

- Validate: Check all required_fields are present and non-empty
- Generate: Extract capabilities for architecture.md, entities for data_model.md
- Conflict: Flag if downstream artifacts contradict vision
- Context: This is the root of truth. All children must reference this file
