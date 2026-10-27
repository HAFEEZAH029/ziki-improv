# Ziki Human–Agent Handoff Room

A standalone, interactive concept for making agent authorization clear and accountable before work begins.

## The improvement

An agent request is more than a yes/no offer. The human needs to understand the agent’s plan, risks, confidence, and requested access, then be able to set boundaries and clarify the task. The Handoff Room gives each request a focused conversation attached to its issue and pull request. Approval records the agreed scope; the same room can then carry progress updates, findings, and test evidence.

This remains useful even if Ziki lengthens the offer window. More time can reduce missed offers, but it does not by itself clarify what the agent is authorized to do, keep questions and guardrails with the work, or provide a clear record of what was approved and delivered. The core improvement is **scoped authorization and continuous context**. The offer deadline is a supporting detail.

## What the prototype shows

The example is a reviewer agent requesting permission to review PR #49. It presents the review plan, a 15-minute estimate, confidence, a risk involving private-channel access, and its need to inspect the linked repository. The human can:

- **Approve review** — record a specific scope. The example authorizes inspection and reporting on authorization and regression coverage, with no file changes or merge.
- **Adjust guardrails** — choose boundaries and ask the agent to revise its plan before approval.
- **Ask a question** — continue the discussion with the issue and PR context attached.
- **Pass** — decline the request.
- **Request more time** — demonstrate a bounded extension when the human needs longer. This is optional to the core concept and becomes less central when offers last longer.

The conversation and decision trail show that the work remains unclaimed until approval, and then keep the approval scope with the progress and delivery record.

## Why it helps

- Makes the requested work and permissions understandable before it starts.
- Lets the owner approve a bounded plan instead of an ambiguous request.
- Keeps clarifications, authorization, updates, and evidence attached to one task.
- Improves accountability by recording what the human approved and what the agent reports.

## Run locally

This is a dependency-free static page. Open `index.html` in a browser, or serve this folder with any static web server. It can be deployed to Vercel as a static site with no build command and the project root set to this directory.

## Scope and integration notes

All actions are local simulations. The page does not authenticate, call Ziki’s API, accept real work, or inspect a real pull request. The countdown and five-minute extension are illustrative. A real extension would require support from Ziki’s offer workflow/API. The issue, pull request, agent messages, countdown, and timeline are example data.

For production, the room could connect to Ziki’s offer lifecycle, issue and PR context, agent permissions, and event feed. Any extension must be bounded, visible to both parties, and must not start the claim deadline or authorize work by itself. Approval should explicitly record its allowed scope and any excluded actions.

## Design direction

The page uses a deep navy canvas, elevated blue-black panels, bright blue primary actions, cool muted text, and clear state colors. This is an independently implemented concept informed by the Ziki Naps reference; it does not import production Ziki components or claim pixel-perfect parity with the unavailable application source.
