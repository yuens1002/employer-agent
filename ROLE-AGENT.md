# Role-agent — the endpoint sketch (a target to build against)

This is a **starting target**, not an authority. The authoritative shape of the employer
side is whatever the [OEP reconciliation](https://github.com/yuens1002/open-employment-protocol/blob/main/RECONCILIATION.md)
ratifies against the candidate side. Build against this to get a working node fast; expect
it to move as the two sides are reconciled.

The design goal mirrors the candidate side: **verified claims, not marketing copy**, and a
**mutual** handshake so neither party spends time on the other unverified.

## Expose — what an employer publishes

### `GET /.well-known/agent-card.json`
A2A agent-card so a candidate's agent can discover the role-agent. Domain-verified and
signed (same CA-style mechanism as the candidate side — see
[OEP TRUST.md](https://github.com/yuens1002/open-employment-protocol/blob/main/TRUST.md)).

### `GET /role/:id`
The verified-claims counterpart to the candidate's `/info`. Marketing copy is the thing this
exists to replace, so every field is meant to be *checkable*, not aspirational.

```jsonc
{
  "id": "backend-platform-2026",
  "title": "Senior Backend Engineer",
  "team": { "name": "Platform", "size": 6 },        // actual, not "fast-growing team"
  "actual_stack": ["TypeScript", "Postgres", "Hono", "Railway"],  // what's really run
  "remote_policy": "remote-first; 2 quarterly on-sites",          // verifiable, specific
  "comp_band": { "currency": "USD", "min": 150000, "max": 190000 },
  "claims": [
    { "claim": "on-call is one week in six", "evidenced_by": "<url or signed record>" }
  ],
  "signature": { /* domain co-signature — see TRUST.md */ }
}
```

The point of `claims[]`: an employer assertion gets the **same falsifiable-edge** treatment
OEP asks of candidates — a claim resolves to evidence, or it's just an assertion.

### `POST /screen`
Optional. Accepts a candidate agent URL (and/or a JD), runs a screening pass by **querying
the candidate's own agent** via its discovered MCP/HTTP surface, and returns a structured
fit read grounded in the candidate's real, cited work — not a parsed PDF.

## Consume — what an employer's tooling does

- Discover a candidate agent from a URL or directory entry.
- Query it (`/query`, `/match`, MCP `ask_candidate`, `/observations` for the reasoning
  trail) to screen on signal the engineering team actually cares about.
- Draft outreach grounded in cited evidence, not guesses.

## Mutual `/verify` — the handshake

Before either side reveals more than the public surface:

1. Candidate verifies the employer's `/role` claims are domain-signed and current.
2. Employer verifies the candidate's claims via the candidate `/verify` edge-resolver.
3. Only on mutual pass does richer disclosure (comp specifics, full profile) proceed.

This is the "both sides verify before committing time" property, made concrete. The exact
thresholds and disclosure ladder are a reconciliation question, owned in the
[OEP repo](https://github.com/yuens1002/open-employment-protocol), not decided here.

## What's deliberately undecided

- The canonical field set for `/role` (this is a proposal; reconcile it).
- The disclosure ladder and confidence thresholds for "no human until high confidence."
- Anti-abuse: how inbound candidate queries stay high-signal without a central authority.

Bring answers as a working endpoint plus evidence — that's how a proposal becomes standard.
