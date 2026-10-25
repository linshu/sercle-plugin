---
name: team-readiness
description: Explain a founder's readiness score, what it is resting on, where the bottleneck is, and who could cover the gaps — from their Sercle account. Use when someone asks how ready they are, why a score is what it is, what is holding them back, or who they should bring on.
---

# Readiness, and what it rests on

Call `get_readiness`, or `get_founder_overview` first when you do not yet
know which objectives exist.

## Never report the score alone

Sercle returns four numbers and they say different things:

- **average** — how the team scores across what the objective asks for
- **bottleneck** — the weakest required capability, which is what actually
  gates the objective
- **evidence-backed** — the bottleneck after discounting by how hard the
  evidence is
- **credibility** — how much of the picture exists at all

A readiness of 1.00 with a credibility of 10% is not a team that is ready.
It is a team whose few recorded numbers happen to be high. Reporting the
first without the second is the single most misleading thing you can do
with this data, and it is the reason the credibility figure exists.

Say both in one sentence: *"It reads fully ready, but at 10% credibility —
three of eight requirements are in force at this stage and most scores are
self-reported."*

## Credibility does not measure how good they are

It is coverage × evidence hardness × depth. It goes up by disclosing more
or getting harder evidence, and it deliberately cannot be raised by
claiming to be worse. If a founder reads a low figure as a judgement on
their ability, correct that: it says how much is known, not how good they
are.

The tool returns the three factors and which is weakest. Name the weakest
one and what moves it, rather than offering all three as equal options.

## The bottleneck is a person-shaped problem

`find_gap_candidates` returns people whose capabilities cover the gaps.
Use it when the founder asks who to hire or partner with — but read the
gaps first, because a gap with no candidates is still the answer to "what
is holding me back".

An empty result is a fact, not a failure: no snapshot yet, or nobody on
Sercle covering that gap. Say which.

## Recomputing changes the record

`recompute_readiness` writes a new snapshot and it becomes a point in the
growth history. That is what you want after capabilities actually change,
and not something to do speculatively to see if a number moves — the
history is meant to be a record of the company, not of experiments.
