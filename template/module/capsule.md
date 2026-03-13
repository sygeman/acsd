---
template_version: "1.0"
file_type: "module_capsule"
cascade_level: 2
required_fields:
  - module_name
  - parent_architecture_ref
  - domain_concepts
  - invariants
  - operations
cascade_children:
  - "interface.md"
---

# Capsule: {{MODULE_NAME}}

> Parent Architecture: {{PARENT_ARCHITECTURE_REF}}

## 1. Domain Concepts

| Concept | Description | Invariant |
|---------|-------------|-----------|
| {{CONCEPT_1}} | {{DESC}} | {{INVARIANT}} |
| {{CONCEPT_2}} | {{DESC}} | {{INVARIANT}} |
| {{CONCEPT_3}} | {{DESC}} | {{INVARIANT}} |

## 2. Invariants

1. Never: {{INVARIANT_1}}
2. Always: {{INVARIANT_2}}
3. Must: {{INVARIANT_3}}

## 3. Operations

| Operation | Input | Output | Errors | Side Effects |
|-----------|-------|--------|--------|--------------|
| {{OP_1}} | {{INPUT}} | {{OUTPUT}} | {{ERRORS}} | {{EFFECTS}} |
| {{OP_2}} | {{INPUT}} | {{OUTPUT}} | {{ERRORS}} | {{EFFECTS}} |
| {{OP_3}} | {{INPUT}} | {{OUTPUT}} | {{ERRORS}} | {{EFFECTS}} |

## 4. Business Rules

- {{RULE_1}}: {{DESCRIPTION}}
- {{RULE_2}}: {{DESCRIPTION}}
- {{RULE_3}}: {{DESCRIPTION}}

## 5. State Transitions

| Entity | From State | To State | Trigger | Guard |
|--------|------------|----------|---------|-------|
| {{ENTITY}} | {{STATE_A}} | {{STATE_B}} | {{OP_NAME}} | {{CONDITION}} |

## Checklist

- [ ] module_name matches parent architecture
- [ ] parent_architecture_ref exists
- [ ] Each concept has at least one invariant
- [ ] Each operation has input, output, and errors defined
- [ ] Invariants are testable (Never/Always/Must format)

## LLM Instructions

- Validate: Check all concepts have invariants, operations are complete
- Generate: Extract operations for interface.md with DTOs
- Conflict: Flag if operations contradict domain invariants
- Context: Read module architecture.md first, ensure components match concepts
