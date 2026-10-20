# Trueman Baldwin

Computer science student at the College of Charleston (B.S., May 2027). I build backend and
full-stack systems in TypeScript and PostgreSQL. 

Looking for software engineering internships and new-grad roles.

## What I've built

These repos are private. I'm glad to walk through any of them in an interview.

**Farmsie**: marketplace with escrowed payments · [farmsie.app](https://farmsie.app)
- Concurrent stock claims resolve in one guarded `UPDATE … WHERE quantity_remaining >= qty RETURNING`
  inside the order transaction. The losing buyer matches zero rows, and the whole order rolls back.
  A two-buyer race test runs against a real Postgres 16 in CI.
- Escrow release is a compare-and-swap on payment state: released or refunded, never both.
- Stripe webhooks record the event id before any side effect, so a duplicate delivery short-circuits.

**LeadVault**: multi-tenant AI phone receptionist on Twilio and Stripe · [leadvault.baldwinseo.com](https://leadvault.baldwinseo.com)
- Built for a family-owned contractor. In production since June 2026, it has answered 149 of their missed
  calls with a full AI conversation (15 seconds or longer, spam excluded), 34 of them after hours.
- Closed a check-then-act race in call allowances with one row-locking Postgres function
  (`SELECT … FOR UPDATE`) that reserves the slot before the call connects, plus a per-call claim
  stamp so webhook retries don't double-count.
- Compensating rollback for multi-vendor provisioning. If a step fails, the steps that already
  succeeded are torn down, and each teardown is guarded on its own.

**Client portal**: tenant isolation enforced inside Postgres
- Deny-by-default row-level security on all 33 tables, with 37 policies, resolved through a
  `security definer` helper so policy evaluation can't recurse.
- A CI gate boots an in-process Postgres (pglite, no Docker), applies every migration and runs a
  78-case cross-tenant leak suite on every pull request.

**Ops platform**: internal tooling on the Anthropic API
- Prompt caching on a stable system prefix, token streaming to the browser over Server-Sent
  Events across four routes, and child-process agent workers with rate-limit detection and backoff.

## Public code

- **[construction-rag-assistant](https://github.com/Wtbaldw/construction-rag-assistant)**: local
  retrieval-augmented Q&A over a small document set, built on Ollama, ChromaDB and Streamlit.
- **[WumpusWorldA1](https://github.com/Wtbaldw/WumpusWorldA1)**: a team course project, a simple
  reflex agent for Wumpus World in Python and pygame.

## Stack

TypeScript · Node.js · Next.js · React · PostgreSQL (Supabase, Drizzle) · SQL · Python · Java ·
Vitest · Jest · GitHub Actions

## Contact

truemanbaldwin@gmail.com · [Portfolio](https://truemanbaldwin.netlify.app) · [LinkedIn](https://www.linkedin.com/in/truemanbaldwin)
