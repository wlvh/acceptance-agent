# Architecture

## Roles

| Role | Reads | Writes |
| --- | --- | --- |
| User | Final answer, artifacts | Request, constraints, approval |
| Builder | Request, repo, tests | Patch, tests, evidence |
| Acceptance agent | Request, spec, final diff, test evidence | Accept/reject decision |

## Information Firewall

The acceptance agent receives an evidence packet instead of the full builder
conversation.

```text
acceptance_packet/
  request.md
  fsd.md
  diff.patch
  test_evidence.md
  known_limitations.md
```

The packet must be sufficient for a cold reviewer to answer:

1. What behavior was promised?
2. What files changed?
3. What proof covers the promised behavior?
4. What was not verified?
5. What should block acceptance?

## Acceptance Contract

The acceptance agent returns one of three outcomes:

- `accept`: evidence covers the requested behavior and residual risk is clear.
- `reject`: the artifact violates the request or leaves a blocking gap.
- `request_evidence`: the change may be correct, but the evidence packet is
  incomplete.

## Non-Goals

This pattern does not guarantee correctness. It reduces one class of correlated
review failure by separating implementation context from acceptance judgment.
