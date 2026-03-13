---
template_version: "1.0"
file_type: "architecture"
cascade_level: 1
required_fields:
  - parent_vision_ref
  - overview
  - responsibilities
  - components
  - boundaries
  - interfaces
  - constraints
cascade_children:
  - "acsd/data_model.md"
  - "**/acsd-module/architecture/index.md"
---

# Architecture: {{PROJECT_NAME}}

> Parent: {{PARENT_VISION_REF}}

## 1. Overview
{{One paragraph summary}}

## 2. Responsibilities
- {{RESP_1}} → implements `{{VISION_CAP_REF}}`
- {{RESP_2}} → implements `{{VISION_CAP_REF}}`
- {{RESP_3}} → implements `{{VISION_CAP_REF}}`

## 3. Components
- {{COMPONENT_A}} ({{type}}): {{responsibility}}
- {{COMPONENT_B}} ({{type}}): {{responsibility}}
- {{COMPONENT_C}} ({{type}}): {{responsibility}}

## 4. Boundaries

Allowed:
- {{COMP_A}} → {{COMP_B}}: via {{INTERFACE}}
- {{MODULE_X}} → {{MODULE_Y}}: via contract tests

Forbidden:
- Direct database access from controllers
- Circular dependencies between modules
- Implicit data sharing (no global state)

## 5. Interfaces (Public Contracts)
- `{{INTERFACE_1}}`: {{purpose}} | Input: {{IN}} | Output: {{OUT}} | Errors: {{ERR}}
- `{{INTERFACE_2}}`: {{purpose}} | Input: {{IN}} | Output: {{OUT}} | Errors: {{ERR}}

## 6. Data Flow
{{ENTITY_1}}: Owner={{MODULE}}, Readers={{LIST}}, Writers={{LIST}}
{{ENTITY_2}}: Owner={{MODULE}}, Readers={{LIST}}, Writers={{LIST}}

## 7. Constraints
- {{CONSTRAINT_1}} (Reason: {{WHY}}, Source: {{REF}})
- {{CONSTRAINT_2}} (Reason: {{WHY}}, Source: {{REF}})

## 8. ADR References
- {{ADR-XXX}}: {{TITLE}} → {{IMPACT}}
- {{ADR-YYY}}: {{TITLE}} → {{IMPACT}}

## Checklist
- [ ] parent_vision_ref exists
- [ ] Each responsibility links to vision capability
- [ ] Each component has type and responsibility
- [ ] At least one public interface defined
- [ ] No circular dependencies

## LLM Instructions
- Validate: Check required_fields, verify parent_vision_ref
- Generate: Extract interfaces for module/interface.md
- Conflict: Flag if module artifacts contradict boundaries
- Context: Read vision.md first, cover all capabilities
