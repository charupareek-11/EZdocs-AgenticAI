# Test Case Traceability Matrix & Execution Guide
## EZDocs Endorsement Management - User Stories 1455, 1705, 1817

---

## User Story 1455: Financial Lines - Excess Select Endorsements

### Acceptance Criteria → Test Case Mapping

| Acceptance Criteria | Description | Test IDs | Status | Coverage % |
|-------------------|-------------|----------|--------|-----------|
| **AC-1455-001** | Drop Down Endorsement form available in English (ZC-FLXS-256-C CW) | TC_1455_001, 021, 024 | ✓ | 100% |
| **AC-1455-002** | Drop Down Endorsement form available in French (ZC-FLXS-256-C FR) | TC_1455_001, 022, 024 | ✓ | 100% |
| **AC-1455-003** | DIC Endorsement form ZC-FLXS-11816 U/G available | TC_1455_008, 012, 025 | ✓ | 100% |
| **AC-1455-004** | Guaranteed Renewal Endorsement ZC-FLXS-11819 U available | TC_1455_007, 012, 024-025 | ✓ | 100% |
| **AC-1455-005** | Growing table accepts Policy Coverage (string) input | TC_1455_003, 004, 015 | ✓ | 100% |
| **AC-1455-006** | Growing table accepts Sublimit ($ amount) input | TC_1455_003, 015, 018-019 | ✓ | 100% |
| **AC-1455-007** | Growing table accepts Total Underlying sublimit input | TC_1455_003, 018-019 | ✓ | 100% |
| **AC-1455-008** | Multiple rows can be added to growing table | TC_1455_004, 020 | ✓ | 100% |
| **AC-1455-009** | DIC form accepts Lead DIC policy insurer name (alphanumeric) | TC_1455_005, 023, 028 | ✓ | 100% |
| **AC-1455-010** | DIC form accepts Lead DIC policy number (alphanumeric) | TC_1455_005, 029 | ✓ | 100% |
| **AC-1455-011** | DIC form accepts Lead DIC Limit of Liability ($ amount) | TC_1455_005, 024 | ✓ | 100% |
| **AC-1455-012** | DIC form accepts Other underlying DIC policies with multiple rows | TC_1455_006, 020, 025 | ✓ | 100% |
| **AC-1455-013** | Quote can be created after form entry | TC_1455_009, 024-025 | ✓ | 100% |
| **AC-1455-014** | Quote preview available in English | TC_1455_010, 012, 024 | ✓ | 100% |
| **AC-1455-015** | Quote preview available in French | TC_1455_011, 012, 024 | ✓ | 100% |
| **AC-1455-016** | All fields validate correctly in finalized document | TC_1455_012, 024 | ✓ | 100% |
| **AC-1455-017** | Binder can be created from approved quote | TC_1455_013, 024-025 | ✓ | 100% |
| **AC-1455-018** | Policy can be created from binder | TC_1455_014, 024-025 | ✓ | 100% |
| **AC-1455-019** | Empty growing table rows rejected with error | TC_1455_015 | ✓ | 100% |
| **AC-1455-020** | Invalid currency amounts rejected | TC_1455_016 | ✓ | 100% |
| **AC-1455-021** | Field length limits enforced | TC_1455_017 | ✓ | 100% |
| **AC-1455-022** | Minimum sublimit accepted ($1) | TC_1455_018 | ✓ | 100% |
| **AC-1455-023** | Maximum sublimit accepted ($999,999,999.99) | TC_1455_019 | ✓ | 100% |
| **AC-1455-024** | Growing table row limit enforced | TC_1455_020 | ✓ | 100% |
| **AC-1455-025** | Bilingual support: English coverage types | TC_1455_021 | ✓ | 100% |
| **AC-1455-026** | Bilingual support: French coverage types | TC_1455_022 | ✓ | 100% |
| **AC-1455-027** | Form dependency: DIC dependent fields | TC_1455_023 | ✓ | 100% |
| **AC-1455-028** | Multiple forms supported simultaneously | TC_1455_025 | ✓ | 100% |
| **AC-1455-029** | Send for Booking integration (1817) | TC_1455_026-027, TC_1817_* | ✓ | 100% |

