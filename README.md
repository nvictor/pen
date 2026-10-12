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

**Compound Rhetoric:** When a stanza operates through two devices simultaneously, stack with `,`: primary device first: `R=,:` means Anaphora primary, Metaphor secondary. The first symbol is always the structural driver; subsequent symbols are supporting devices.

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

## Examples

### Basic Examples

#### "Come Healing" by Leonard Cohen

**Verse 1**
> Behold the gates of mercy / In arbitrary space
> And none of us deserving / The cruelty or the grace

**PEN:**
```text
S4 M≈ V^ R≠ D* T↔
```
*   `V^`: Starts with command "Behold".
*   `R≠`: Contrast of "cruelty" vs "grace".
*   `D*`: Domain is Divine/Cosmic.

**Verse 2**
> O solitude of longing / Where love has been confined
> Come healing of the body / Come healing of the mind

**PEN:**
```text
S4 M≈ V! R= D.>D_ T↑
```
*   `V!`: Address "O solitude".
*   `R=`: Parallel "Come healing...".
*   `D.>D_`: Shifts from Somatic (Body) to Abstract (Mind).

**Verse 4**
> O troubled dust concealing / An undivided love
> The heart beneath is teaching / To the broken heart above

**PEN:**
```text
S4 M≈ V! R≠ D~ T↓
```
*   `V!`: Address "O troubled dust".
*   `R≠`: Contrast "Beneath" vs "Above".
*   `D~`: Nature/Elemental focus.

**Verse 5**
> Let the heavens falter / Let the earth proclaim
> Come healing of the altar / Come healing of the name

**PEN:**
```text
S4 M≈ V^ R= D* T↑
```
*   `V^`: "Let...", "Come...".
*   `R=`: Strong parallelism.
*   `D*`: Heavens, Altar, Name (Divine/Ritual).

**Verse 6**
> O longing of the branches / To lift the little bud
> O longing of the arteries / To purify the blood

**PEN:**
```text
S4 M≈ V! R= D~>D. T↑
```
*   `V!`: "O longing...".
*   `R=`: Parallel structure.
*   `D~>D.`: Shifts from "Branches/Bud" (Nature) to "Arteries/Blood" (Somatic).

**Verse 7 (Chorus/Refrain)**
> And let the heavens hear it / The penitential hymn
> Come healing of the spirit / Come healing of the limb

**PEN:**
```text
S4 M≈ V^ R≠ D*>D. T↑
```
*   `V^`: "Let...", "Come...".
*   `R≠`: Contrast of "Spirit" vs "Limb" (Merism: the whole being).
*   `D*>D.`: Perfect fusion of Divine and Body.

#### "Suzanne" by Leonard Cohen

**Verse 1**
> Suzanne takes you down / To her place near the river
> You can hear the boats go by / You can spend the night beside her
> And you know that she's half-crazy / But that's why you want to be there
> And she feeds you tea and oranges / That come all the way from China
> And just when you mean to tell her / That you have no love to give her
> Then she gets you on her wavelength / And she lets the river answer
> That you've always been her lover

**PEN:**
```text
S~ M≈ V. R+ D~>D@ T→
```
*   `S~`: Free verse, irregular stanzaic structure (13 lines).
*   `M≈`: Loose, conversational rhythm maintaining flow.
*   `V.`: Indicative voice: observation and witnessing ("you know," "you can hear").
*   `R+`: Accumulation of sensory images and narrative details.
*   `D~>D@`: Shifts from Nature/Elemental (river, boats) to Domestic/Social (tea, oranges from China, place).
*   `T→`: Forward narrative progression.

**Chorus**
> And you want to travel with her / And you want to travel blind
> And you know that she will trust you / For you've touched her perfect body with your mind

**PEN:**
```text
S4 M≈ V. R= D_>D. T↑
```
*   `S4`: Quatrain structure.
*   `R=`: Anaphoric repetition ("And you want... And you want... And you know").
*   `D_>D.`: Abstract/Mental (blind, mind, trust) to Somatic (perfect body).
*   `T↑`: Ascending: aspiration, transcendence through connection.

**Verse 2**
> And Jesus was a sailor / When he walked upon the water
> And he spent a long time watching / From his lonely wooden tower
> And when he knew for certain / Only drowning men could see him
> He said, "All men will be sailors then / Until the sea shall free them"
> But he himself was broken / Long before the sky would open
> Forsaken, almost human / He sank beneath your wisdom like a stone

**PEN:**
```text
S~ M≈ V. R: D*>D~ T↓
```
*   `S~`: Free verse (12 lines).
*   `V.`: Indicative: narrative of Jesus as witnessed myth.
*   `R:`: Extended metaphor (Jesus as sailor; drowning as salvation).
*   `D*>D~`: Divine/Cosmic (Jesus, sky, forsaken) to Nature/Elemental (water, sea, stone).
*   `T↓`: Descending: "sank," "broken," entropy and embodiment.

