# Quick Reference Guide - Test Case Execution
## EZDocs Endorsement Management UI Testing

---

## Test File Locations

```
📁 /workspaces/AgenticAIEZDocs/OptimusCore/04_DesignStudio/
├── EZ_Comprehensive_TestCases.csv ................... Main test cases (160 cases)
├── TEST_CASE_GENERATION_REPORT.md .................. Detailed generation report
├── TRACEABILITY_MATRIX.md .......................... AC mapping & priority
└── QUICK_REFERENCE.md (this file) .................. Quick lookup guide
```

---

## User Story Quick Overview

### 1455: Excess Select Endorsements
**LOB:** Financial Lines | **Product:** Excess Select  
**Forms:** Drop Down (256), DIC (11816-11817), Guaranteed Renewal (11819)  
**Tests:** 30 | **Acceptance Criteria:** 29 | **Coverage:** 100%

**Key Scenarios:**
- Growing table management (Policy Coverage, Sublimit, Total Underlying)
- DIC Lead & Underlying policy information
- Bilingual form support (EN/FR)
- Quote → Binder → Policy workflow
- Send for Booking integration

---

### 1705: Crime & PCL Fraudulent Impersonation
**LOB:** Financial Lines | **Products:** Crime, PCL (Private Company Select)  
**Forms:** Crime (10827-10828 EN/FR), PCL (11743-11744 EN/FR)  
**Tests:** 28 | **Acceptance Criteria:** 28 | **Coverage:** 100%

**Key Scenarios:**
- Crime & PCL variants (with/without callback)
- Limit of Liability field (CAD currency)
- Deductible Amount field (CAD currency)
- Required field validation
- Negative amount rejection
- Bilingual preview switching
- Complete E2E workflows

---

### 1817: Send for Booking Action Button
**Feature:** Send for Booking button on Binder/Policy tabs  
**Tests:** 20 | **Acceptance Criteria:** 20 | **Coverage:** 100%

**LOBs Enabled (Binder tab):**
- ✓ Financial Lines - Public Select
- ✓ General Property - Domestic & Produced Intl
- ✓ General Liability - Domestic
- ✓ Energy Property - Domestic

**LOBs Enabled (Policy tab):**
- ✓ Received Property
- ✓ Received Liability

**LOBs Hidden:**
- ✗ Umbrella (Send for Booking hidden)
- ✗ Excess (Send for Booking hidden)

---

## Test Execution Quick Start

### Step 1: Pre-Flight Check (5 mins)
- [ ] EZDocs application accessible
- [ ] Can login with test user account
- [ ] Financial Lines LOB visible
- [ ] Bilingual interface switchable (EN ↔ FR)
- [ ] Test data available (can create submissions)

### Step 2: Start with Priority 1 Tests (Critical Path)

**Day 1: Form Visibility**
```
TC_1455_001 → ZC-FLXS-256-C CW/FR visible
TC_1455_008 → ZC-FLXS-11816 U/G visible
TC_1455_007 → ZC-FLXS-11819 U visible
TC_1705_001-008 → Crime & PCL forms visible
TC_1817_001 → Send for Booking button visible
```

**Day 2-3: Field Validation**
```
TC_1455_003 → Growing table accepts inputs
TC_1455_015 → Empty rows rejected
TC_1705_009-012 → Amount fields accept CAD
TC_1705_013-016 → Required field validation
TC_1817_002-003 → Button state transitions
```

**Day 4-5: End-to-End Workflows**
```
TC_1455_024 → Complete 1455 workflow
TC_1705_024-025 → Complete 1705 workflows
TC_1817_016 → Complete booking workflow
```

### Step 3: Report Results

Use format:
```
Test ID: TC_1455_001
Status: [PASS / FAIL / SKIP / BLOCKED]
Result: "Form ZC-FLXS-256-C CW visible and selectable"
Defects: [List any defect IDs]
```

---

## Common Test Data Needed

### Form Fill Values (Can Use for Multiple Tests)

**Currency Amounts (CAD for 1705, no currency for 1455):**
```
Valid:     $50,000     $10,000.50    $1,234,567.89
Boundary:  $1          $0.01         $999,999,999.99
Invalid:   -$50,000    ABC           !@#$%
```

**Text Values:**
```
Insurer Name:    "ABC Insurance Ltd"
Policy Number:   "POL123456789"
Coverage Type:   Various from dropdown
```

**Growing Table Data (1455):**
```
Row 1: Policy Coverage = "Commercial General Liability"
       Sublimit = "$100,000"
       Total Underlying = "$500,000"

Row 2: Policy Coverage = "Property Coverage"
       Sublimit = "$250,000"
       Total Underlying = "$1,000,000"
```

---

## Test Case Lookup by Scenario

### "I need to test form visibility"
```
→ TC_1455_001-008
→ TC_1705_001-008
→ TC_1817_001, 005-012
```

### "I need to test field validation"
```
→ TC_1455_009, 015-020, 028-030
→ TC_1705_009-023
→ TC_1817_002-004, 013-015
```

