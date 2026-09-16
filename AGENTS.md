# Asteroid Survival

## Project Overview

This is a simple one-screen 2D arcade game built in Godot 4 using GDScript.

The player controls a spaceship near the center of the screen and attempts
to survive for as long as possible while asteroids enter from the edges of
the screen and move toward the player.

The game should be intentionally small and simple. Avoid unnecessary
systems, abstractions, or dependencies.

## Core Game Loop

1. The game begins immediately.
2. The player controls a spaceship using directional movement.
3. Asteroids periodically spawn from random locations along the edges
   of the screen.
4. Asteroids travel generally toward the player's position.
5. The player's score is the number of seconds they have survived.
6. If an asteroid collides with the player's spaceship, the game ends.
7. The final survival time is displayed.
8. The player can restart the game.

## Design Goals

The game should:

- Be easy to understand immediately.
- Become increasingly difficult to survive.
- Reward careful movement and positioning.
- Provide clear visual feedback when the player loses.
- Allow important gameplay values to be easily tuned during playtesting.

## Project Structure

Keep the project organized using the following directory structure:

- `scenes/` — All Godot scene files (`.tscn`) should be stored here.
- `assets/` — All game assets should be stored here, including images,
  sprites, sound effects, music, and fonts.
- `scripts/` — All GDScript files (`.gd`) should be stored here.

Do not place scenes, assets, or scripts in the project root unless there
is a specific reason to do so.

The `project.godot` file should remain in the project root.

## Technical Requirements

- Use Godot 4.x.
- Use GDScript.
- Use Godot's normal scene/node architecture.
- Prefer simple solutions appropriate for a small game.
- Do not add external plugins or dependencies.
- Do not modify files inside the `.godot/` directory.
- Avoid unnecessary global state or autoloads.
- Use signals where appropriate to communicate between scenes.

## Suggested Scene Structure

Prefer separate scenes for major game objects.

The project will likely contain scenes representing:

- Main game
- Player spaceship
- Asteroid
- Game-over / UI elements

All scene files should be stored in the `scenes/` directory.

Do not create additional systems or scenes unless they provide a clear
benefit to the game.

## Player

The player should:

- Move in two dimensions.
- Remain within the visible play area.
- Respond immediately to player input.
- Collide with asteroids.

Movement values such as speed should be exposed in the Godot Inspector
when practical so they can be tuned without modifying code.

## Asteroids

Asteroids should:

- Spawn outside or at the edge of the visible play area.
- Spawn from different sides of the screen.
- Travel across the play area in a direction that threatens the player.
- Collide with the player.
- Be removed when they are no longer relevant.

Important values such as asteroid speed and spawn frequency should be
easy to tune.

## Difficulty

Difficulty should increase over time.

Prefer simple, tunable approaches such as:

- Increasing asteroid spawn frequency.
- Increasing asteroid speed.

Do not introduce complicated difficulty systems without being asked.

## Score

The score represents survival time.

- Begin timing when gameplay starts.
- Display the current survival time during gameplay.
- Stop the timer when the player is hit.
- Display the final survival time on the game-over screen.

## Development Guidelines

When making changes:

1. Inspect the existing project before modifying it.
2. Preserve existing behavior unless the requested change requires
   modifying it.
3. Make the smallest reasonable change that accomplishes the requested task.
4. Avoid unrelated refactoring.
5. Prefer readable code over clever code.
6. Expose gameplay values in the Inspector when they are likely to need
   playtesting and tuning.
7. Do not add features that were not requested.
8. Follow the project's directory structure when creating new files.

## Working With This Project

For non-trivial changes:

1. Examine the relevant scenes and scripts.
2. Explain the proposed implementation before making major architectural
   changes.
3. Implement one coherent feature at a time.
4. Check for GDScript errors after making changes.
5. Run the project when possible.
6. Report which files were changed and briefly explain why.

## Important Design Principle

Do not make game-design decisions unless specifically asked.

If a requested feature requires an unspecified design decision, identify
the decision and ask for guidance rather than inventing substantial new
gameplay.

Implementation should support the intended design, not determine it.