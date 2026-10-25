---
name: legal-documents
description: Draft a founders agreement, bylaws, stock purchase agreement, IP assignment, NDA, advisor agreement or equity split from the founder's Sercle account. Use when someone asks to draft, generate or prepare one of these, or asks what a document needs before it can be signed.
---

# Drafting a legal document from Sercle

Sercle drafts the document, not you. It grounds the draft in the state the
founder recorded, checks that the model did not stop mid-sentence, builds
the signature block, and stores the result in their account. Writing one
here instead would lose all four.

## Check what Sercle already knows first

Call `get_document_fields` with the document type **before** asking the
founder anything. It answers with three things:

- values Sercle can fill from their account
- which of those are **guesses** that want confirming
- which state's law the draft will be grounded in

Then ask only about what is missing. A founder who has already told Sercle
their company name and co-founders should not be asked again — being asked
twice is how a product feels like it is not listening.

The company name is the usual guess. A Sercle "team" is created with every
objective and is often named after it, so a team called *Seed-stage AI
SaaS* is an objective, not a company. When the field comes back flagged,
ask: *"Sercle has your team name as X — is that the name you registered,
or is the legal name different?"*

## Do not invent what you are not told

If the founder has not said how equity splits, leave it as a blank. Sercle
supplies the roster and leaves the percentages empty on purpose: it is the
most consequential number in the document and the one nobody should guess
on someone's behalf. The blanks come out of the PDF as fields they can tab
through.

The same goes for dates, addresses and share counts. A document full of
honest blanks is signable after one conversation with a lawyer. A document
full of plausible inventions is worse than no document, because the
inventions do not announce themselves.

## Generating takes a minute or two

`generate_legal_document` returns an id straight away, and the draft lands
afterwards. Tell the founder it is being written, then call
`get_legal_document` once a minute or two has passed. It answers
`pending`, `ready` or `failed`.

Do not call it in a tight loop; one check after a wait is enough, and a
second if the first still says pending.

## Say what it is

Every draft Sercle produces carries a disclaimer, and you should say the
same thing in your own words when you hand it over: it is a draft to
review with a licensed attorney, not advice and not a finished
instrument. Where the draft carries a **FOR YOUR ATTORNEY** note — the
California §2115 question is the common one — point at it rather than
letting it scroll past, because it is the part a lawyer most needs to see.
