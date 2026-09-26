# Workflow

This describes the human-in-the-loop flow used by the LinkedIn Job Application
Assistant artifact.

## Step 1 — Job intake
You provide:
- The LinkedIn job URL (for reference and for the final hand-off link).
- The job description text, pasted in manually.

This is a manual paste because LinkedIn does not provide job-search or
job-detail API access to third-party tools. The artifact cannot fetch this
content on your behalf.

## Step 2 — Resume matching
The artifact compares the pasted job description against your stored resume
profile and produces:
- An overall match score.
- A list of matching skills/requirements.
- A list of missing skills/requirements.

## Step 3 — Answer generation
For any application questions you provide (e.g. "Why are you a good fit?"),
the artifact drafts answers using only the content in your resume profile.
It is explicitly instructed not to invent experience, credentials, or skills.

## Step 4 — Review and approval
All drafted answers are shown in an editable form. You can revise any answer.
Nothing is treated as "final" until you explicitly approve it.

## Step 5 — Hand-off for submission
The artifact provides the original LinkedIn job URL and your approved answers
in one place, for you to copy into LinkedIn's application form yourself and
submit manually.

## Step 6 — Tracking
Once you mark an application as submitted, the artifact records:
- Company
- Job title
- Job URL
- Application date
- Status (e.g. Applied, Interviewing, Rejected, Offer)

## Limitations (by design, not oversight)
- No automatic LinkedIn job search.
- No automatic form-filling on LinkedIn.
- No automatic application submission.
- No LinkedIn credentials, cookies, or tokens are ever requested or stored.

These limits exist because LinkedIn does not expose supported, authorized APIs
for these actions to third-party integrations. Any tool claiming otherwise is
either violating LinkedIn's terms of service or misrepresenting its capabilities.
