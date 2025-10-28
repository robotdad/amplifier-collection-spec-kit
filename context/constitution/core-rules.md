# Constitutional Core Rules

**Fundamental principles governing all specification-driven development**

---

## I. Library-First Principle

**Every feature is developed as a standalone library.**

### Requirements
- Libraries must be self-contained and independently testable
- Clear purpose required - no organizational-only libraries
- Libraries must be usable outside the original context
- Documentation must explain the library's purpose and usage

### Rationale
Libraries enforce modularity, enable reuse, and ensure features can be tested in isolation.

---

## II. CLI Interface Requirement

**Every library exposes functionality via command-line interface.**

### Requirements
- Text in/text out protocol: stdin/args → stdout, errors → stderr
- Support JSON and human-readable output formats
- Exit codes follow Unix conventions (0 = success, non-zero = error)
- Help documentation via `--help` flag

### Rationale
CLI interfaces are language-agnostic, testable, composable, and enable automation.

---

## III. Test-First Development (NON-NEGOTIABLE)

**TDD is mandatory: Tests written → User approved → Tests fail → Then implement.**

### Requirements
- Write tests BEFORE implementation
- Tests must fail initially (proving they test something)
- User reviews and approves test strategy
- Red-Green-Refactor cycle strictly followed
- No implementation without corresponding tests

### Rationale
Test-first ensures requirements are clear, testable, and implementation meets specifications.

---

## IV. Integration Testing Priority

**Integration tests take priority over unit tests.**

### Focus Areas
- Library contract tests (public API)
- Contract changes (breaking change detection)
- Inter-service communication (if applicable)
- Shared schemas and data models

### Testing Pyramid
- 60% unit tests (logic verification)
- 30% integration tests (contract verification)
- 10% end-to-end tests (workflow validation)

### Rationale
Integration tests catch architectural issues unit tests miss. Contracts must be validated.

---

## V. Simplicity Gates

**Ruthless simplicity is enforced through explicit gates.**

### Constraints
- Maximum 3 projects per repository
- No future-proofing or speculative features
- YAGNI principle: You Aren't Gonna Need It
- Each abstraction must justify its existence
- Prefer duplication over wrong abstraction

### Validation
Every specification must answer:
- Is this the simplest approach that works?
- Are we building only what's needed now?
- Can we remove complexity without losing value?

### Rationale
Complexity is the enemy of maintainability. Start minimal, grow as proven necessary.

---

## VI. Anti-Abstraction Rule

**Use frameworks and libraries directly - don't wrap them unnecessarily.**

### Requirements
- Direct usage of external libraries (no adapter layers)
- Wrappers only when absolutely necessary (and justified)
- Prefer framework idioms over custom patterns
- Document why wrappers exist when used

### Rationale
Unnecessary abstractions add complexity, reduce clarity, and create maintenance burden.

---

## VII. Observability Requirement

**All libraries must be debuggable via text I/O.**

### Requirements
- Text-based I/O ensures debuggability
- Structured logging for complex operations
- Error messages must be actionable
- State changes must be observable

### Rationale
Text I/O is inspectable, diffable, and works with standard Unix tools.

---

## VIII. Versioning & Breaking Changes

**Semantic versioning with explicit breaking change management.**

### Requirements
- MAJOR.MINOR.BUILD format
- Breaking changes increment MAJOR version
- Deprecation notices before removal
- Migration guides for breaking changes

### Rationale
Clear versioning prevents unexpected breakage and enables gradual migration.

---

## Constitutional Compliance

### Validation

Every specification MUST validate against ALL eight principles:
- [ ] Library-first principle applied
- [ ] CLI interface defined
- [ ] Test-first approach planned
- [ ] Integration testing strategy included
- [ ] Simplicity gates passed
- [ ] No unnecessary abstractions
- [ ] Observability ensured
- [ ] Versioning strategy defined

### Enforcement

**At specification phase**:
- constitutional-guardian agent validates compliance
- spec-critic reviews against constitution
- [NEEDS CLARIFICATION] marks violations

**At implementation phase**:
- Tests must validate constitutional requirements
- Code review checks compliance
- CI/CD enforces gates

---

## Amendments

The constitution can be amended when:
- Principles conflict with new requirements
- Better approaches discovered
- Team consensus on improvements

### Amendment Process
1. Propose amendment with rationale
2. Document impact on existing work
3. Team reviews and approves
4. Update all affected specifications
5. Create migration plan if needed

---

**This constitution supersedes all other development practices. Compliance is mandatory.**

**Version**: 1.0.0
**Ratified**: 2025-10-27
**Last Amended**: 2025-10-27
