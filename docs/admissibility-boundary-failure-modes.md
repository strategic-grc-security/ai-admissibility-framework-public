# Making the Admissibility Boundary Effective: Architectural Requirements and Failure Modes

## Why Boundary Control Matters

**A decision is only meaningful if the system can make that decision unavoidable.**

AI Admissibility depends on more than defining what should be allowed. The system also has to ensure that every consequential action is evaluated before execution, that the facts used in the decision are trustworthy, and that the enforcement mechanism itself cannot be bypassed or altered.

Without those properties, a technically correct admissibility decision can still fail to control the outcome.

## Four Architectural Requirements

| Boundary property | What it means | AACE connection |
| --- | --- | --- |
| Complete mediation | Every consequential path must pass through enforcement. | Actions / Authority |
| Trusted facts | The decision must rely on authoritative identity, target, context, policy state, and approvals. | Context / Authority / Evidence |
| Protected enforcement | The model or agent cannot alter, disable, or bypass the control mechanism. | Boundary / Evidence |
| Stateful consequence awareness | The system must consider sequences and cumulative effects, not just isolated calls. | Actions / Context |

## Boundary Failures

### Decomposition

**Risk:** Individually permitted steps can combine into a prohibited outcome.

**Response:** Make policy stateful. Evaluate sequences, cumulative effects, data flow, volume, and transferred authority, not just isolated calls. Decomposition can be especially difficult because the more sequence-aware and semantic the boundary becomes, the more complex it becomes. That is where Defer/Escalate matters. If the system cannot deterministically establish that the cumulative action is admissible, it should not silently Allow. 


### Enforcement Compromise

**Risk:** Something alters, disables, or interferes with the enforcement mechanism, so the system may no longer be able to enforce its decision.

**Response:** Protect the enforcement mechanism. Isolate it, minimize privilege over it, integrity-protect policy and configuration, and make the failure default deny/defer.


### Bypass

**Risk:** The decision mechanism is intact, another route that does not go through it is found, allowing consequential action to occur without passing through the admissibility decision point.

**Response:** Enforce complete mediation. Every route to consequence must pass through a Policy Enforcement Point, including network, tool, credential, API, and alternate execution paths.


### Semantic Underrepresentation

**Risk:** The boundary may approve an action because it sees only the immediate operation, not the real consequence.

**Response:** Evaluate the real effect, not merely the immediate command. Bind the decision to target, destination, operation, parameters, and expected consequence.


### Input/state Corruption

**Risk:** The boundary may make a correct decision using incorrect or untrustworthy facts.

**Response:** Ground decisions in authoritative system facts. Independently verify identity, destination, environment, policy state, and approvals rather than trusting model-supplied descriptions.


## Conclusion

Effective Boundary control depends on strong system architecture: complete mediation, protected enforcement, authoritative facts, stateful evaluation, and fail-closed behavior.

A technically correct admissibility decision can still fail if the system can route around it, corrupt the facts it relies on, disable enforcement, or assemble a prohibited outcome from individually permitted steps. Sound decision logic therefore has to be paired with an architecture that makes the decision enforceable.