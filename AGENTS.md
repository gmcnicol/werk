# AGENTS.md

## Read First

Before planning or changing Werk, read:

1. `README.md`
2. `docs/CAMPAIGN.md`
3. `docs/PHILOSOPHY.md`
4. `docs/DOMAIN_MODEL.md`
5. `docs/ARCHITECTURE.md`
6. `docs/CURRENT_VICTORY.md`

Treat these documents as the project's constitution.

## Working Rule

Work only towards the Current Victory unless the user explicitly changes it.

Use the available Matt Pocock planning/specification skills to drill the Current Victory into detailed missions, acceptance criteria and implementation plans. Do not pre-empt that workflow by inventing a broad backlog or speculative framework.

## Product Rule

Werk is three rhythmic musicians listening to one another:

- Slot A — Primary Groove
- Slot B — Counter-Rhythm
- Slot C — Structural Punctuation

An engine supplies rhythmic character. A slot supplies compositional responsibility. The same engine must behave differently in different slots.

## UI Rule

Werk uses immediate-mode JSFX `gfx`:

- geometry is recalculated every frame;
- no retained widget hierarchy;
- measure and calculate before drawing;
- every control stays inside its assigned rectangle;
- no clipped text, overflow, accidental overlap or guessed startup size;
- accessibility is part of normal design, not a separate mode;
- do not abstract a generic GFX framework prematurely.

Immediate mode is the implementation style. Werk is the product.

## Scope Rule

If work does not directly advance the Current Victory, defer it or explain why it is necessary now.

Prefer thin, playable vertical slices over infrastructure work.

## Licence

All original project code is MIT licensed.