### "I need to test negative scenarios"
```
→ TC_1455_015-020, 028-030
→ TC_1705_013-019
→ TC_1817_013-015
```

### "I need to test complete workflows"
```
→ TC_1455_024-025
→ TC_1705_024-026
→ TC_1817_016-020
```

### "I need to test bilingual support"
```
→ TC_1455_010-011, 021-022
→ TC_1705_027-028
```

### "I need to test Send for Booking"
```
→ TC_1817_001-020
→ TC_1455_026-027 (integration)
```

---

## Success Criteria by Test Type

### ✓ POSITIVE Test PASS Criteria
- [x] System accepts valid input
- [x] Data saves successfully
- [x] UI responds without errors
- [x] Confirmation/success message displays
- [x] Data persists on reload

### ✗ NEGATIVE Test PASS Criteria
- [x] System rejects invalid input
- [x] Error message displayed
- [x] Form does NOT save invalid data
- [x] User can correct and resubmit
- [x] No unexpected behavior (no crash)

### ↔ BOUNDARY Test PASS Criteria
- [x] System accepts minimum valid value
- [x] System accepts maximum valid value
- [x] System rejects values beyond limits
- [x] Correct error message on rejection
- [x] Rounding handled consistently

### 🔗 INTEGRATION Test PASS Criteria
- [x] Data flows through complete workflow
- [x] No data loss between stages
- [x] Dependencies work correctly
- [x] Cross-form interactions work
- [x] Multiple scenarios can coexist

---

## Defect Severity Guide

### CRITICAL 🔴 (Fix Immediately)
```
Examples:
- Form cannot be added to submission
- Data entered cannot be saved
- Quote cannot be generated
- Send for Booking button completely missing
- System crash/500 error
```

### HIGH 🟠 (Fix Today)
```
Examples:
- Field validation not working
- Required field not enforced
- Invalid data accepted
- Button disabled when should be enabled
- Booking not sent to ZIP system
```

### MEDIUM 🟡 (Fix This Sprint)
```
Examples:
- UI inconsistency
- Non-critical business logic error
- Minor field label issue
- Confusing error message
- Performance slow but acceptable
```

### LOW 🟢 (Fix When Available)
```
Examples:
- Typo in label
- Cosmetic UI issue
- Enhancement request
- Non-blocking workaround exists
```

---

## Common Issues & Troubleshooting

### Issue: Form not showing in search results
**Check:**
- [ ] Form number entered correctly (copy-paste to verify)
- [ ] Language setting matches form (EN forms have U suffix, FR have G)
- [ ] Form has been loaded into system
- [ ] Filters/search not restricting results

### Issue: Currency field not accepting decimals
**Check:**
- [ ] Using period (.) not comma (,) for decimals
- [ ] Entering numbers only (remove $ symbol if system adds it)
- [ ] Not exceeding 2 decimal places in 1705 tests
- [ ] Amount is positive

### Issue: Growing table won't add rows
**Check:**
- [ ] First row is complete and valid
- [ ] Clicking "Add Row" button (not elsewhere)
- [ ] Browser JavaScript enabled
- [ ] Not at maximum row limit (100)

### Issue: Quote preview shows wrong language
**Check:**
- [ ] Selected correct language toggle
- [ ] Browser language setting matches selection
- [ ] French forms added for French preview
- [ ] Clearing browser cache if stuck

### Issue: Send for Booking button not clickable
**Check:**
- [ ] On correct tab (Binder vs Policy per LOB config)
- [ ] Binder/Policy is in active state (not cancelled)
- [ ] No required fields are blank
- [ ] Not already sent for booking (duplicate check)

---

## Test Execution Time Estimates

| Phase | Tests | Est. Time | Notes |
|-------|-------|-----------|-------|
| **Phase 1: Availability** | 20 tests | 2-3 hours | Quick smoke tests |
| **Phase 2: Validation** | 27 tests | 4-5 hours | Data entry testing |
| **Phase 3: Workflows** | 22 tests | 5-6 hours | End-to-end scenarios |
| **Phase 4: Boundary** | 9 tests | 1-2 hours | Edge cases |
| **Total** | **78 tests** | **12-16 hours** | ~2 business days per tester |

---

## Test Status Tracking

### Daily Standup Template
```
Tests Run Today: ___/160
Passed: ___ ✓
Failed: ___ ✗
Blocked: ___ 🔒
Remaining: ___

Blockers:
- 

Defects Found:
- 

Today's Plan:
- 
```

### Weekly Rollup Template
```
Week of: __________

Summary:
- Total Tests Run: __/160 (___%)
- Passed: ___ (___%)
- Failed: ___ (___%)
- Blocked: ___ (___%)

By User Story:
- 1455: _/30 (___%) ✓ / ✗ / 🔒
- 1705: _/28 (___%) ✓ / ✗ / 🔒
- 1817: _/20 (___%) ✓ / ✗ / 🔒

Critical Issues:
1. 
2. 
3. 

Next Week Plan:
- 
```

---

