---
template_version: "1.0"
file_type: "module_architecture"
cascade_level: 2
required_fields:
  - module_name
  - parent_architecture_ref
  - parent_data_model_ref
  - responsibilities
  - components
  - dependencies
  - boundaries
cascade_children:
  - "capsule.md"
  - "interface.md"
---

# Module Architecture: {{MODULE_NAME}}

> Parent Architecture: {{PARENT_ARCHITECTURE_REF}}
> Parent Data Model: {{PARENT_DATA_MODEL_REF}}

## 1. Overview
{{One paragraph summary of module purpose and scope}}

## 2. Responsibilities
- {{RESP_1}} → implements `{{GLOBAL_CAPABILITY_REF}}`
- {{RESP_2}} → implements `{{GLOBAL_CAPABILITY_REF}}`
- {{RESP_3}} → implements `{{GLOBAL_CAPABILITY_REF}}`

## 3. Components
- {{COMPONENT_A}} ({{type}}): {{responsibility}}
- {{COMPONENT_B}} ({{type}}): {{responsibility}}
- {{COMPONENT_C}} ({{type}}): {{responsibility}}

## 4. Dependencies

### Inbound (Who calls this module)
- {{MODULE_X}}: via `{{INTERFACE_NAME}}`
- {{MODULE_Y}}: via `{{INTERFACE_NAME}}`

### Outbound (This module calls)
- {{MODULE_A}}: via `{{INTERFACE_NAME}}`
- {{MODULE_B}}: via `{{INTERFACE_NAME}}`

## 5. Boundaries

Allowed:
- {{COMP_A}} → {{COMP_B}}: internal call
- This module → {{OTHER_MODULE}}: via public interface only

Forbidden:
- Direct database access from other modules
- Circular dependencies with {{MODULE_X}}, {{MODULE_Y}}
- Bypassing interface for internal components

## 6. Data Ownership

| Entity | Access | Operations |
|--------|--------|------------|
| {{ENTITY_1}} | Owner | Create, Read, Update, Delete |
| {{ENTITY_2}} | Read-only | Read only via {{OWNER_MODULE}} interface |

## 7. Constraints

- {{CONSTRAINT_1}} (Reason: {{WHY}}, Source: {{ADR_REF|ARCH_REF}})
- {{CONSTRAINT_2}} (Reason: {{WHY}}, Source: {{REF}})

## Checklist

- [ ] module_name is unique in project
- [ ] parent_architecture_ref exists
- [ ] parent_data_model_ref exists
- [ ] Each responsibility links to global capability
- [ ] Dependencies are explicit (inbound and outbound)
- [ ] Data ownership matches global data_model.md

## LLM Instructions

- Validate: Check required_fields, verify parent refs exist
- Generate: Extract domain concepts for capsule.md, operations for interface.md
- Conflict: Flag if dependencies violate global architecture boundaries
- Context: Read global architecture.md and data_model.md first
