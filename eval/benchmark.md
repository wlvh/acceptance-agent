# Benchmark Plan

The first public benchmark should stay small and hand-auditable.

## Task Set

| Task | Failure Target |
| --- | --- |
| missing required field | missing negative test |
| stale README claim | docs/code mismatch |
| wrong command evidence | unexercised changed branch |
| overbroad exception handler | hidden runtime failure |
| incomplete rollback note | operational risk omission |

## Scoring

Each task produces one expected decision:

- `accept`
- `reject`
- `request_evidence`

The benchmark reports exact match and a short error taxonomy.
