# The Cave — A Game That Grows

**Generation 0 · Experimental browser game and emergent-systems laboratory**

[Play The Cave](https://thebiggesttaco.github.io/The-Cave/)

The Cave explores a different approach to game development: **grow a game instead of specifying every object and behavior in advance**. Start with space, points, relationships, time, and a shared, evolving atomic rulebook. Let interaction, mutation, and connection determine which properties are expressed—and observe what structures and behaviors arise.

The goal is **not to claim that we've created life**. It is to develop a playable system capable of surprising, understandable, and reproducible behavior. Artificial-life-like properties—self-maintenance, adaptation, repair, reproduction—are research questions, not implemented features.

This repository is an independent prototype. The original Cave ChatGPT Site remains untouched.

## Play

Open [the GitHub Pages build](https://thebiggesttaco.github.io/The-Cave/) or open `index.html` locally in a browser. No build process is required.

- **Move:** WASD, arrow keys, touch direction buttons, or an Xbox-compatible controller.
- **Interact:** E, Space, the Interact button, or controller A.
- **Objective:** Control the fifth atom among four autonomous atoms; connect or break lines, create circular boundaries, and explore whether closed geometry produces an enclosure.
- **Save / Load:** Browser `localStorage`; saves are local to that browser.

### Five-atom play experiment

The Play tab now starts with **four autonomous atoms and a fifth player-controlled atom**. The previous scripted room and exit have been replaced with a geometric enclosure experiment. Four line connections can enclose a room when they form a closed cycle; individual atoms can also express circles that the player can enter and leave. Use E / Space / controller A to connect or break nearby lines, and C / controller X to toggle a nearby circle. Live controls adjust spring bonds, collision resistance, attraction, and circle-boundary resistance.

The earlier four-port atom visualization was a preliminary prototype: Each has its own mutation and rotation state, plus four internal connection ports:

| Port | Color | Intended property |
| --- | --- | --- |
| Elasticity | Teal | Stretching and recovery |
| Resistance | Gold | Opposition to movement or deformation |
| Curvature | Purple | Bending relationships |
| Closure | Rose | Open/closed boundaries |

Lines attach to **ports within the atoms**, rather than always running center-to-center. Port selection currently depends on the direction between atoms. Activating and connecting atoms changes their mutation state; their ports rotate gradually, and connections can be rendered differently based on their ports.

**Current limitation:** These port names are *potential properties*, not four fully implemented physical effects. The earlier port visualization was an interaction/visualization prototype. The current five-atom Play mode has simple motion, spring bonds, collision forces, attraction, and circle-boundary forces, but it is **not yet driven by the same shared physics module as the Big Bang Laboratory**. A port's appearance alone should not be mistaken for an emergent material behavior.

## Big Bang Laboratory

A separate canvas-based sandbox explores the behavior of **128 interacting particles** under a seeded initial condition (`CAVE-001`).

Current experiments include:

- Attraction, short-range repulsion, collisions, spring bonds, and bond breakage.
- Density-triggered growth and mutation; bond fatigue; variable connectivity.
- Open/closed bond states and circular perimeter interactions.
- Circle containment and particle memory tails.
- Center-of-mass movement, ejection, and angular-motion observatories.
- Optional momentum-correction comparison and center-outward division force.
- Experimental **mutation-driven local adaptation**, which changes responses to selected forces according to mutation and crowding.

The laboratory has Pause/Run, Step, Reset/Replay, Pulse, and speed controls. The physics mode switches can be changed **while the simulation is running**, preserving the existing particle world rather than replaying the seed. Disabling a rule may intentionally clear rule-specific state (for example, closed-bond state).

Click or tap the laboratory canvas to pulse it. With a compatible gamepad, A pulses and the left stick selects direction.

**Scientific caveats:** This is toy physics, not a cosmological or biological model. The center-outward division force is an explicit external bias, so division under that setting is not proof of spontaneous self-division. The angular observatory has shown `NaN` readings in some runs and needs debugging. Reset repeats seeded initial conditions, **not** the history of user pulses or live toggle changes.

## Core design model

- **Space** is the environment in which points exist. Points do not create space.
- **Points / atoms** are the fundamental interactive entities.
- **Relationships** between atoms can express lines, elasticity, resistance, curvature, closure, and other properties.
- **Circles / boundaries** enclose regions of existing space; their interiors may contain other points.
- **Time and history** let states, relationships, and configurations change.
- **Mutation** changes how an atom expresses rules it already possesses.
- **Rulebook updates** change the definition of the atom itself.

The ambition is for **every atom to share a common rulebook** while retaining its own state, history, and connections. Complex objects should arise from configurations of these atoms wherever possible, rather than from predefined object categories.

Importantly, the rulebook must **remain editable and versionable**. We should be able to improve the atom without becoming locked into our earliest assumptions. Possible future update modes include live updates, generational coexistence, and seeded replay comparisons. Those update modes are design goals, not yet a finished versioning system.

## Views

- **Play:** Five-atom physics experiment, line-loop enclosures, circular boundaries, and player-controlled movement.
- **Rule Map:** Current conceptual rules and atomic-port model.
- **Stems:** Generation 0 ancestry and a place for future branches.
- **Big Bang Lab:** Physics experiments, instrumentation, and live rule toggles.

## Development direction

The next challenge is to connect the playable atoms' internal ports to **actual local physics** rather than only visual effects, then observe whether those rules produce interesting and useful differences. We also want more reliable observatory measurements, preserved experimental histories, and ways to compare atom-rulebook versions without losing existing worlds.

The design principle is simple:

> **The designer creates the possibility space. The game discovers its contents. The player participates in that discovery.**

The Cave is an experiment in making a game whose consequences are not entirely known in advance—even to its developers.
