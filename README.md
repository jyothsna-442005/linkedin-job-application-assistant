# LinkedIn Job Application Assistant

A workspace-based assistant that helps you evaluate LinkedIn job postings against
your resume, draft tailored application answers, and track your applications —
without requiring anything installed on your laptop.

## What this project is

The working application is a **Claude Artifact** (a self-contained, published web
page hosted by Claude) — not a script you run locally. This repository exists to
document the design and keep a version-controlled record of it, not to be cloned
and executed.

## What it does

1. **Job intake** — you paste a LinkedIn job URL and the job description text.
2. **Resume matching** — compares the job description against your resume profile
   and shows a match score, matching skills, and missing skills.
3. **Answer generation** — drafts application answers based strictly on your real
   resume content. It will not invent qualifications, experience, or skills you
   haven't provided.
4. **Human review** — every generated answer is shown to you for editing/approval
   before it's considered final. Nothing is submitted automatically.
5. **Application tracking** — keeps a record of company, job title, job URL,
   application date, and status.

## What it deliberately does NOT do

- It does not search LinkedIn jobs automatically (no such API access exists for
  third-party tools).
- It does not fill out or submit LinkedIn application forms automatically.
- It never asks for, stores, or uses your LinkedIn password, session cookies, or
  auth tokens.
- It does not fabricate resume content — answers are grounded only in what you
  provide.

You always do the final submission yourself, directly on LinkedIn.

## How it works

See [`docs/architecture.md`](docs/architecture.md) for how the artifact is built
and [`docs/workflow.md`](docs/workflow.md) for the step-by-step usage flow.

## Data

`data/resume-template.json` and `data/applications-log-template.json` show the
data shapes used by the artifact. Your actual resume and application history are
stored privately in the artifact's own storage — real personal data is not
committed to this repository.
