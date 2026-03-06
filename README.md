# Poetic Engineering Notation (PEN)
**Version:** 1.0.0

PEN is a symbolic system for describing the structural logic, rhetorical mechanics, and imagery domains of a poem.

## Model: Captures vs Ignores

| Captures | Ignores |
| :--- | :--- |
| Stanza form & Meter consistency | Exact line counts (unless specified) |
| Rhetorical stance (Voice) | Specific vocabulary |
| Structural devices (Rhetoric) | Subjective "meaning" |
| Imagery source domains | Cultural context |
| Emotional vector (Tone) | |

## Canonical Syntax

```text
PEN ::= <Structure> <Meter> <Voice> <Rhetoric> <Domain> [<Vector>]
```

Example: `S4 M≈ V. R≠ D* T↑`

## Symbol Table

### 1. Structure (S)
The physical container of the verse.
- `S2`: Couplet.
- `S3`: Tercet.
- `S4`: Quatrain.
- `S6`: Sextet.
- `S~`: Free verse / Irregular.

### 2. Meter (M)
The rhythmic consistency.
- `M=`: **Regular:** Strict meter (e.g., Iambic Pentameter).
- `M≈`: **Loose:** Near-regular, conversational rhythm.
- `M~`: **Free:** No discernible metric pattern.

### 3. Voice (V)
The grammatical mood or stance of the speaker.
- `V^`: **Imperative:** High agency, commands ("Come", "Let", "Behold").
- `V!`: **Apostrophe:** Addressing an abstract/absent entity ("O solitude", "Darkness!").
- `V.`: **Indicative:** Observation, description, witnessing.
- `V~`: **Confessional/Intimate:** Direct second-person address to a specific, known subject ("you were my ground", "I've seen you change"). Distinct from `V!`, which addresses abstractions.
- `V?`: **Interrogative:** Questioning.

### 4. Rhetoric (R)
The structural device driving the logic.
- `R=`: **Parallelism/Anaphora:** Repeating structures ("Come healing... Come healing...").
- `R≠`: **Antithesis:** Juxtaposing opposites (Light/Dark, Body/Mind).
- `R:`: **Metaphor/Simile:** Direct comparison (A is B).
- `R+`: **Accumulation:** Listing or stacking images.

**Compound Rhetoric:** When a stanza operates through two devices simultaneously, stack with `,` — primary device first: `R=,:` means Anaphora primary, Metaphor secondary. The first symbol is always the structural driver; subsequent symbols are supporting devices.

### 5. Domain (D)
The source material of the imagery. Can use `>` to show shifts (e.g., `D_>D.`).
- `D*`: **Divine/Cosmic:** Heavens, Spirit, Grace, Mercy.
- `D.`: **Somatic/Body:** Heart, Blood, Limb, Arteries.
- `D~`: **Nature/Elemental:** Dust, Earth, Branches, Sea.
- `D_`: **Abstract/Mental:** Reason, Solitude, Memory, Time.
- `D@`: **Domestic/Social:** Home, City, War, Trade.

### 6. Vector (T)
The emotional or energetic direction (Optional).
- `T↑`: **Ascending:** Hope, lifting, praise, intensification.
- `T↓`: **Descending:** Despair, grounding, grief, entropy.
- `T↔`: **Neutral:** Balanced, static, reflective.
- `T→`: **Forward:** Narrative progression.
- `T⇕`: **Inverted/Ironic:** Stated tone opposes actual emotional direction. Surface signals `T↑` (celebration, freedom) while the logic is `T↓` (fault, loss, grief).

## Semantics Rules

- **Layered Analysis:** PEN describes multiple layers (structure, meter, voice, rhetoric, imagery, tone) simultaneously.
- **Domain Shifts:** Domains can transition (using `>`) to show movement of imagery within the stanza.
- **No Same-Domain Shifts:** `Dx>Dx` (source and target the same domain) is prohibited. Use a single domain token. If two images feel distinct within one domain, that is a signal the domain taxonomy needs refinement, not a shift.
- **Rhetorical Focus:** The Rhetoric (`R`) axis captures the *primary* device driving the stanza's logic. Secondary devices may be appended with `,` (e.g., `R=,:`).

## Constraints / Invariants

- Every PEN expression must define at least Structure (`S`) and Meter (`M`). An expression missing `M` is malformed.
- Domains (`D`) describe the *source* of the imagery, not the target.
- Same-domain shifts (`Dx>Dx`) are prohibited; use a single domain token.
- PEN is language-agnostic; it describes the poetic devices, not the specific words.

## Live Mode (Shorthand)

Optimized for quick analysis.

- Omit prefixes (`S`, `M`, `V`, `R`, `D`, `T`) if standard order is used.
- Use `>` for `D_>D.` transitions.

Example: `4 ≈ ^ ≠ *` (Quatrain, Loose Meter, Imperative, Antithesis, Divine)

---

See [EXAMPLES.md](./EXAMPLES.md) for usage and [CHEATSHEET.md](./CHEATSHEET.md) for a quick reference.
