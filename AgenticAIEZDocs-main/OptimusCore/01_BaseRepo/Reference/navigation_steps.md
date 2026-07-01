Login to ez docs application
Select required LOB
Select required product
fill all required fields
add endorsment forms and fill details if available and check functionalities of fields
create quote and prewiew document in both english and french available
validate given fields of endorsement in document
create binder ,create policy and verify fields 

## Steps for User Story 1724 - Deductibles and Time Specification

1. Login to the EZDocs application with a valid user account.
2. Select the required Line of Business (LOB) and the specific product for the quote.
3. Create a new quote or open an existing quote for that product.
4. Go to the `Coverage` tab, then open the Deductible or Deductible & Waiting Period section.
5. In the Deductible section, select `PD & TE` as the deductible type.
6. Under `PD`, choose `%` and verify the UI shows the `Minimum/Maximum` option when applicable.
7. Confirm the user can leave `Minimum/Maximum` unselected and still enter free text notes.
8. Enter a deductible example such as `PD: $10000` and add free text remarks.
9. Verify the form now supports an `Other` or free-text field for `%` PD values without forcing `PD&TE Combined`.
10. Open the Time Specification section and verify the coverage dropdown lists previously entered coverage names from Annual Aggregate Limit and Deductible sections.
11. Confirm the `Coverage Period` field accepts free text input without requiring selection of `Hours/Days`.
12. Verify the label reads `Earthquake or Earth Movement` and is consistent with the Deductible section.

## Steps for User Story 1725 - Rate & Premium precision

1. Login to the EZDocs application with a valid user account.
2. Select the required Line of Business (LOB) and the specific product for the quote.
3. Create a new quote or open an existing quote for that product.
4. Navigate to the "Total Insured Values" section and expand the "Premium" area.
5. Click an existing premium line or click Add to open the Premium modal (the small dialog shown on the right in the screenshot).
6. In the modal, set `Rate Type` to "Rate (Number)" and enter a rate value using multiple decimal places (for example: `0.45234567`).
7. Observe the Premium field and confirm the calculator populates a premium amount based on the entered rate and the Value ($) field.
8. Save the modal and check the Premium table row; confirm the calculated premium matches the expected value using the full precision of the rate.
9. Preview the generated document (English and/or French) and confirm the printed premium/ rate shows the expected formatting (print may show up to six decimal places while calculations use higher precision).
10. To reproduce the issue and validate the fix, repeat steps with rates having 4, 6 and 8 decimal places and compare calculation vs printed result.