**Verse 3**
> Now Suzanne takes your hand / And she leads you to the river
> She is wearing rags and feathers / From Salvation Army counters
> And the sun pours down like honey / On our lady of the harbour
> And she shows you where to look / Among the garbage and the flowers
> There are heroes in the seaweed / There are children in the morning
> They are leaning out for love / And they will lean that way forever
> While Suzanne holds the mirror

**PEN:**
```text
S~ M≈ V. R≠ D@>D~ T↔
```
*   `S~`: Free verse (13 lines).
*   `V.`: Indicative witness: "she shows you."
*   `R≠`: Antithesis throughout (rags/feathers, garbage/flowers, heroes/seaweed).
*   `D@>D~`: Domestic/Social (Salvation Army, harbour) to Nature/Elemental (river, seaweed, sun).
*   `T↔`: Balanced: reflection and stasis ("holds the mirror," "lean that way forever").

**Song-Level Observation:**
The song operates with cyclical structure: verse-chorus-verse-chorus-verse-chorus. Each verse explores a different facet of spiritual-physical union, using Suzanne, Jesus, and finally Suzanne-as-mirror. The choruses provide anaphoric anchoring with consistent quatrain form while verses remain free-flowing, mirroring the river motif.


#### "Hallelujah" by Leonard Cohen

**Verse 1**
> Now I've heard there was a secret chord / That David played and it pleased the Lord
> But you don't really care for music, do ya?
> It goes like this, the fourth, the fifth / The minor fall, the major lift
> The baffled king composing Hallelujah

**PEN:**
```text
S6 M= V. R: D*>D_ T→
```
*   `S6`: Sextet (6-line stanza).
*   `M=`: Regular meter (Iambic/Waltz time).
*   `V.`: Indicative narrative voice ("I've heard," "It goes").
*   `R:`: Meta-commentary/Description ("The fourth, the fifth" describes the music itself).
*   `D*>D_`: Divine (David, Lord) shifts to Abstract/Technical (Chord, Fourth, Fifth).
*   `T→`: Forward narrative progression.

**Chorus**
> Hallelujah, Hallelujah / Hallelujah, Hallelujah

**PEN:**
```text
S4 M= V! R= D* T↑
```
*   `S4`: Quatrain structure.
*   `V!`: Exclamation/Praise (Apostrophe).
*   `R=`: Repetition.
*   `D*`: Divine domain.
*   `T↑`: Ascending praise.

**Verse 2**
> Your faith was strong but you needed proof / You saw her bathing on the roof
> Her beauty and the moonlight overthrew ya
> She tied you to a kitchen chair / She broke your throne and she cut your hair
> And from your lips she drew the Hallelujah

**PEN:**
```text
S6 M= V. R≠ D*>D. T↓
```
*   `S6`: Sextet.
*   `R≠`: Antithesis (Faith vs Proof, Throne vs Kitchen chair).
*   `D*>D.`: Shifts from Divine/Cosmic (Faith, Throne) to Somatic/Body (Bathing, Hair, Lips).
*   `T↓`: Descending: "overthrew," "tied," "broke," "cut."

**Verse 3**
> You say I took the name in vain / I don't even know the name
> But if I did, well, really, what's it to ya?
> There's a blaze of light in every word / It doesn't matter which you heard
> The holy or the broken Hallelujah

**PEN:**
```text
S6 M= V. R≠ D_>D* T↔
```
*   `S6`: Sextet.
*   `V.`: Indicative/Argumentative.
*   `R≠`: Antithesis (Holy vs Broken).
*   `D_>D*`: Abstract (Name, Word) to Divine (Holy Hallelujah).
*   `T↔`: Balanced/Resigned ("It doesn't matter").

**Verse 4**
> I did my best, it wasn't much / I couldn't feel, so I tried to touch
> I've told the truth, I didn't come to fool ya
> And even though it all went wrong / I'll stand before the Lord of song
> With nothing on my tongue but Hallelujah

**PEN:**
```text
S6 M= V. R≠ D.>D* T↑
```
*   `S6`: Sextet.
*   `R≠`: Contrast (Feel vs Touch).
*   `D.>D*`: Somatic (Touch, Tongue) to Divine (Lord of Song).
*   `T↑`: Ascending finality (Stand before, Hallelujah).

#### "Treaty" by Leonard Cohen

**Verse 1**
> I've seen you change the water into wine
> I've seen you change it back to water, too
> I sit at your table every night
> I try but I just don't get high with you

**PEN:**
```text
S4 M≈ V~ R= D* T↓
```
*   `V~`: Intimate address: "I've seen *you*…" directly confronts the beloved/divine.
*   `R=`: Anaphora: "I've seen you… I've seen you…"
*   `D*`: Divine/Cosmic: water-to-wine miracle, communion table.
*   `T↓`: Descending: proximity without transcendence ("don't get high with you").

