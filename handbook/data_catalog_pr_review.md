# Lego Data Catalog PR Review Guide 

This guide walks reviewers through the process of validating pull requests (PRs) that update our dataset catalog. Most changes involve adding, removing, or updating dataset entries.

## Overview

Our dataset catalog is a public website that displays standardized metadata for all NSAPH datasets. The catalog is generated automatically from JSONL files stored in the `json/` folder:
- Each `.jsonl` file contains one or more dataset entries with structured metadata
- When a PR updates these files, the catalog website rebuilds automatically
- A preview deployment is available for each PR, allowing you to verify changes without running any local builds

**For reviewers:** Your primary task is to verify the changes through the preview deployment. You don't need to review code, run the build process, or validate technical implementation. The aim is to ensure the catalog displays correctly and contains the expected changes.


### PR Review Steps

#### 1. Read and Summarize the Issue

Understand what the PR is intended to accomplish:
- Locate the issue number in the PR description (typically formatted as "fixes #89")
- Read the full issue to understand the request
- Write a brief 1–2 sentence summary in your review notes documenting what should change and where (optional)
- This helps establish context for your review

#### 2. Check the Preview (main review step)

**This is your primary responsibility.** Before examining any code, verify the changes look correct on the live preview:
- Navigate to the PR page on GitHub
- Locate the deployment preview link (typically labeled "Deploy Preview" in the comments section)
- Click through to view the deployed catalog website
- Find and navigate to the modified or newly added datasets
- Verify each change displays correctly:
  - Titles render clearly and match the issue request
  - Descriptions are complete and properly formatted
  - Keywords and data dictionary information appear as expected
  - All metadata fields are populated (not empty or placeholder text)
- Test all external links (GitHub repository, DOI, documentation) to confirm they are valid and accessible

#### 3. (Optional) Inspect the Source Files

Only examine the source code if the preview appears incorrect or the PR description is ambiguous. This helps identify whether the issue is with the data structure or formatting.

Review the relevant `.jsonl` file (e.g., `json/medpar_outcomes.jsonl`) for:
- **New datasets:** Verify they follow the correct JSON structure and include all required fields
- **Removed datasets:** Confirm the deletions align with the issue request
- **Field updates:** Review modified values to ensure they are reasonable and properly formatted
- **Formatting issues:** Flag any typos, inconsistent naming, or structural errors

#### 4. Submit Your Review

Decide on the appropriate review action based on your findings:
- **Approve:** Everything looks good—the preview displays correctly, all changes match the issue request, and no issues are detected
- **Comment:** You have minor suggestions or questions but no blocking concerns
- **Request changes:** The preview shows problems, content is incorrect, links are broken, or changes don't match the issue request

How to submit your review:
- On the PR page, navigate to the "Files changed" tab
- Scroll to the top right and click **Submit Review**
- Select the appropriate review type (Approve, Comment, or Request changes)
- Add a brief note summarizing what you verified, even if approving (e.g., "Preview looks good, all datasets display correctly, links work")

### What to Look For

**Looks good if:**
- The preview displays the expected changes as described in the issue
- Dataset pages load without errors and render cleanly
- Names and descriptions are consistent with the style of existing datasets
- All external links (GitHub repos, DOI URLs, documentation) open correctly without errors
- No obvious typos, grammatical errors, or inconsistencies in titles or headings
- Metadata fields are properly populated with meaningful content
- If reorganizing datasets, parent-child relationships are correctly maintained

**Needs follow‑up if:**
- The preview is unavailable or shows incorrect/unexpected content
- External links return errors (404, 403 Forbidden, etc.) or are incomplete
- Dataset descriptions are empty, contain placeholder text, or are incomplete
- A dataset appears twice in the catalog or is unexpectedly missing
- Dataset naming is inconsistent (e.g., ID format doesn't match other datasets, title differs from description intent)
- Changes don't match what was requested in the linked issue
- Parent dataset's subdatasets list wasn't updated when adding or removing child datasets

### Common Patterns

Understanding these patterns helps you know what to check:

**Adding datasets:** New dataset entries are added to the JSONL file AND listed in the parent dataset's `subdatasets` field. Verify both changes are present.

**Removing datasets:** Dataset entries are deleted from the JSONL file AND removed from the parent dataset's `subdatasets` list. Confirm both changes align with the issue.

**Fixing text:** Description or name fields are updated, but the structure remains unchanged. Verify the text looks reasonable and matches the issue request.

**Reorganizing:** Multiple changes occur—some datasets may be removed, new ones added, or aggregation levels adjusted. Review the preview carefully to confirm the new structure matches expectations.

### Quick Checklist

Use this as a rapid checklist when reviewing large or complex PRs:

- ✓ Preview link is available and dataset pages load without errors
- ✓ Dataset names and descriptions are consistent with existing catalog entries
- ✓ All URLs (GitHub repos, DOIs, documentation links) are valid and accessible
- ✓ `dataset_id` format is consistent with other datasets in the catalog
- ✓ Parent dataset `subdatasets` lists have been updated if child datasets were added or removed
- ✓ Only the `.jsonl` and related catalog files were modified—no unrelated files changed
- ✓ Changes match what was requested in the linked issue
