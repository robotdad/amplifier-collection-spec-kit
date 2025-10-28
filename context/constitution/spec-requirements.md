# Specification Requirements

**What makes a valid, high-quality specification**

---

## Mandatory Sections

Every specification MUST include:

1. **User Scenarios & Testing** - Prioritized user journeys (P1, P2, P3)
2. **Requirements** - Functional requirements with IDs (FR-001, FR-002, etc.)
3. **Success Criteria** - Measurable outcomes (SC-001, SC-002, etc.)
4. **Constitutional Compliance** - Validation against all 8 principles

---

## Clarity Requirements

### Use [NEEDS CLARIFICATION] Markers

Mark any ambiguity explicitly:

```markdown
## Authentication

Users authenticate via [NEEDS CLARIFICATION: method not specified - OAuth2, JWT, or both?]

Token expiry: [NEEDS CLARIFICATION: duration not specified]
```

**Purpose**: Force explicit resolution before implementation.

### No Implementation Details

Specifications describe WHAT and WHY, not HOW:

- ❌ "Use bcrypt for password hashing"
- ✅ "System MUST securely hash passwords"

- ❌ "Implement using Express middleware"
- ✅ "API MUST authenticate requests before processing"

Implementation details belong in plans, not specs.

---

## Testability Requirements

### Every Requirement Must Be Testable

**Good** (testable):
- "System MUST validate email format"
- "API MUST return 401 for invalid tokens"
- "Users MUST be able to reset passwords"

**Bad** (not testable):
- "System should be user-friendly"
- "API should perform well"
- "Users might want to customize settings"

### Acceptance Scenarios Required

Each user story needs Given/When/Then scenarios:

```markdown
**Acceptance Scenarios**:
1. **Given** user has valid credentials
   **When** they submit login form
   **Then** system returns authentication token

2. **Given** user has invalid credentials
   **When** they submit login form
   **Then** system returns 401 error with helpful message
```

---

## Completeness Requirements

### Must Answer These Questions

- **What** are we building? (Clear feature description)
- **Why** does it matter? (User value, problem solved)
- **Who** will use it? (User personas, use cases)
- **When** is it successful? (Measurable criteria)
- **What** are the boundaries? (In scope / out of scope)

### Must NOT Include

- Implementation technology choices (that's planning phase)
- Specific library selections (unless constitutional requirement)
- Code structure decisions (that's implementation phase)
- Timeline estimates (that's project management)

---

## Constitutional Alignment

### Every Spec Must Pass All Gates

- [ ] **Library-first**: Designed as standalone library?
- [ ] **CLI interface**: Text in/out protocol defined?
- [ ] **Test-first**: Test strategy included?
- [ ] **Integration testing**: Contract tests planned?
- [ ] **Simplicity**: Minimal approach, no future-proofing?
- [ ] **Anti-abstraction**: Direct framework usage?
- [ ] **Observability**: Text-based I/O specified?
- [ ] **Versioning**: Versioning strategy defined?

**If any fail**: Specification is incomplete or violates constitution.

---

## Quality Standards

### Specification Quality Indicators

**High Quality**:
- All requirements testable and measurable
- User scenarios prioritized and independently testable
- Ambiguities marked with [NEEDS CLARIFICATION]
- Constitutional compliance validated
- Edge cases identified
- Success criteria specific and measurable

**Low Quality**:
- Vague requirements ("should be good")
- No test scenarios
- Hidden ambiguities (not marked)
- Constitutional violations
- Missing edge cases
- Success criteria too general

---

## Review Process

### Specification Review Checklist

Before advancing to planning:

**Completeness**:
- [ ] All mandatory sections present
- [ ] User scenarios prioritized (P1, P2, P3)
- [ ] All requirements have IDs
- [ ] Success criteria measurable
- [ ] Edge cases identified

**Clarity**:
- [ ] No ambiguities OR marked with [NEEDS CLARIFICATION]
- [ ] All terms defined
- [ ] Consistent terminology
- [ ] Examples provided where helpful

**Constitutional**:
- [ ] All 8 principles validated
- [ ] Violations documented and justified
- [ ] Simplicity gates passed

**Testability**:
- [ ] All requirements testable
- [ ] Acceptance scenarios defined
- [ ] Test strategy clear

**Approval**:
- [ ] spec-critic reviewed
- [ ] constitutional-guardian validated
- [ ] User approved
- [ ] Ready for planning phase

---

**A specification is complete when implementation can proceed without additional requirement clarification.**

**Document Version**: 1.0
**Last Updated**: 2025-10-27
