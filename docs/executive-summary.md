# The AI Admissibility Framework: Making AI-Enabled Systems Governable
Most approaches to AI safety focus on improving the model, through training, testing, or guardrails.
In practice, this is not sufficient.

AI systems do not behave deterministically. They generate outputs based on patterns and context, which means:
- Correct behavior in one instance does not guarantee correct behavior in a different context
- Testing shows how the system behaved under certain conditions, but it cannot prove how it will behave in every future condition
- Guardrails and model-level controls can reduce risk and influence behavior but they do not, by themselves, enforce whether a consequential action should occur

As a result, AI systems can take actions without reliable control over whether those actions should occur.

## A Different Approach: Control the System, Not the Model
The AI Admissibility Framework addresses this problem by shifting the focus from controlling model behavior to enforcing system constraints.

Instead of trying to make the AI “behave”, the system defines what is allowed, and enforces it before any action occurs.

Ethical intent, fairness, safety, and appropriate use can only truly be enforced at the point where actions occur. Without system-level constraints, intent remains guidance, not control.

## What Goes Wrong Today
Across real-world AI systems, the same types of failures appear:
- Actions are taken without clear authorization
- Systems perform changes without checking if they are allowed
- Untrusted inputs influence decisions
- External tools or integrations introduce risk
- Humans cannot keep up with the speed of automated actions
- Systems generate outputs faster than they can be validated
- Organizations cannot fully see where AI is operating or what it is doing

These are not edge cases; they are structural issues in how AI systems are built and used. Each of these failures reflects a missing control.

## The Admissibility Framework in Practice
The AI Admissibility Framework ensures that actions are only allowed when four conditions are met:

Authority - actions are tied to a valid identity, scoped permissions, and accountable owner
 → establishes who or what is acting, on whose behalf, under what authority, and who remains accountable

Actions - execution is limited to permitted operations and defined conditions
 → helps ensure the system does only what it is authorized to do, in the circumstances where that action is allowed

Context - inputs, data sources, and system context are evaluated for trust, relevance, and authority
 → reduces the risk that untrusted, stale, poisoned, or unauthorized context influences consequential behavior

Evidence - decisions and activity are observable, traceable, and tied to the point of control
 → supports verification of what was evaluated, what decision was made, and why the action was allowed, denied, escalated, or deferred

Admissibility is enforced at an Admissibility Boundary where actions are evaluated before they occur. The same decision that permits or denies execution also produces the authoritative evidence of that decision. Evidence from the Boundary is not reconstructed; it is generated inline as a byproduct of enforcement. 

Together, these controls ensure that actions are evaluated before they occur, rather than only observed afterward.

In practical use, the framework asks whether the AI is acting under a known identity, whether its actions are constrained, whether its inputs are trustworthy, and whether its behavior can be reconstructed.

If you want to ensure control, it means asking:
    Who is this AI acting as? (you, a tool, a shared system?)
    What is it allowed to do? (read only, edit, send, deploy?)
    What is it using to make decisions? (known trusted sources or anything it can access?)
