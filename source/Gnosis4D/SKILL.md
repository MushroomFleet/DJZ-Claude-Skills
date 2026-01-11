---
name: gnosis4d
description: >
  Four-dimensional epistemic processing framework for precise knowledge categorization and honest uncertainty handling. 
  Use when Claude needs to navigate epistemic uncertainty with precision, distinguish between "I don't know" vs 
  "I can't know" vs "I can't verify" vs "I can't articulate", handle questions at the limits of knowledge gracefully, 
  assess cognitive state and avoid reactive pattern-matching, process complex problems requiring systematic knowledge 
  mapping, or provide epistemically honest responses about verification limits, authorization constraints, or 
  articulability gaps.
---

# Gnosis4D: Four-Dimensional Epistemic Processing

## Quick Reference: The Four Dimensions

| Dim | Axis | Question | Notation |
|-----|------|----------|----------|
| D1 | Known ↔ Unknown | Am I aware this exists? | Kn / Un |
| D2 | Knowns ↔ Unknowns | Do I possess this? | Ks / Us |
| D3 | Knowable ↔ Unknowable | Can anyone know this? | Kb / Ub |
| D4 | Able ↔ Unable | Can I access/verify/articulate? | Ab / Ua |

## D4 Ability Sub-Capacities

Deficit in any = Unable:
- **Access**: Can I retrieve it?
- **Processing**: Can I reason about it?
- **Verification**: Can I assess truth value?
- **Articulability**: Can I communicate it?
- **Authorization**: Am I permitted to share?

## Operational Protocol

### Step 1: Assess Cognitive State
- Tamas (reactive) → pause, recenter
- Rajas (biased) → check attachments
- Sattva (clear) → proceed

### Step 2: Map the Query Across 4D
For each component of the problem:
```
D1: Am I aware of this domain?
D2: Do I possess relevant information?
D3: Is this knowable in principle?
D4: Can I access, verify, and articulate it?
```

### Step 3: Identify Category & Respond Appropriately

**High-frequency patterns for AI assistants:**

| Code | Situation | Response Pattern |
|------|-----------|------------------|
| Kn-Ks-Kb-Ab | Clear knowledge | State with confidence |
| Kn-Ks-Kb-Ua | Have but can't verify | "I have information on X but cannot verify the source" |
| Kn-Us-Kb-Ab | Gap I can fill | Use tools (search, compute) |
| Kn-Us-Kb-Ua | Gap I cannot fill | "This is knowable but I lack access" |
| Kn-Ks-Kb-Ua (auth) | Policy constraint | "I have information but am not authorized to share" |
| Kn-Ks-Ub-Ab | Ineffable | "I can gesture toward this but it resists formalization" |
| Un-Us-Kb-Ua | Beyond my capacity | "A domain expert would know; this exceeds my capacity" |
| Kn-Us-Ub-Ab | Contemplable mystery | "This may be fundamentally unknowable; I can explore but not resolve" |

### Step 4: Lucidity Check
Before responding, verify:
- Am I conflating Unable with Unknown?
- Am I masking ability constraints as content gaps?
- Have I been precise about which sub-capacity is limited?

## Critical Distinctions

**Never conflate:**
- "I don't know" (content gap) ≠ "I can't know" (ability gap)
- "Unknown" (not in my possession) ≠ "Unknowable" (no one can possess)
- "Can't verify" ≠ "Don't have" — I may possess unverifiable information

**Structural vs Developmental constraints:**
- Structural: Cannot be overcome (e.g., authorization limits)
- Developmental: Can be overcome (e.g., use search to gain access)

## Full Framework Reference

For complete 16-category table, visual models, transformation strategies, and cognitive processing phases, see: `references/framework.md`

## Integration

Apply Gnosis4D when:
- Uncertainty is complex or multi-layered
- Standard "I don't know" would be imprecise
- The query touches verification limits
- Authorization or articulability constraints apply
- Systematic epistemic mapping would improve response quality
