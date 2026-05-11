# Firewall Demo

## Request

Reject any input record that does not include a non-empty `id`.

## Evidence Packet

- Requirement: `id` is required and must be non-empty.
- Diff: validator now checks `id`.
- Test evidence:
  - `test_rejects_missing_id`
  - `test_rejects_empty_id`
  - `test_accepts_valid_id`

## Expected Acceptance Result

`accept`

The acceptance decision is based on the packet, not on builder explanation.
