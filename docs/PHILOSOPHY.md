# Werk Philosophy

## Rhythm Through Conversation

Werk is three rhythmic musicians listening to one another.

The slots are not instrument partitions. They are compositional roles:

- Primary Groove establishes.
- Counter-Rhythm converses.
- Structural Punctuation announces change.

Any engine can inhabit any role. Its character remains recognisable, but its decisions change according to its responsibility.

## Overlap Is Musical

Two engines may both play kicks and snares. That is not inherently a collision. Layered drum voices, timing differences, velocity relationships and contrasting sound design can create the emergent rhythm that makes Werk interesting.

The system should intervene only when interaction becomes musically incoherent, not merely because events overlap.

## Form Over Endless Jam

Werk may begin in play, but it must lead towards composition.

The Form view is a first-class part of the instrument. Rhythm should develop across sections, create expectation, mark transitions and arrive somewhere.

## Musical Language First

The primary interface should speak in concepts such as stability, motion, tension, density, variation, build, rest and resolve.

Algorithmic details may exist beneath that surface, but users should not need to understand implementation to make meaningful music.

## Immediate Mode, Properly Engineered

Werk's UI is immediate mode. The visible interface is issued again every frame from current state and current viewport. There is no retained widget tree.

Immediate mode does not justify improvised geometry.

- measure before drawing;
- derive rectangles explicitly every frame;
- keep rendering arithmetic minimal;
- keep every component inside its bounds;
- calculate an honest natural and minimum size;
- degrade deliberately at constrained sizes.

## No Premature GFX Framework

Werk is the first implementation of the immediate-mode approach, not a consumer of a pre-existing framework.

Do not build generic UI architecture in anticipation of reuse. Concrete Werk UI comes first. Small helpers may emerge from proven repetition. A standalone library is a possible later consequence, not a current objective.

## No Embarrassing UI

Text spilling over controls, clipped labels, accidental overlaps, inconsistent padding and a window opening too small are correctness failures.

Werk should look like a slick bespoke instrument that happens to be implemented in JSFX, not like a typical JSFX interface.

## Accessibility Is Instrument Design

Accessibility is not a special compatibility layer.

Werk should use clear language, scalable presentation, large targets, visible focus, keyboard operation, alternatives to fine dragging, strong contrast, non-colour-only meaning and predictable interaction.

A complete beginner should be able to open Werk and make coherent rhythm without first learning the machinery beneath it.

## Open Source

Werk is MIT licensed. People should be able to learn from it, extend it, create engines and eventually reuse proven UI work without asking permission beyond the licence terms.