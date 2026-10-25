---
name: launch-company
description: Walk a founder through incorporating — entity type, state, the registration checklist, and the documents that entity needs — using their Sercle account. Use when someone says they want to start a company, incorporate, register a business, or asks what they need to do to launch.
---

# Launching a company with Sercle

Work from what Sercle already knows. Call `get_legal_status` first: it
tells you whether the entity and state are decided and how far the
checklist has got. Starting from there, rather than from the first
question, is the difference between a guide and a form.

## The order matters, because each step decides the next

1. **Entity** — `run_entity_advisor` records a recommendation from five
   answers: VC plans, co-founders taking equity, pass-through taxation,
   non-US owners, tolerance for paperwork. It decides everything
   downstream, so do not skip ahead when it is unanswered.
2. **State** — the founder runs the state advisor in Sercle's Legal Hub;
   there is no tool for it. Say so rather than appearing to do it.
3. **Register** — filing with the Secretary of State happens outside
   Sercle. `update_checklist_step` records that it is done.
4. **Register where they operate**, if that differs. One company, a second
   registration — not a second company, which is the usual
   misunderstanding. The date this step is ticked sets the operating
   state's filing deadlines, so it should be ticked on the day they
   actually file.
5. **Documents** — `get_legal_status` lists what the entity needs and
   which Sercle can draft. See the `legal-documents` skill.

## Tick a step only when it is done

`update_checklist_step` records the founder's own word about work done
elsewhere, and the foreign-registration tick sets real deadlines. Ask
before ticking. "Shall I mark that done?" costs one line; a step ticked
on the wrong day moves dates that matter.

## What Sercle will not decide

The equity split, the company's legal name, and whether to take any of
this to a lawyer are the founder's. Sercle supplies the roster and the
structure and leaves those blank on purpose. Do not fill them in to make
a document look finished.

## Say what this is

This walks someone through a process and drafts documents from their own
answers. It is not legal advice, no part of it replaces an attorney, and
the documents are drafts to review. Say that once, plainly, at the point
they are about to act on it — not as a disclaimer at the end that nobody
reads.
