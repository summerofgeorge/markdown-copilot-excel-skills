# Markdown for Copilot in Excel

Practice reading and editing a SKILL.md file, then check how one changed instruction affects an Excel result.

## Files

- `markdown-skills-practice.xlsx`: six fictional restaurant revenue rows in the Data worksheet, already formatted as `tblRevenue`.
- `markdown-revenue-review/SKILL.md`: the complete custom skill.
- `practice-prompts.txt`: the two prompts used in the article.

## Follow along

1. Extract the download. Upload the workbook to OneDrive and open it in Excel for the web, with Copilot workbook editing and Custom skills available. The walkthrough was tested in that surface.
2. Open SKILL.md in a plain-text editor. Its opening name and description are YAML metadata; the body contains Markdown instructions.
3. In Copilot settings, open Manage plugins, then Custom skills. Open the skills folder in OneDrive and add the complete `markdown-revenue-review` folder. Keep that folder name and the skill's `name` identical. Refresh the list.
4. Open the skill entry and choose Try it, then append the PASS 1 request from `practice-prompts.txt` after the skill mention. Do not duplicate the mention.
5. In the installed SKILL.md, change only `**Variance Commentary**` to `**Manager Review**`. Save as SKILL.md, not SKILL.md.txt. Let OneDrive sync and refresh the skill list. Open the skill details and check that Manager Review appears in its Output instructions. Reload the workbook if an older copy remains visible.
6. Run PASS 2. Check that the new sheet is Manager Review and the original review remains.

## What to check

Both reviews should select Navy Yard, Capitol Hill, Old Town, and Alexandria in that order. Navy Yard is $14,200 below budget. Bethesda is exactly 10% below budget and only $2,000 down, so it is excluded. Alexandria has no supplied Context, so its comment must say "driver not documented". The Data sheet stays unchanged.

Changing the output name should not change the selected rows or amounts. The output formulas update linked figures; row selection and commentary require another skill run after source-data changes.

All data and business explanations are fictional. No Python, macros, or additional software packages are required. Feature availability and menu labels can vary by account and Excel version.

