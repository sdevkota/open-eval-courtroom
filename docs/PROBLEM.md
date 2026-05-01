# Problem Statement

## Pain point

Legal and policy AI tools can sound authoritative while hallucinating citations or applying stale law.

## Why now

AI systems are moving from chat into action: they retrieve, decide, write, buy, deploy, remember, and delegate. Existing software governance patterns help, but they do not fully describe model uncertainty, prompt/context boundaries, tool autonomy, memory consent, or provenance across AI pipelines.

## v1 intervention

A review-packet validator that records claims, citations, jurisdiction, date checked, reviewer role, and unresolved authority gaps.

## Non-goals

- This v1 release does not claim to solve the entire research problem.
- It does not require a hosted service or proprietary model.
- It does not hide policy decisions inside opaque model prompts.

## Success criteria

- A maintainer can run the CLI offline.
- A contributor can understand the domain packet in under ten minutes.
- A team can add fixtures, adapters, and stricter checks without rewriting the project.
