# Open Eval Courtroom

Citation and claim review packets for legal and policy AI outputs.

> Version: 1.0.0 | License: MIT | Status: production-oriented v1 foundation

## Problem

Legal and policy AI tools can sound authoritative while hallucinating citations or applying stale law.

## What this project solves

A review-packet validator that records claims, citations, jurisdiction, date checked, reviewer role, and unresolved authority gaps.

Open Eval Courtroom ships as a small, dependency-free CLI and library. It validates a domain-specific JSON packet, emits actionable findings, and gives contributors a concrete surface for adding adapters, richer checks, schemas, and integrations.

## Who it is for

Legal tech builders, policy researchers, law librarians, access-to-justice groups.

## Quick start

```bash
npm test
npm start -- sample
```

Analyze your own packet:

```bash
open-eval-courtroom ./packet.json
```

Or pipe JSON:

```bash
cat packet.json | node src/cli.js
```

## Example packet

```json
{
  "output": {
    "topic": "tenant repair rights",
    "jurisdiction": "CA"
  },
  "claims": [
    {
      "text": "landlord must repair habitability issues",
      "citation": "Cal. Civ. Code 1941"
    }
  ],
  "review": {
    "checkedAt": "2026-04-30",
    "reviewer": ""
  }
}
```

## Library usage

```js
const { analyze } = require("./src/index.js");

const report = analyze({
  "output": {
    "topic": "tenant repair rights",
    "jurisdiction": "CA"
  },
  "claims": [
    {
      "text": "landlord must repair habitability issues",
      "citation": "Cal. Civ. Code 1941"
    }
  ],
  "review": {
    "checkedAt": "2026-04-30",
    "reviewer": ""
  }
});
console.log(report.summary);
```

## v1 behavior

- Validates required fields for the domain packet.
- Scores readiness from 0 to 100.
- Reports missing or weak governance evidence.
- Suggests next actions and contributor extension points.
- Runs fully offline with no API keys and no network access.

## Contribution map

Good first contributions:

- Add citation resolvers.
- Add jurisdiction packs.
- Add court rule freshness checks.
- Add plain-language review.

Larger contributions:

- Add a JSON Schema and compatibility tests.
- Build import/export adapters for popular AI frameworks.
- Add real-world fixtures from public, non-sensitive examples.
- Improve scoring with transparent, documented heuristics.

## Project principles

- Human agency over blind automation.
- Open standards over vendor lock-in.
- Auditable decisions over hidden magic.
- Privacy and safety as design constraints, not release notes.

## GitHub Pages

The marketing site lives in `site/index.html`. Enable GitHub Pages from the `site` folder or use the included Pages workflow after publishing.

## Security

This project does not process secrets by default. If you build adapters that touch production systems, keep least privilege, explicit consent, and auditable logs in the design.
