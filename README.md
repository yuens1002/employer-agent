# oep-recruiter — the employer side of the Open Employment Protocol

> **The missing half — scaffolded, not yet built. This repo is an invitation.**

[`resume-agent`](https://github.com/yuens1002/resume-agent) is the candidate-side reference
of the [Open Employment Protocol](https://github.com/yuens1002/open-employment-protocol): a live, queryable,
signed agent. **This is its mirror** — the employer-side reference. It does two things a
walled-garden job board never lets you do:

1. **Consume** — let a hiring *engineer* query a candidate's agent directly (`/info`,
   `/query`, `/match`, the MCP `ask_candidate` tool) and screen on real signal, in their own
   workflow, **before HR or a keyword filter is involved.**
2. **Expose** — publish a `/role` endpoint of **verified claims** (actual stack, team size,
   remote policy) — domain-co-signed, not JD marketing copy — so the candidate can verify
   *you* too. Mutual `/verify` before either side spends time.

## Status: a call, not a finished thing

Planned since 2026-04-24; **not yet built.** This scaffold exists so that someone who hires —
or builds hiring tooling — can stand it up. Per the protocol's
[evidence-graph method](https://github.com/yuens1002/open-employment-protocol/blob/main/EVIDENCE-GRAPH.md),
**building it is itself the proof the other side of the protocol is real.** A working
`/role` endpoint is worth more than any amount of agreement.

If you build it, you don't just contribute code — you become the **employer voice** the
reconciliation needs. The protocol can't be netted honestly with only one side staffed.

## Maintainership & independence

This repo is deliberately **not owned or driven by the candidate-side author.** The person
who built [`resume-agent`](https://github.com/yuens1002/resume-agent) (the candidate
reference) stays in a **mentor-only** role here and recuses from the employer-side work —
because the whole point of the protocol is that **no single party owns both sides.** Someone
who controlled the candidate side *and* the employer side would defeat the independence the
trifecta exists to protect; that conflict of interest is real, and naming it is the honest
move.

So the employer side needs a real owner — someone who hires, or builds hiring tooling, to
take it and run. **Mentorship is available; ownership is open.**

## How it plugs into OEP

OEP is a **reconciler, not a spec author**: the candidate side and the employer side each
bring their own spec, and OEP poses both and settles a net outcome no single party owns.
This repo is the **employer position made executable** — the running counterpart to
[`positions/employer.md`](https://github.com/yuens1002/open-employment-protocol/blob/main/positions/employer.md)
in the OEP repo. Build here; the standard gets reconciled there.

See **[ROLE-AGENT.md](./ROLE-AGENT.md)** for the concrete endpoint sketch to build against —
a *starting target*, not an authority (the authoritative shape is whatever the OEP
reconciliation ratifies).

## Build the smallest version

- **An afternoon** — a minimal `GET /role` returning verified claims (`actual_stack`,
  `team_size`, `remote_policy`) and a `/.well-known/agent-card.json` so a candidate agent
  can discover you. That alone completes one direction of the handshake.
- **A weekend** — add the consume side: paste a JD + a candidate agent URL, run a screening
  pass via the discovered MCP, draft grounded outreach from real evidence (not a résumé
  guess).
- **The handshake** — implement mutual `/verify`: each side confirms the other's
  domain-signed claims before revealing more. The trust mechanism is described in
  [OEP TRUST.md](https://github.com/yuens1002/open-employment-protocol/blob/main/TRUST.md).

## Provenance

If AI helps you build it, that's on-mission — value transfer, not extraction. No need to
name a tool; the working endpoint and its evidence speak.

## License

[MIT](./LICENSE) — build it, make it yours, keep the protocol no one's to own.
