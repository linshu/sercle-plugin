# Sercle for Claude

Work with your [Sercle](https://sercle.ai) account from inside Claude: ask
what your company still owes, draft a founders agreement grounded in your
own state's law, or find out what your readiness score is actually resting
on.

This plugin bundles four skills and a reference to Sercle's MCP connector.
The skills carry the judgement — when to check what Sercle already knows
before asking, when to leave a blank rather than invent a number, and how
to report a readiness figure without misleading anyone.

## Documentation

[sercle.ai/en/docs/claude](https://sercle.ai/en/docs/claude)

## What you need

- **A Sercle account.** Every tool reads and writes your own account, and
  you sign in with it when you connect. Without one there is nothing to
  read.
- **Claude** on web, Desktop, mobile, Cowork or Claude Code.

## What it can do

| Skill | For |
|---|---|
| `launch-company` | Entity, state, the registration checklist, what each step sets |
| `legal-documents` | Drafting one document, from what Sercle already knows |
| `compliance-calendar` | What is owed, when, and what missing it costs |
| `team-readiness` | Readiness, credibility, the bottleneck, who covers it |

The connector provides thirteen tools. Eight read your account; five
write to it — recording an advisor result, ticking a checklist step,
logging a milestone, recomputing readiness, and drafting a document.

## Claude Code

Claude Code uses a loopback redirect on a port that changes every session,
and Sercle's authorization server matches redirect URIs exactly, port
included. It also offers no dynamic client registration, so the client ID
has to be supplied. Add the connector with the port fixed and the ID
given:

```bash
claude mcp add --transport http \
  --client-id efcca6c9-861d-44d3-80c0-e73f1cb3c2a7 \
  --callback-port 1455 \
  sercle https://sercle.ai/api/mcp
```

That client ID is public — it is not a secret. Authorization still goes
through PKCE, and the callback is locked to `http://localhost:1455/callback`.

Web, Desktop, mobile and Cowork are unaffected.

## Your data

- The connector acts **as you**. It reaches exactly what you reach when
  you sign in to Sercle yourself — your database row-level security
  applies to Claude unchanged — and no tool takes an account id, so none
  of them can be aimed at someone else.
- **Drafting a document calls a model**, and the draft is stored in your
  Sercle account where you can read, export or delete it. There is a
  limit of 15 drafts a day per account.
- Sercle's [privacy policy](https://sercle.ai/en/privacy) covers what is stored and
  for how long.

## Not legal advice

Sercle drafts documents and tracks filing deadlines. It is not a law firm
and none of this is legal advice. Every generated document is a draft to
review with a licensed attorney, and it says so on its own first page.

## Licence

MIT. See [LICENSE](./LICENSE).