**User Story 1455 Coverage: 100% (30 Test Cases)**

---

## User Story 1705: Financial Lines - Crime & PCL Fraudulent Impersonation Endorsements

### Acceptance Criteria → Test Case Mapping

| Acceptance Criteria | Description | Test IDs | Status | Coverage % |
|-------------------|-------------|----------|--------|-----------|
| **AC-1705-001** | English Crime form ZC 10827 U 0126 (No Callback) available | TC_1705_001, 013, 024 | ✓ | 100% |
| **AC-1705-002** | English Crime form ZC 10828 U 0126 (With Callback) available | TC_1705_002, 024 | ✓ | 100% |
| **AC-1705-003** | French Crime form ZC 10827 G 0126 (No Callback) available | TC_1705_003, 024 | ✓ | 100% |
| **AC-1705-004** | French Crime form ZC 10828 G 0126 (With Callback) available | TC_1705_004, 024 | ✓ | 100% |
| **AC-1705-005** | English PCL form ZC-PCL-11743 U 1225 (No Callback) available | TC_1705_005, 012, 025 | ✓ | 100% |
| **AC-1705-006** | English PCL form ZC-PCL-11744 U 1225 (With Callback) available | TC_1705_006, 025 | ✓ | 100% |
| **AC-1705-007** | French PCL form ZC-PCL-11743 G 1225 (No Callback) available | TC_1705_007, 025 | ✓ | 100% |
| **AC-1705-008** | French PCL form ZC-PCL-11744 G 1225 (With Callback) available | TC_1705_008, 025 | ✓ | 100% |
| **AC-1705-009** | Crime Item 2 (Limit of Liability) accepts CAD currency | TC_1705_009, 015, 020 | ✓ | 100% |
| **AC-1705-010** | Crime Item 4 (Deductible Amount) accepts CAD currency | TC_1705_010, 016, 020 | ✓ | 100% |
| **AC-1705-011** | PCL Limit of Liability field accepts CAD currency | TC_1705_011, 021 | ✓ | 100% |
| **AC-1705-012** | PCL Deductible field accepts CAD currency | TC_1705_012, 021 | ✓ | 100% |
| **AC-1705-013** | Crime Item 2 required field - cannot save blank | TC_1705_013 | ✓ | 100% |
| **AC-1705-014** | Crime Item 4 required field - cannot save blank | TC_1705_014 | ✓ | 100% |
| **AC-1705-015** | Crime Item 2 rejects non-numeric input | TC_1705_015 | ✓ | 100% |
| **AC-1705-016** | Crime rejects negative amounts | TC_1705_016 | ✓ | 100% |
| **AC-1705-017** | PCL rejects submission with blank fields | TC_1705_017 | ✓ | 100% |
| **AC-1705-018** | PCL enforces CAD-only currency | TC_1705_018 | ✓ | 100% |
| **AC-1705-019** | PCL Deductible cannot exceed Limit (business rule) | TC_1705_019 | ✓ | 100% |
| **AC-1705-020** | Crime minimum amount acceptance ($1) | TC_1705_020 | ✓ | 100% |
| **AC-1705-021** | Crime maximum amount acceptance ($999,999,999.99) | TC_1705_021 | ✓ | 100% |
| **AC-1705-022** | PCL decimal precision (2 decimals) | TC_1705_022 | ✓ | 100% |
| **AC-1705-023** | Callback/no-callback form variants selectable | TC_1705_023 | ✓ | 100% |
| **AC-1705-024** | Complete Crime workflow: Entry → Quote → Document → Binder → Policy | TC_1705_024 | ✓ | 100% |
| **AC-1705-025** | Complete PCL workflow: Entry → Quote → Document → Binder → Policy | TC_1705_025 | ✓ | 100% |
| **AC-1705-026** | Crime and PCL mixed submission support | TC_1705_026 | ✓ | 100% |
| **AC-1705-027** | Crime English to French preview switch | TC_1705_027 | ✓ | 100% |
| **AC-1705-028** | PCL English to French preview switch | TC_1705_028 | ✓ | 100% |

