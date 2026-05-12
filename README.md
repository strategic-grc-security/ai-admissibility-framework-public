# AI Admissibility Framework

## What it is
The AI Admissibility Framework is a system governance model for determining whether AI-driven behavior should be permitted to affect a system.

## Core idea
AI governance should not depend on making models behave safely. It should determine whether AI-driven behavior is admissible within the system before action occurs.

## The four pillars
| Pillar    | Governance Question               |
| --------- | --------------------------------- |
| Authority | Who or what is acting?            |
| Actions   | What is being done?               |
| Context   | What is influencing the decision? |
| Evidence  | What can be proven?               |


## The Admissibility Boundary
Current AI governance often relies on policies, guardrails, testing, and monitoring. These may improve behavior or visibility, but they do not necessarily enforce whether an action should occur.

Admissibility introduces an explicit decision boundary: before AI-driven behavior affects a system, the system must determine whether the action is allowed.

## Relationship to the Control Intent Engine
The Admissibility Framework is complemented by the Control Intent Engine, which evaluates governance intent against system reality and helps operationalize admissibility conditions in practice.The Control Intent Engine is a complementary mechanism for evaluating whether those governing conditions are present in a real system.
[Control Intent Engine](https://github.com/daphne-apollo/control-intent-engine-public)

## Repository contents
Links:

- [AI Admissibility Executive Summary](docs/executive-summary.md)

- [AI Admissibility Four Pillars](docs/four-pillars.md)

- [AI Admissibility Boundary](docs/boundary.md)

- [AI Admissibility Control Architecture](docs/control-architecture.md)

- [AI Coding Agent Example](docs/ai-coding-agent-example.md)

## Status
This repository contains the public overview of the AI Admissibility Framework. A longer paper is in progress.