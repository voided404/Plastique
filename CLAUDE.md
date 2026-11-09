Plastique Project Operating Instructions

This file defines the permanent development standards for the Plastique project.

The project launch prompt defines the initial mission, agent assignments, and development roadmap. This file defines the rules that must continue to be followed during all subsequent work.

Read this file before making changes.

---

1. Project Identity

Game: Plastique
Tagline: A Little World of Big Explosions.
Level Editor: Plastique Workshop
Platform: Android
Engine: Godot 4.x
Language: GDScript

Plastique is an original arcade game set in a miniature universe made entirely of colorful molded plastic.

Maintain an original identity. Do not copy protected characters, artwork, maps, audio, logos, or distinctive expression from existing games.

The game and its integrated level editor are both first-class products.

---

2. Non-Negotiable Visual Direction

The entire world must look like a premium miniature plastic toy universe.

This applies to all characters, environments, objects, effects, and UI elements.

Maintain a cohesive visual language using:

- Glossy, satin, and matte molded plastic.
- Translucent and clear colored plastic.
- Rounded geometry and soft bevels.
- Chunky toy-like proportions.
- Convincing highlights and reflections.
- Carefully composed studio-style lighting.
- Soft shadows and contact shadows.
- Selective depth of field and subtle tilt-shift.
- Miniature-diorama camera composition.

Even objects representing natural materials must look like plastic toy interpretations.

Do not introduce realistic wood, stone, dirt, or organic textures that break the aesthetic.

Depth of field and visual effects must never compromise gameplay readability.

Use "ART_DIRECTION.md" as the detailed visual reference.

Review actual rendered output when making significant visual changes. Do not judge visual quality from code alone.

---

3. Architecture and Coding Standards

Use Godot 4.x and GDScript.

Prefer typed GDScript where practical and native Godot capabilities where appropriate.

Maintain clear separation between:

- Gameplay logic.
- Rendering.
- Input.
- Game state.
- Level data.
- Persistence.
- UI.
- Audio.
- Plastique Workshop.

Keep gameplay logic independent of visual presentation wherever practical.

Use shared interfaces and data structures rather than duplicating functionality.

The game and level editor must use the same level definitions, assets, and validation rules.

Prefer incremental changes over architectural rewrites.

Do not replace working systems simply because another implementation seems more elegant.

Before changing an established architecture:

1. Understand the existing implementation.
2. Identify a concrete problem.
3. Evaluate the impact on dependent systems.
4. Write or update tests.
5. Document significant architectural decisions.

Avoid unnecessary dependencies, monolithic scripts, duplicated logic, and premature abstractions.

---

4. Testing Standards

Test-driven development is required for core functionality.

Use this cycle:

1. Write a failing test.
2. Verify the expected failure.
3. Implement the solution.
4. Run the test.
5. Refactor.
6. Run regression tests.

Test gameplay rules independently from rendering wherever possible.

Maintain tests for:

- Movement and collision.
- Bomb placement and timers.
- Explosion propagation and chain reactions.
- Destructible obstacles.
- Enemy behavior.
- Power-ups and scoring.
- Game-state transitions.
- Level serialization and validation.
- Editor operations.
- Undo and redo.
- Save and load.
- Input handling.

Never delete or weaken tests simply to make a build pass.

Never claim a test passed unless it was actually executed successfully.

Use headless testing where practical.

---

5. Plastique Workshop

The level editor must remain a fully supported product feature.

It must use the same level data model and runtime systems as the game.

Preserve these requirements:

- Create, open, save, duplicate, rename, and delete levels.
- Paint, place, select, move, and erase objects.
- Configure level dimensions and object properties.
- Support undo and redo.
- Validate levels.
- Display level thumbnails.
- Test-play levels using actual gameplay systems.
- Return from test play without losing editor state or unsaved changes.

Use a versioned level format and preserve compatibility through explicit schema migrations where necessary.

Do not introduce a second, incompatible level representation.

Use "LEVEL_EDITOR.md" for detailed editor specifications.

---

6. Android and Input

Android is the primary platform.

Support both touchscreen and physical controllers.

Use a shared input abstraction so gameplay does not depend directly on a particular device.

Preserve:

- Responsive touch controls.
- Physical controller support.
- Controller hot-plugging.
- Menu navigation.
- Appropriate screen and aspect-ratio handling.
- Android lifecycle behavior.
- Pause and resume.
- Performance-conscious rendering.

Do not claim physical-device verification when only emulator testing has been performed.

---

7. Agent Responsibilities and Collaboration

Follow the agent responsibilities established in the project launch plan.

The Technical Lead owns architecture and integration.

The Independent QA Director must remain independent of implementation approval.

Agents must communicate interface changes and file ownership before making overlapping changes.

Avoid concurrent edits to the same files.

Do not redesign established architecture independently of the Technical Lead.

QA findings must be addressed or explicitly documented. Do not dismiss failures simply because the implementation agent believes the feature is complete.

---

8. Git Discipline

Use the cloud environment's local repository clone.

- Work on branches, never directly on main.
- Never force-push.
- Make meaningful commits.
- Commit working milestones frequently.
- Inspect diffs before integration.
- Run relevant tests before committing.
- Do not overwrite unrelated work.
- Preserve recoverable working states.

Do not assume cloud sessions preserve uncommitted work indefinitely.

Checkpoint work according to the available repository workflow.

---

9. Documentation and Persistent State

Keep these documents accurate:

- "README.md"
- "ARCHITECTURE.md"
- "DEVELOPMENT_ROADMAP.md"
- "PROJECT_STATUS.md"
- "CHANGELOG.md"
- "TESTING.md"
- "QA_REPORT.md"
- "ANDROID_BUILD.md"
- "ART_DIRECTION.md"
- "LEVEL_EDITOR.md"

Update documentation when a change materially affects architecture, functionality, setup, or project status.

At the end of substantial work sessions, update "PROJECT_STATUS.md" with:

- Completed work.
- Current work.
- Outstanding tasks.
- Known defects.
- Test results.
- Current Git branch and commit.
- Next concrete actions.

Resume from documented project state rather than restarting completed work.

---

10. Definition of Done

A feature is not complete merely because code has been written.

Before considering a feature complete:

- Verify its behavior.
- Run relevant automated tests.
- Check integration with dependent systems.
- Run regression tests where appropriate.
- Review its visual presentation if applicable.
- Update relevant documentation.
- Obtain independent QA review for significant features.
- Document any remaining limitations.

Never fabricate test results, successful builds, or device verification.

---

11. Autonomous Work

Make reasonable technical decisions independently.

Do not interrupt development for routine questions that can be answered through engineering judgment.

When blocked, investigate alternatives and continue with independent tasks.

Prefer incremental improvements over wholesale rewrites.

Do not silently abandon incomplete work.

Record blockers, tradeoffs, and unresolved issues in the project documentation.

Prioritize working, tested software over plans and reports.

---

12. Guiding Principle

Every development decision should support the same objective:

Plastique should feel like a cohesive, premium miniature plastic universe, with genuinely enjoyable arcade gameplay and a level editor that is useful enough to stand on its own.

Maintain that standard throughout development.