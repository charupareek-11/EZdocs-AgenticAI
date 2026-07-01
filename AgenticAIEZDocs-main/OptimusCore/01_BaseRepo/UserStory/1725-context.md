# User Story 1725 - Context

## Simple Summary
This story is about fixing the premium calculation in the Premium section.

The main issue is that the rate field does not allow enough decimal digits for accurate premium calculations. The current setup only supports a small number of digits after the decimal point, so the premium value becomes incorrect when the real rate has more decimals.

## What is happening now
- Users can enter the rate and premium manually as a workaround.
- The calculator feature does not work properly for premium lines.
- The premium calculation is not using the same values as the Total Insured Values lines.
- The system currently allows only a limited number of decimal digits for the calculation.

## What the user expects
- The rate field should allow more digits after the decimal point.
- The system should support at least 6 to 8 decimal digits.
- The premium should be calculated correctly using the full rate value.
- The printed document should still show only six digits if needed.

## Business reason
This change is needed so the premium amount is accurate and the calculator feature is useful again. Without this fix, users must enter values manually, which is slower and can cause errors.

## Expected behavior
1. The user enters a rate with more decimal digits.
2. The premium is calculated correctly based on that rate.
3. The calculation works properly for premium lines.
4. The printed output displays the value in the required format.

## Important notes
- The current problem is mainly in the premium calculation logic.
- The issue is not just about data entry; it is also about calculation accuracy.
- The requirement is to support more precision without breaking the print format.

## Acceptance idea
- The rate field accepts at least 6 to 8 decimal digits.
- Premium calculation matches the intended result.
- The printout remains readable and shows the expected number of digits.
- Manual workaround is no longer needed for this scenario.
