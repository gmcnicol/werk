# Werk Domain Model

## Werk

The complete rhythmic composition instrument.

Werk hosts three fixed slots, selected engines, shared form, semantic drum mapping, conversation state and immediate-mode UI.

## Slot

A fixed compositional responsibility.

### Slot A — Primary Groove

Establishes the rhythmic spine, continuity and core identity.

### Slot B — Counter-Rhythm

Challenges, enriches and converses with the primary groove through displacement, syncopation, contrast and response.

### Slot C — Structural Punctuation

Marks form through fills, arrivals, departures, breaks, turnarounds, crescendos and transitions.

A slot is not a fixed set of drum voices. All roles may use kicks, snares and other voices.

## Engine

A rhythmic personality and decision-making dialect.

Initial engine family:

- PulseWerk
- DanseWerk
- MetalWerk
- CrescendoWerk

An engine interprets the role it occupies. Engine character and slot responsibility combine to produce behaviour.

## Role Profile

The behavioural influence a slot applies to an engine.

It changes priorities, phrase stability, variation, response style and structural responsibility without replacing the engine's identity.

## Conversation

The evolving musical relationship between active slots.

Conversation is not MIDI collision avoidance. Engines expose meaningful state and respond to one another while retaining autonomy.

## Published State

A compact description of an engine's current musical behaviour, such as:

- sparse;
- busy;
- stable;
- syncopated;
- building;
- resting;
- filling;
- resolving;
- creating tension.

## Conductor

The shared coordination capability that makes the three slots aware of the whole.

It supports role hierarchy, density awareness, fill ownership, phrase context and conversation. It should preserve productive overlap rather than suppress every simultaneous event.

## Semantic Voice

One of sixteen musical drum identities used internally by Werk independently of a concrete MIDI note.

A semantic voice is resolved through the active note map before MIDI output.

The exact sixteen-voice vocabulary will be established through the relevant Victory rather than fixed speculatively here.

## Note Map

A mapping between Werk semantic voices and concrete MIDI notes and labels for a chosen drum instrument.

Werk must be able to interpret relevant REAPER MIDI note-name map files.

## Form

The song-level rhythmic structure.

Form contains sections and their intended development, including duration, energy, variation, participation and transition behaviour.

## Section

A bounded part of Form with an identity and rhythmic intention.

A section influences all three slots but does not prescribe every note.

## Intention

A musical request expressed above note level, such as more motion, preserve weight, delay the climax, increase tension or simplify before arrival.

## Performance

The live behaviour of Werk during playback or exploration.

Performance can inform Form and eventually become editable composition material.

## Immediate-Mode View

A Werk interface view issued from current state and current viewport each frame.

The view has no retained widget hierarchy. Persistent state is limited to genuine interaction and product state such as selections, focus, active drag, scroll position and musical settings.

## Rectangle

The explicit drawing and interaction boundary assigned to a UI element during the current frame.

Every component must remain inside its rectangle.

## HIT Boundary

HIT owns composition-level structure and intention.

Werk owns rhythmic interpretation, engine conversation and generated drum material.

HIT asks what the drums should achieve. Werk decides how its musicians achieve it.