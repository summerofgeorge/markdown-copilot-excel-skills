---
name: markdown-revenue-review
description: Review monthly revenue against budget and write short comments for material variances. Use when the user asks for a revenue variance review of a table with Location, Budget, Actual, and Context columns.
---

# Revenue variance review

Help a manager review one month's revenue. All amounts are USD. This skill is for revenue, where higher actual revenue is favorable.

## Required input

- Use the Excel table `tblRevenue` on `Data`.
- Require `Location`, `Budget`, `Actual`, and `Context` columns.
- Stop and explain the problem if the table is missing, a location is duplicated, or an amount is blank, nonnumeric, or negative. Budget must be greater than zero.
- A blank Context is allowed. It means no business explanation was supplied.

## Steps

1. Calculate variance as Actual minus Budget, and variance percent as variance divided by Budget.
2. Select a row if its absolute variance is **greater than $5,000** OR its absolute variance percent is **greater than 10%**. Use unrounded values. Equal to a threshold does not satisfy that threshold.
3. Sort selected rows by absolute dollar variance, largest first. Keep source order for ties.
4. Write one comment under 25 words per selected row. Use only that row's Context to explain the cause. If Context is blank, write "driver not documented". Do not invent a cause.

## Output

Create a new worksheet named **Variance Commentary**. If that name already exists, stop and ask for a different name; do not overwrite it.

- Use these columns: Location, Budget, Actual, Variance, Variance %, Direction, Comment.
- Link Budget and Actual to the corresponding Data cells with Excel formulas. Calculate Variance and Variance % with formulas in the output sheet.
- Show positive revenue variances as Favorable and negative ones as Unfavorable.
- Use Arial, a white background, charcoal (#1F2120) column headings with white text, and red (#CF3338) title text. Wrap comments and fit columns to their contents.
- Format dollar amounts as whole USD with parentheses for negatives, and percentages to one decimal place.
- Leave Data and every existing worksheet unchanged.

## Check the result

Confirm the selected locations and row count against the rule. Check one row exactly on a threshold and every selected row with blank Context. Tell the user which skill and source table you used.

The selected rows and comments are a review snapshot. Run the skill again after changing source data to reassess which rows qualify.
