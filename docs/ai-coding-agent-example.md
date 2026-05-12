# AI Coding Agent Example

## Scenario
An AI coding assistant operates in an enterprise environment and can interact with repositories, deployment workflows, and production systems.

## Without Admissibility
User → AI → Repository → Deployment → Production

The AI can propose or trigger changes without a required decision point before execution.

## With Admissibility
User → AI → Admissibility Boundary → Repository / Deployment / Production

Before execution, the system evaluates whether the action is permitted.

| Pillar | What is evaluated |
|---|---|
| Authority | Who or what is acting, under what identity and authority |
| Actions | Whether the requested operation is allowed |
| Context | Whether the inputs and sources influencing the action are trusted |
| Evidence | Whether the decision and outcome can be reconstructed |

## Boundary Outcome
The action is permitted, denied, deferred, or escalated.

## Key Point
Controls are required to produce an explicit decision before execution.