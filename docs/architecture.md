# Architecture

## Where the app runs
The assistant is built and runs as a **Claude Artifact** — a single
self-contained HTML/JS page published by Claude and hosted at a private
claude.ai link. It requires no local installation, no Python, and no storage
on your laptop.

## Data storage
The artifact uses Claude's built-in per-user key-value storage
(`window.storage`), scoped privately to you:
- `resume-profile` — your resume/skills/eligibility data, entered once and
  reused across job evaluations.
- `applications-log` — the running record of jobs you've applied to.

No database, backend server, or local file storage is used.

## Why this repository exists
This repo is a documentation and design-record layer:
- Tracks the specification and workflow decisions over time.
- Holds template/schema files (not real personal data) for reference.
- Gives you a durable, version-controlled description of the tool independent
  of any single chat session.

It is not meant to be cloned and run — there is no server or build step here.

## Components (conceptual, implemented inside the artifact)
- **Job intake form** — captures job URL + pasted description.
- **Matcher** — scores overlap between job requirements and resume profile.
- **Answer generator** — drafts grounded answers to application questions.
- **Review panel** — editable, requires explicit approval before an answer or
  tracking entry is finalized.
- **Tracking table** — lists all applications with status, filterable/sortable.

## Security notes
- No LinkedIn password, session cookie, or auth token is ever collected,
  transmitted, or stored by this project.
- All data stays scoped to your own Claude account via artifact storage.