**User Story 1705 Coverage: 100% (28 Test Cases)**

---

## User Story 1817: Send for Booking Action Button

### Acceptance Criteria → Test Case Mapping

| Acceptance Criteria | Description | Test IDs | Status | Coverage % |
|-------------------|-------------|----------|--------|-----------|
| **AC-1817-001** | Send for Booking button visible on Binder tab | TC_1817_001, 002, 007-009 | ✓ | 100% |
| **AC-1817-002** | Send for Booking button enabled on active binder | TC_1817_002, 007 | ✓ | 100% |
| **AC-1817-003** | Send for Booking click initiates booking process | TC_1817_003, 016 | ✓ | 100% |
| **AC-1817-004** | Send for Booking disabled after policy creation | TC_1817_004 | ✓ | 100% |
| **AC-1817-005** | Umbrella LOB: Send for Booking hidden | TC_1817_005 | ✓ | 100% |
| **AC-1817-006** | Excess LOB: Send for Booking hidden | TC_1817_006 | ✓ | 100% |
| **AC-1817-007** | Financial Lines Public Select: Send for Booking enabled | TC_1817_007 | ✓ | 100% |
| **AC-1817-008** | General Property Domestic: Send for Booking enabled | TC_1817_008 | ✓ | 100% |
| **AC-1817-009** | General Liability Domestic: Send for Booking enabled | TC_1817_009 | ✓ | 100% |
| **AC-1817-010** | Received Property: Send for Booking on Policy tab | TC_1817_010 | ✓ | 100% |
| **AC-1817-011** | Energy Property Domestic: Send for Booking on Policy tab | TC_1817_011 | ✓ | 100% |
| **AC-1817-012** | Received Liability: Send for Booking on Policy tab | TC_1817_012 | ✓ | 100% |
| **AC-1817-013** | Duplicate booking prevention | TC_1817_013 | ✓ | 100% |
| **AC-1817-014** | Required field validation before booking | TC_1817_014 | ✓ | 100% |
| **AC-1817-015** | Cancelled binder: Send for Booking unavailable | TC_1817_015 | ✓ | 100% |
| **AC-1817-016** | Complete Binder → Booking → Policy flow | TC_1817_016 | ✓ | 100% |
| **AC-1817-017** | Multiple endorsements: Send for Booking includes all forms | TC_1817_017 | ✓ | 100% |
| **AC-1817-018** | Rescinded policy: Send for Booking button removed | TC_1817_018 | ✓ | 100% |
| **AC-1817-019** | Booking completes within performance timeout (30s) | TC_1817_019 | ✓ | 100% |
| **AC-1817-020** | Concurrent booking requests handled correctly | TC_1817_020 | ✓ | 100% |

**User Story 1817 Coverage: 100% (20 Test Cases)**

---

## Execution Priority Map

### Critical Path - Day 1-2 (Must Pass First)

```
Phase 1: Form Availability & Access
├─ TC_1455_001-008    [Day 1: Excess Select Forms]
├─ TC_1705_001-008    [Day 1: Crime & PCL Forms]
└─ TC_1817_001, 005-012 [Day 2: Send for Booking Config]

Dependencies: NONE (foundation tests)
Blockers: Form visibility failures block all downstream tests
```

### Critical Path - Day 3-4 (Field Validation)

```
Phase 2: Data Entry & Field Validation
├─ TC_1455_003-020    [Day 3: 1455 Fields & Validation]
├─ TC_1705_009-023    [Day 3: 1705 Fields & Validation]
└─ TC_1817_002-004, 013-015 [Day 4: Booking Button Logic]

Dependencies: Phase 1 (forms must be visible)
Blockers: Field validation failures block workflow tests
```

### Critical Path - Day 5-7 (Workflows & Integration)

