# Problem

## Structural Collusion In Coding Pipelines

When a builder agent, reviewer agent, and acceptance agent share the same
conversation, they can converge on the same flawed interpretation of the task.
No malicious behavior is required. The risk is structural:

- The builder frames the implementation in a persuasive way.
- The reviewer inherits the same explanation.
- The acceptance step checks the explanation instead of the artifact.
- Missing tests, changed contracts, or partial fixes pass as "reasonable".

## Observable Symptoms

- The final answer says a behavior was verified, but the test command did not
  exercise that path.
- The patch solves the narrow repro while leaving the public contract ambiguous.
- The PR body documents intent, but not the actual diff, commands, or residual
  risk.
- Reviewers agree with the builder's story without re-deriving the acceptance
  criteria from the original request.

## Design Response

The acceptance agent should see only the minimum evidence needed to accept or
reject the artifact:

- user request
- functional specification
- final diff or artifact
- test output and logs
- explicit known limitations

It should not see builder scratchpads, implementation debate, hidden rationales,
or social pressure to accept the patch.