**Verse 2**
> I wish there was a treaty we could sign
> I do not care who takes this bloody hill
> I'm angry and I'm tired all the time
> I wish there was a treaty, I wish there was a treaty
> Between your love and mine

**PEN:**
```text
S~ M≈ V~ R= D@>D_ T↓
```
*   `S~`: Irregular: 5 lines, with the refrain folded into the stanza.
*   `V~`: Intimate: the treaty is addressed to a specific "you."
*   `R=`: Anaphora: "I wish there was a treaty… I wish there was a treaty."
*   `D@>D_`: Domestic/Social (war, "bloody hill," treaty) to Abstract ("your love and mine").
*   `T↓`: Exhaustion and anger: the petition has no answer.

**Chorus**
> Ah, they're dancing in the street—it's Jubilee
> We sold ourselves for love but now we're free
> I'm so sorry for that ghost I made you be
> Only one of us was real and that was me

**PEN:**
```text
S4 M≈ V~ R≠ D@>D_ T⇕
```
*   `V~`: Still addressed to "you": "that ghost I made *you* be."
*   `R≠`: Antithesis throughout: sold/free, ghost/real, you/me.
*   `D@>D_`: Social/Civic (dancing, Jubilee, street) to Abstract (ghost, real, identity).
*   `T⇕`: Ironic inversion: the liberation framing ("Jubilee," "free") is immediately undercut by the confession that follows.

**Verse 3**
> I haven't said a word since you been gone
> That any liar couldn't say as well
> I just can't believe the static coming on
> You were my ground, my safe and sound
> You were my aerial

**PEN:**
```text
S~ M≈ V~ R= D_>D~ T↓
```
*   `S~`: Irregular: 5 lines, closing couplet breaks the quatrain form.
*   `V~`: Intimate elegy: "You were *my* ground."
*   `R=`: Anaphora: "You were my… You were my…"
*   `D_>D~`: Abstract (words, static, communication) to Nature/Elemental (ground, aerial: both earthing rod and sky antenna).
*   `T↓`: Loss and silence: the other was the infrastructure of the self.

**Verse 4**
> I heard the snake was baffled by his sin
> He shed his scales to find the snake within
> But born again is born without a skin
> The poison enters into everything

**PEN:**
```text
S4 M≈ V. R: D~>D* T↓
```
*   `R:`: Extended metaphor: the snake as emblem of sin, transformation, and the failure of rebirth.
*   `D~>D*`: Nature/Elemental (snake, scales, skin) to Divine/Cosmic (sin, born again, poison as spiritual corruption).
*   `T↓`: Hard descent: "the poison enters into everything" closes with total entropy.

**Verse 5** *(Repeat of Verse 2)*

Same PEN annotation as Verse 2: `S~ M≈ V~ R= D@>D_ T↓`

**Song-Level Observation:**
Treaty operates as a legal-spiritual complaint: the speaker addresses an unnamed "you" who is simultaneously the beloved and a deity-figure, conflating romantic and divine failure. The central device is a legal-political lexicon (treaty, hill, sold, free, Jubilee) overlaid on religious imagery (water-to-wine, Jubilee as sabbath year, snake, born again), held together by a predominantly `V~` intimate stance, with `V.` witnessing in Verse 4. The structural arc moves from *witnessing* (V1) → *petition* (V2) → *confession* (Chorus) → *elegy* (V3) → *theological digression* (V4) → *return to petition* (V5). Verse 4 is the pivot: it generalises the failed relationship into a cosmological principle: transformation without protection exposes you to the very poison you shed. The chorus's `T⇕` captures the formal tension of the song: Jubilee announces freedom while the speaker confesses to having made the other a ghost.

## Quick Reference

| Need | Example |
| :--- | :--- |
| Loose quatrain with antithesis | `S4 M≈ V. R≠ D* T↑` |
| Intimate address | `S4 M≈ V~ R= D* T↓` |
| Sextet with regular meter | `S6 M= V. R: D* T→` |
| Primary and supporting rhetoric | `R=,:` |
| Imagery domain shift | `D~>D.` |
| Ironic emotional inversion | `T⇕` |
| Live capture | `4 ≈ ^ ≠ *` |

Use the symbol table above for the full vocabulary. Structure and meter remain required, including in shorthand.

## Changelog

### [1.0.0] - 2026-02-17

#### Added
- Initial formalized specification.
- Core axes: Structure (S), Meter (M), Voice (V), Rhetoric (R), Domain (D), and Vector (T).
- Symbol tables for all axes including domain types (Divine, Somatic, Nature, Abstract, Domestic).
- Suffix modifiers for domain transitions (`>`).
- Live mode shorthand notation.
