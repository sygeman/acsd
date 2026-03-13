---
template_version: "1.0"
file_type: "data_model"
cascade_level: 1
required_fields:
  - parent_vision_ref
  - parent_architecture_ref
  - entities
  - relationships
  - ownership
  - constraints
cascade_children:
  - "**/acsd-module/capsule.md"
  - "**/acsd-module/interface.md"
---

# Data Model: {{PROJECT_NAME}}

> Parent Vision: {{PARENT_VISION_REF}}
> Parent Architecture: {{PARENT_ARCHITECTURE_REF}}

## 1. Entities

| Entity | Description | Owner Module | Fields |
|--------|-------------|--------------|--------|
| {{ENTITY_1}} | {{DESC}} | {{MODULE}} | {{FIELD_LIST}} |
| {{ENTITY_2}} | {{DESC}} | {{MODULE}} | {{FIELD_LIST}} |
| {{ENTITY_3}} | {{DESC}} | {{MODULE}} | {{FIELD_LIST}} |

## 2. Relationships

| From | To | Type | Constraints |
|------|-----|------|-------------|
| {{ENTITY_A}} | {{ENTITY_B}} | {{one-to-many|many-to-many|one-to-one}} | {{CONSTRAINTS}} |
| {{ENTITY_C}} | {{ENTITY_D}} | {{type}} | {{CONSTRAINTS}} |

## 3. Data Ownership

| Entity | Owner | Read Access | Write Access | Validation Rules |
|--------|-------|-------------|--------------|------------------|
| {{ENTITY_1}} | {{MODULE}} | {{READERS}} | {{WRITERS}} | {{RULES}} |
| {{ENTITY_2}} | {{MODULE}} | {{READERS}} | {{WRITERS}} | {{RULES}} |

Rule: Only owner module can write. Others must use public interfaces.

## 4. Constraints

- {{CONSTRAINT_1}} (e.g., All timestamps in UTC)
- {{CONSTRAINT_2}} (e.g., Soft delete required for all entities)
- {{CONSTRAINT_3}} (e.g., No direct SQL, use repository pattern)

## 5. State Management

| State Type | Storage | Sync Strategy | Cache Policy |
|------------|---------|---------------|--------------|
| {{STATE_1}} | {{SQLite|Memory|File}} | {{SYNC}} | {{CACHE}} |
| {{STATE_2}} | {{STORAGE}} | {{SYNC}} | {{CACHE}} |

## Checklist

- [ ] parent_vision_ref exists
- [ ] parent_architecture_ref exists
- [ ] Each entity has an owner module
- [ ] Each relationship has type and constraints
- [ ] Ownership rules are explicit

## LLM Instructions

- Validate: Check all entities have owners, relationships are valid
- Generate: Extract DTOs for module/interface.md, entities for capsule.md
- Conflict: Flag if code uses unowned entities or violates ownership rules
- Context: Read architecture.md first, ensure components match data ownership
