# Security Model

## Public Repository Boundary

This public repository contains only sanitized patterns and toy examples. It
does not publish:

- private source code
- customer data
- trading strategies
- API tokens, credentials, or environment values
- private logs or transcripts
- unreleased implementation details

## Verifier Boundary

The acceptance agent should not receive:

- builder scratchpads
- hidden reasoning
- implementation chat history
- informal assurances that a command passed
- private context that is not part of the acceptance packet

The verifier should receive:

- original request
- functional specification
- final patch or artifact
- exact commands and outputs
- known limitations

## Threats

| Threat | Control |
| --- | --- |
| Reviewer inherits builder framing | Hide builder conversation from verifier |
| Test evidence is overstated | Require exact commands and summarized output |
| Sensitive data leaks into examples | Use toy tasks and sanitized fixtures only |
| Acceptance becomes subjective | Force accept/reject/request_evidence schema |

## Disclosure Principle

When a detail cannot be public, disclose the category of omission instead of
pretending the evidence is complete.
