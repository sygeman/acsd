---
template_version: "1.0"
file_type: "module_interface"
cascade_level: 3
required_fields:
  - module_name
  - parent_capsule_ref
  - operations
  - dtos
  - errors
  - invariants
cascade_children:
  - "../tests/contract/*.test.ts"
  - "../src/*.ts"
---

# Interface: {{MODULE_NAME}}

> Parent Capsule: {{PARENT_CAPSULE_REF}}

## 1. Operations

| Operation | Method | Input | Output | Errors | Idempotent |
|-----------|--------|-------|--------|--------|------------|
| {{OP_1}} | {{POST|GET|PUT|DELETE}} | `{{INPUT_DTO}}` | `{{OUTPUT_DTO}}` | `{{ERROR_CODES}}` | {{yes|no}} |
| {{OP_2}} | {{METHOD}} | `{{INPUT}}` | `{{OUTPUT}}` | `{{ERRORS}}` | {{yes|no}} |
| {{OP_3}} | {{METHOD}} | `{{INPUT}}` | `{{OUTPUT}}` | `{{ERRORS}}` | {{yes|no}} |

## 2. DTOs

### {{DTO_NAME_1}}
| Field | Type | Required | Description | Validation |
|-------|------|----------|-------------|------------|
| {{FIELD_1}} | {{TYPE}} | {{yes|no}} | {{DESC}} | {{RULE}} |
| {{FIELD_2}} | {{TYPE}} | {{yes|no}} | {{DESC}} | {{RULE}} |

### {{DTO_NAME_2}}
| Field | Type | Required | Description | Validation |
|-------|------|----------|-------------|------------|
| {{FIELD}} | {{TYPE}} | {{yes|no}} | {{DESC}} | {{RULE}} |

## 3. Errors

| Code | Message | When | Recovery |
|------|---------|------|----------|
| {{CODE_1}} | {{MESSAGE}} | {{CONDITION}} | {{ACTION}} |
| {{CODE_2}} | {{MESSAGE}} | {{CONDITION}} | {{ACTION}} |
| {{CODE_3}} | {{MESSAGE}} | {{CONDITION}} | {{ACTION}} |

## 4. Invariants

1. Never: {{INVARIANT_1}}
2. Always: {{INVARIANT_2}}
3. Must: {{INVARIANT_3}}

## 5. Rate Limits & Quotas

| Operation | Limit | Window | Behavior on Exceed |
|-----------|-------|--------|-------------------|
| {{OP_1}} | {{N}} requests | {{TIME}} | {{429|queue|reject}} |
| {{OP_2}} | {{N}} requests | {{TIME}} | {{BEHAVIOR}} |

## Checklist

- [ ] module_name matches parent capsule
- [ ] parent_capsule_ref exists
- [ ] Each operation has input DTO, output DTO, and errors
- [ ] Each DTO has fields with types and validation rules
- [ ] Each error code has a clear condition and recovery action
- [ ] Invariants are testable (Never/Always/Must format)

## LLM Instructions

- Validate: Check all operations have DTOs, errors are documented
- Generate: Create contract tests from operations, generate implementation stubs
- Conflict: Flag if implementation misses operations or violates invariants
- Context: Read capsule.md first, ensure all operations are covered
