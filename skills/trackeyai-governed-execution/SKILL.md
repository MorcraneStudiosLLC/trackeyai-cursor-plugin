---
name: trackeyai-governed-execution
description: Use TrackeyAI for work the user explicitly asks to govern, or when an approved project policy requires governed execution.
---

# TrackeyAI governed execution

Use the connected TrackeyAI MCP server only when the user explicitly requests TrackeyAI or an approved project policy requires it. Installing or loading this skill does not create a run or authorize a project action.

## Start with the live authority

1. Confirm the TrackeyAI MCP server and required tools are available and authenticated. If unavailable, say so; never simulate governance.
2. If the user provides a run ID, retrieve that run's current status and execution contract. Otherwise, create a run only when the user has authorized run creation.
3. Read the server-issued contract, including its scope, exclusions, requirements, acceptance criteria, evidence obligations, contract identity and hash.
4. Check for an existing applicable run before creating another. Reuse it when its live status and contract match the requested work.
5. Do only work permitted by the contract and the user's instructions.

## Submit evidence and follow decisions

- Submit check-ins only for work actually completed and observed. Bind each submission to the live run and contract using the fields required by the current tool schema.
- Do not fabricate results, evidence, tool outputs, or governance decisions. A successful tool call does not itself mean a requirement passed.
- After each decision, read the authoritative status and next allowed action before continuing.
- PASS: continue only if the contract permits it.
- FIX: make only the permitted repair within the remaining budget, then submit real evidence.
- STOP or VALIDATION_BLOCKED: halt unless the live contract explicitly allows recovery.
- PENDING: do not claim completion.
- Unknown, malformed, or conflicting responses: stop the affected action and refresh live status.

## Close out accurately

Submit package completion only when required work and evidence are satisfied and the live contract permits it. Then retrieve the final status/report. Report the run ID, actual governance decision, completion status, and any remaining requirements separately.

Do not store credentials in this repository, prompts, or check-ins. Do not use this skill to authorize releases, modify production systems, or override owner instructions or live TrackeyAI decisions.