```
Phase 3: End-to-End Workflows
├─ TC_1455_021-027    [Day 5-6: 1455 Workflows]
├─ TC_1705_024-028    [Day 6-7: 1705 Workflows]
└─ TC_1817_016-020    [Day 7: 1817 Booking Workflows]

Dependencies: Phase 1 & 2 (forms & fields must work)
Blockers: None (integration tests verify full system)
```

---

## Test Execution Checklist

### Pre-Execution Setup
- [ ] Test environment ready (EZDocs staging/UAT)
- [ ] Test data prepared (dummy submissions, forms loaded)
- [ ] User accounts created with appropriate LOB access
- [ ] Bilingual browser/locale configured (EN & FR)
- [ ] ZIP booking system mock/test endpoint ready
- [ ] ODS duplicate check system available

### Test Execution Log Template

```
Date: ___________
Tester: ___________
Test ID: ___________
Test Case: ___________
Result: [ ] PASS [ ] FAIL [ ] SKIP [ ] BLOCKED
Notes: ___________
Defect IDs: ___________
```

### Defect Escalation

| Severity | Impact | Resolution | SLA |
|----------|--------|-----------|-----|
| **Critical** | Form not visible or cannot submit | Immediate escalation to dev | 2 hours |
| **High** | Field validation fails or data lost | Same-day fix | Same day |
| **Medium** | UI inconsistency or minor logic error | Next sprint | 5 days |
| **Low** | Cosmetic or non-blocking issue | Backlog | Next sprint |

---

## Test Coverage Summary

### By User Story

```
User Story 1455: 30 Tests
├─ Positive:     14 (47%)
├─ Negative:      8 (27%)
├─ Boundary:      4 (13%)
└─ Integration:   4 (13%)

User Story 1705: 28 Tests
├─ Positive:     12 (43%)
├─ Negative:      8 (29%)
├─ Boundary:      3 (11%)
└─ Integration:   5 (18%)

User Story 1817: 20 Tests
├─ Positive:     12 (60%)
├─ Negative:      3 (15%)
├─ Boundary:      2 (10%)
└─ Integration:   3 (15%)

TOTAL: 78 Tests (100% Acceptance Criteria Coverage)
```

### By Test Type

```
Positive Tests (Successful Path):        38 tests (49%)
├─ Form availability & accessibility
├─ Data entry acceptance
├─ Workflow progression
├─ Document generation
└─ Language support

Negative Tests (Error Handling):         19 tests (24%)
├─ Required field validation
├─ Invalid data rejection
├─ Currency enforcement
├─ Business logic constraints
└─ Duplicate prevention

Boundary Tests (Edge Cases):              9 tests (12%)
├─ Amount limits ($1 - $999,999,999.99)
├─ Field length limits
├─ Growing table row limits
├─ Decimal precision
└─ Performance timeouts

Integration Tests (Cross-Functional):    12 tests (15%)
├─ Form dependencies
├─ Multi-form workflows
├─ Language switching
├─ Booking process flow
└─ Concurrent operations
```

### By Priority

```
HIGH Priority:    129 tests (81%)
├─ Critical workflows
├─ Form functionality
├─ Required field validation
└─ Booking integration

MEDIUM Priority:   31 tests (19%)
├─ Boundary conditions
├─ Concurrent operations
├─ Performance requirements
└─ Edge cases
```

---

## Test Result Report Template

### Summary Statistics
- Total Test Cases: ___
- Passed: ___ (___%)
- Failed: ___ (___%)
- Skipped: ___ (___%)
- Blocked: ___ (___%)

### Failed Test Cases
| Test ID | Title | Root Cause | Status |
|---------|-------|-----------|--------|
| | | | |

### Known Issues / Deferred Tests
| Test ID | Reason | Planned Date |
|---------|--------|--------------|
| | | |

### Sign-Off
- QA Lead: __________ Date: __________
- Product Owner: __________ Date: __________
- Dev Lead: __________ Date: __________

---

## Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-05-25 | Test Case Generator | Initial generation - 78 test cases |
| | | | |

*Last Updated: May 25, 2026*
*Repository: /workspaces/AgenticAIEZDocs/OptimusCore/04_DesignStudio/*
