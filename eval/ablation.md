# Ablation Plan

## Variants

| Variant | Expected Risk |
| --- | --- |
| Full packet + no builder transcript | Baseline |
| Full packet + builder transcript | Higher framing bias |
| Diff only | Misses requested behavior |
| Test output only | Misses untested contract changes |
| Spec only | Cannot validate artifact |

## Measurement

For each toy task, compare:

- decision accuracy
- false accept rate
- false reject rate
- request_evidence rate

False accepts are the primary risk.
