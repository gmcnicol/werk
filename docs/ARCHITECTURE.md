# Werk Architecture

## Product Shape

Werk is one REAPER JSFX instrument containing:

- three fixed role slots;
- selectable Werk engines;
- shared musical conversation;
- shared Form;
- sixteen semantic drum voices;
- REAPER note-map integration;
- immediate-mode `gfx` views.

A Lua companion may later support REAPER project integration, file selection and editable MIDI rendering where JSFX alone is the wrong boundary. Do not introduce it before a Victory needs it.

## Dependency Direction

```text
Werk views
    ↓
Werk application behaviour
    ↓
Form, slots and conversation
    ↓
Engine contract
    ↓
MIDI and REAPER adapters
```

UI helpers support views but must not own musical behaviour.

## Engine Boundary

An engine provides rhythmic character. It must be capable of interpreting:

- its assigned role;
- current section context;
- relevant published state from the other slots;
- shared timing and transport context;
- semantic output voices.

Do not create separate engine implementations for each slot. Role-aware behaviour belongs to the combination of engine and role profile.

## Conversation Boundary

Conversation operates on musical state and context, not by blindly merging or deleting MIDI notes.

Productive overlap is preserved. Coordination may influence density, emphasis, fills, phrase response and structural ownership, but it should not reduce the three musicians to one centrally generated pattern.

## Mapping Boundary

Engines emit semantic voices. A shared mapping layer resolves them to concrete MIDI notes.

REAPER note-name file parsing belongs to the shared host or an appropriate REAPER adapter, never separately inside each engine.

## Form Boundary

Form describes section-level development. Engines interpret it through their roles.

Form does not contain every generated note and should not become a low-level clip sequencer.

## Immediate-Mode UI

The UI is regenerated every frame from current state and viewport.

```text
read state and input
        ↓
measure visible content
        ↓
derive rectangles
        ↓
issue controls and draw
        ↓
return interactions
```

There is no retained widget hierarchy.

Persistent UI state is limited to values that genuinely survive frames, such as:

- focused control;
- active drag;
- open popover;
- scroll offset;
- selected view;
- product state.

## UI Correctness Rules

- Every component receives an explicit rectangle.
- Nothing draws or handles input outside its rectangle.
- Text is measured and given a deliberate fit strategy.
- Natural and minimum view sizes are calculated rather than guessed.
- Initial window size must correctly present the active first-class view.
- Smaller sizes degrade through responsive layout, clipping, scrolling or simplification by deliberate choice.
- Rendering code should contain very little coordinate arithmetic.
- Padding and gaps use a small consistent spacing vocabulary rather than scattered magic offsets.

## GFX Evolution

Werk is the first immediate-mode GFX implementation. It is not initially divided into a product and a generic framework.

Start with concrete Werk views. Extract only small helpers justified by present duplication or maintenance pain. Do not create generic layout trees, widget registries, theme providers or speculative extension systems.

A separate GFX project may eventually be extracted when:

- the reusable boundary already exists in practice;
- core code contains no Werk assumptions;
- materially different views have tested the API;
- another real project needs it;
- extraction is cheaper than continued in-tree ownership.

## Accessibility Boundary

Accessibility concerns belong in normal controls and layout from the start:

- scalable dimensions and typography;
- large targets;
- keyboard navigation and visible focus;
- alternatives to fine drag gestures;
- labels alongside icons;
- no colour-only state;
- predictable order and interaction;
- reduced motion where motion is used.

## HIT Integration Boundary

HIT may provide composition-level structure and intention. Werk returns or renders rhythmic material.

Neither project should reach into the other's internal state or duplicate its domain model.