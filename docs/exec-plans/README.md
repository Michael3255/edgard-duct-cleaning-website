# Execution plans

Each documentation file has a short plan that says what it covers, how it will be written and how to tell it is finished.

## Layout

- `active/`: plans for docs that are in progress or waiting on a decision
- `completed/`: plans for docs that are finished

When a doc is finished, update the plan's status and date, then move it from `active/` to `completed/`.

## Naming

One plan per doc, named after the doc: `architecture.md` is planned in `architecture.md`.

## Template

```markdown
# Plan: <doc name>

- **Status:** active | blocked | completed
- **Doc:** link to the file
- **Audience:** who reads it
- **Completed:** date, or blank

## Goal
What the reader should be able to do after reading it.

## Outline
The headings the doc will have.

## Verify against
Source files the claims in the doc must match.

## Steps
1. ...

## Done when
- [ ] ...
```