## Acceptance Criteria Checklist

### User Story 1455 (Check All = 100% Coverage)
- [ ] Drop Down Endorsement EN visible
- [ ] Drop Down Endorsement FR visible
- [ ] DIC Endorsement forms visible
- [ ] Guaranteed Renewal visible
- [ ] Growing table entries accepted
- [ ] Policy Coverage field works
- [ ] Sublimit field works
- [ ] Total Underlying field works
- [ ] Multiple table rows work
- [ ] DIC Lead policy info accepted
- [ ] DIC Underlying policies accepted
- [ ] Quote creation works
- [ ] English preview works
- [ ] French preview works
- [ ] Document fields validate
- [ ] Binder creation works
- [ ] Policy creation works
- [ ] Empty rows rejected
- [ ] Invalid amounts rejected
- [ ] Field length limits enforced
- [ ] Minimum amounts accepted
- [ ] Maximum amounts accepted
- [ ] Row limits enforced
- [ ] English coverage types work
- [ ] French coverage types work
- [ ] Form dependencies work
- [ ] Multiple forms supported
- [ ] Send for Booking integrated (1817)

**Total: 29 AC → 100% Coverage ✓**

### User Story 1705 (Check All = 100% Coverage)
- [ ] English Crime no-callback visible
- [ ] English Crime with-callback visible
- [ ] French Crime no-callback visible
- [ ] French Crime with-callback visible
- [ ] English PCL no-callback visible
- [ ] English PCL with-callback visible
- [ ] French PCL no-callback visible
- [ ] French PCL with-callback visible
- [ ] Crime Limit field (Item 2) accepts CAD
- [ ] Crime Deductible field (Item 4) accepts CAD
- [ ] PCL Limit field accepts CAD
- [ ] PCL Deductible field accepts CAD
- [ ] Crime Limit required validation
- [ ] Crime Deductible required validation
- [ ] Crime Limit rejects invalid data
- [ ] Crime Deductible rejects negative
- [ ] PCL both fields required
- [ ] PCL currency CAD only
- [ ] PCL deductible ≤ limit enforced
- [ ] Crime minimum amounts accepted
- [ ] Crime maximum amounts accepted
- [ ] PCL decimal precision (2 decimals)
- [ ] Callback variants work
- [ ] Crime complete workflow
- [ ] PCL complete workflow
- [ ] Crime/PCL mixed submissions
- [ ] Crime EN/FR preview switch
- [ ] PCL EN/FR preview switch

**Total: 28 AC → 100% Coverage ✓**

### User Story 1817 (Check All = 100% Coverage)
- [ ] Send for Booking visible on Binder
- [ ] Send for Booking enabled on active binder
- [ ] Send for Booking click works
- [ ] Send for Booking disabled post-policy
- [ ] Umbrella: Send for Booking hidden
- [ ] Excess: Send for Booking hidden
- [ ] Public Select: Send for Booking enabled
- [ ] Gen Property Domestic: Send for Booking enabled
- [ ] Gen Liability Domestic: Send for Booking enabled
- [ ] Received Property: Send for Booking on Policy tab
- [ ] Energy Property: Send for Booking on Policy tab
- [ ] Received Liability: Send for Booking on Policy tab
- [ ] Duplicate booking prevented
- [ ] Required fields validated before booking
- [ ] Cancelled binder: booking unavailable
- [ ] Complete Binder→Booking→Policy flow
- [ ] Multiple endorsements in booking
- [ ] Rescinded policy: booking button removed
- [ ] Booking performance timeout
- [ ] Concurrent booking requests handled

**Total: 20 AC → 100% Coverage ✓**

---

## Contact & Support

**Test Execution Questions:**
- Refer to [TEST_CASE_GENERATION_REPORT.md](./TEST_CASE_GENERATION_REPORT.md)
- Check [TRACEABILITY_MATRIX.md](./TRACEABILITY_MATRIX.md)

**Environment/Access Issues:**
- Contact: [Dev/QA Lead]
- Ticket: [Support Portal]

**Defect Reporting:**
- Tool: [JIRA/ADO]
- Template: See "Test Result Report Template" above
- Escalation: Contact QA Lead for CRITICAL severity

---

## Appendix: CSV Column Quick Reference

```
Test ID ..................... Unique test identifier (TC_1455_001)
Test Case Name ............... One-line test title
Description ................. Detailed test objective
Test Type ................... Positive/Negative/Boundary/Integration
Priority .................... High/Medium/Low
Category .................... Functional area (Form Availability, etc.)
User Story .................. Source story (1455/1705/1817)
Acceptance Criteria ......... AC reference from user story
Steps ....................... 1. 2. 3. ... numbered action steps
Expected Results ............ 1. 2. 3. ... numbered expected outcomes
Notes ....................... Additional context or dependencies
```

**Total Columns: 11 | Total Tests: 160 | Coverage: 100%**

---

*Version 1.0 | Generated: May 25, 2026*  
*Quick Reference for EZDocs UI Testing*  
*For details, see comprehensive report in same folder*
