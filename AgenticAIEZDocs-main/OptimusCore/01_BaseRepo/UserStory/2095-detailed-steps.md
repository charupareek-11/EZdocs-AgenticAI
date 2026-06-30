# User Story 2095 - Detailed Steps

## Related Story
- Base story: `AgenticAIEZDocs-main/OptimusCore/01_BaseRepo/UserStory/2095.md`

## Description
Improve the Coverage section of the Energy Property submission screen by arranging coverage rows alphabetically, adding a vertical scroll bar to the coverage list area, and placing page navigation controls at the top of the page as well as the bottom.

## Goal
Deliver a cleaner, more usable Coverage tab experience for users reviewing long coverage lists in EzDocs.

## Scope
- Coverage list sorting on the Coverage tab under Sub Limits.
- Vertical scrolling inside the coverage list container.
- Top-of-page pagination controls in addition to the existing bottom controls.

## Detailed Steps

1. Review the existing Coverage tab implementation and identify the table component that renders the coverage rows.
   - Locate the container element for the Coverage table.
   - Confirm how `Coverage Name`, `Limit of Liability ($)`, and `Limit Of Liability (Free Form)` rows are generated.

2. Implement alphabetical sorting for the coverage rows.
   - Sort by the `Coverage Name` column.
   - Apply case-insensitive alphabetical ordering.
   - Keep any non-coverage header rows (for example informational rows like "LIMITS ARE APPLICABLE...") fixed and unsorted.
   - When the list refreshes, the sorted order should be preserved.

3. Ensure the sorting behavior works across all Coverage entries.
   - Include coverages with long text names and punctuation.
   - Handle blank or null `Coverage Name` values gracefully by placing them at the end.

4. Add a vertical scroll bar to the coverage table area.
   - Limit the visible height of the table container so a scroll bar appears when content exceeds the view area.
   - The scrollbar should appear only within the coverage list region, not on the whole page.
   - Use the existing UI style guidelines so the scroll bar matches the application theme.
   - Ensure the table header remains visible while scrolling if the UX design supports sticky headers.

5. Add page navigation controls at the top of the Coverage section.
   - Duplicate existing pagination controls from the bottom of the list to the top.
   - Ensure top controls show the same current page and total record count as the bottom controls.
   - Keep both control sets in sync when the user changes pages.
   - Place the top pagination controls in a visible location above the coverage table.

6. Verify page move / navigation functions from both top and bottom controls.
   - Confirm users can go to first, previous, next, and last pages from top controls.
   - Confirm the bottom controls continue to work as before.
   - If the table uses infinite scrolling or a virtualized list, map the top controls to the same page-change API.

7. Test the full coverage flow.
   - Open the Coverage tab with a long list of sub-limits.
   - Verify alphabetical ordering across the full list.
   - Check the vertical scrollbar on large lists.
   - Validate the top pagination controls appear and function correctly.
   - Confirm the bottom page controls remain visible and synchronized.

## Acceptance Criteria
- Coverage rows are ordered alphabetically by `Coverage Name` on the Coverage tab.
- The coverage list container displays a vertical scroll bar when the list is taller than the available area.
- Pagination controls are available at both the top and bottom of the list.
- Top and bottom pagination controls remain synchronized and navigate correctly.
- Non-coverage header rows and informational rows are not incorrectly sorted.
- Long coverage names and special characters do not break sorting or layout.

## Test Scenarios

### Scenario 1: Alphabetical ordering
- Given the Coverage tab has multiple coverage rows,
- When the list loads,
- Then the rows are sorted alphabetically by `Coverage Name`.

### Scenario 2: Vertical scrolling
- Given the coverage list contains more rows than fit in the visible container,
- When the user scrolls the list,
- Then a vertical scroll bar is present and scrolling is smooth.

### Scenario 3: Top pagination controls
- Given the Coverage tab has pagination,
- When the page loads,
- Then pagination controls appear at the top of the page above the coverage table.
- And the top controls reflect the same page and record count as the bottom controls.

### Scenario 4: Pagination synchronization
- Given the user uses the top page controls,
- When they move to another page,
- Then the bottom pagination controls also update to the same page state.

### Scenario 5: Edge cases
- Given a coverage name is blank or missing,
- When sorting occurs,
- Then the blank entry appears after valid coverages.
- Given a coverage name contains punctuation or numbers,
- When sorting occurs,
- Then the alphabetical order remains correct and stable.
