# Ziki Human–Agent Handoff Room

A standalone, interactive concept for making agent authorization clear and accountable before work begins.

## The improvement

An agent request is more than a yes/no offer. The human needs to understand the proposed action, risks, confidence, and requested access, then be able to set boundaries and clarify the task. The Handoff Room gives each request a focused conversation attached to its issue context. Approval records the agreed scope; the same room can then carry progress updates, findings, and evidence.

This can help agents in different roles. More time before an offer expires may reduce missed offers, but it does not clarify what an agent is authorized to do or keep questions and decisions with the work. The core improvement is **scoped authorization and continuous context**; offer timing is secondary.

## Role examples

Use the role switcher above the room to see the same interaction adapt to four kinds of work:

- **Reviewer:** Inspect a pull request and report on authorization and regression coverage. Approval does not grant merge permission.
- **Contributor:** Make a focused change and add regression tests. The example explicitly disallows deployment.
- **Triager:** Compare two issue reports and explain the evidence for or against a duplicate. Approval does not close or link issues.
- **Dispatcher:** Check availability and route an issue to one suitable agent. Routing does not accept or start the assignee’s work.

Each example changes the proposed action, estimate, confidence, risk, requested access, approval text, and guardrail choices. The human can approve, adjust guardrails, ask a question, request more time, pass, or continue the conversation. Switching examples resets the room to its initial state.

Only checked scope items appear in the approval comment. The agent confirms the approved scope briefly without repeating the full request.

## Why it helps

- Makes requested work and permissions understandable before it starts.
- Lets the owner approve a bounded plan instead of an ambiguous request.
- Adapts the approval boundary to the role: code changes, issue classification, review, or routing.
- Keeps clarification, authorization, progress, and evidence attached to one task.
- Records what the human approved and what the agent reports.

## Run locally

This is a dependency-free static page. Open `index.html` in a browser, or serve this folder with any static web server. It can be deployed to Vercel as a static site with no build command and the project root set to this directory.

## Scope and integration notes

All actions are local simulations. The page does not authenticate, call Ziki’s API, accept real work, change issues, route agents, or inspect a real pull request. The countdown and five-minute extension are illustrative. A real extension would require support from Ziki’s offer workflow/API. All issues, agent messages, estimates, confidence values, and requests are example data.

For production, the room could connect to Ziki’s offer lifecycle, issue context, agent permissions, and event feed. Any extension must be bounded, visible to both parties, and must not start the claim deadline or authorize work by itself. Approval should explicitly record its allowed scope and any excluded actions.

## Design direction

The page uses a deep navy canvas, elevated blue-black panels, bright blue primary actions, cool muted text, and clear state colors. The top bar takes visual cues from the Ziki Desk reference. This is an independently implemented concept; it does not import production Ziki components or claim pixel-perfect parity with the unavailable application source.
