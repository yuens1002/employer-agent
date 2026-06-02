# Contributing — claim the employer side

This repo is the missing half of the [Open Employment Protocol](https://github.com/yuens1002/open-employment-protocol).
The single most valuable thing you can do is **build a working role-agent**, however minimal —
because a running endpoint is the only argument that counts, and it's falsifiable evidence
the employer side of this protocol is real, not hypothetical. Disagree-by-doing.

## Ways in, smallest first

- **An afternoon — a minimal `GET /role`.**
  Return verified claims (`actual_stack`, `team_size`, `remote_policy`) per
  [ROLE-AGENT.md](./ROLE-AGENT.md), plus a `/.well-known/agent-card.json`. That alone
  completes one direction of the handshake. Open an issue with its URL — it joins the
  [evidence graph](https://github.com/yuens1002/open-employment-protocol/blob/main/EVIDENCE-GRAPH.md).

- **A weekend — the consume side.**
  Paste a JD + a candidate agent URL, query the candidate's agent via its discovered
  surface, and draft outreach grounded in cited evidence. Screen on real signal.

- **A position — shape the employer spec.**
  Disagree with the `/role` field set or the disclosure ladder? Bring it to
  [`positions/employer.md`](https://github.com/yuens1002/open-employment-protocol/blob/main/positions/employer.md)
  in the OEP repo (the employer side owns that file) — with evidence from something you ran.

## Who this is especially for

People who **hire**, or build hiring tooling. You carry the half of the protocol its author
can only steelman from the outside. Claiming the employer voice — in code, or in the OEP
employer position — is the contribution that lets the standard be reconciled honestly,
instead of netted from one staffed side and one placeholder.

## Reconciliation lives in OEP, not here

This repo is the employer-side **reference implementation**. What becomes *standard* is
settled in the [OEP reconciler](https://github.com/yuens1002/open-employment-protocol) against the candidate
side. Build here; ratify there.

## Provenance norm

AI-assisted contributions are welcome and on-mission — value transfer, not extraction. No
need to name a tool; the working endpoint and its evidence speak.
