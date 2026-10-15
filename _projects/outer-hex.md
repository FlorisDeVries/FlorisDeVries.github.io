---
layout: project
id: outer_hex
title: Outer Hex
summary: A turn-based tactical deckbuilding expedition across a dangerous hex-grid frontier
platform: PC · Godot 4, C#
logo: assets/images/projects/Carts3D/EarlyScreenshot.png
date: 2026-08-17
start_date: 2026-08-09
ongoing: true
---

## Project Overview

**Outer Hex** is a solo hobby project about leading an expedition across a dangerous frontier. It combines turn-based tactical combat, deterministic deck-building, and exploration on one continuous hex map. Each friendly unit can take a basic action every turn, while cards add exceptional movement, attacks, repositioning, defense, and exploration effects.

The player starts near a castle and pushes into the fog to find rewards, outposts, enemy camps, and the route to a final boss. Gold supports a shared **Recruit** action for deploying unlocked units and buildings. Captured outposts improve income and extend where new forces can be deployed, while enemy raids and threats keep advancing even when they are out of sight. The boss can be challenged at any time; optional objectives can weaken the final encounter for players who choose to explore further.

<div class="project-images">
  <img src="/assets/images/projects/Carts3D/EarlyScreenshot.png" alt="Early Outer Hex gameplay on a low-poly hex battlefield" class="project-image" />
</div>
<br>
<br>

---

<br>
## Tactical Cards and Enemy Intentions

Enemies telegraph their next action before they act. They commit to an action type, while the player uses positioning and cards to change how that action resolves. Moving a target, blocking a route, or pulling an enemy can turn a dangerous forecast into an opportunity.

Cards complement unit activations instead of replacing a traditional build menu or technology tree. The deck cycles deterministically: when the draw pile empties, the discard pile becomes the new draw pile without shuffling. The order in which cards are played therefore helps determine when they return, making sequencing part of the tactical plan.

Exploration develops both the deck and the roster. Dispatches offer a choice of cards or unlocks for the Recruit action, and deeper routes can present stronger rewards. Players decide whether to build strength and weaken the boss through optional objectives, or take a shorter, riskier route to the final fight.

<br>
<br>

---

<br>
## Technical Direction and Scope

Outer Hex is built in **Godot 4** as a 3D project with **C#/.NET** scripting. Its current visual direction pairs a low-poly world with a clean geometric interface. The core game uses a command-driven architecture, with reversible actions and history supporting undo and redo during a run.

The current focus is a complete single-player expedition: tactical combat, fog-of-war exploration, card and roster progression, outposts, enemy raids, and a final boss. Two handcrafted maps share the same core content while offering different routes and spatial choices. Procedural maps, multiplayer, and broad meta-progression are outside the current slice.

## Reflection

Outer Hex has grown from an early RTS and deck-building experiment into a more focused turn-based tactics game. The central idea is still the relationship between a deterministic card cycle and strategic growth, but cards now shape moment-to-moment decisions on the battlefield while unit activations and a global Recruit action provide the basic structure.

The project is ongoing, and its design continues to evolve through implementation and playtesting. I enjoy using it to explore how readable enemy intentions, a shared tactical and strategic map, and careful card sequencing can make each turn feel consequential.

### Source Code

You can follow the project's development on [GitHub](https://github.com/FlorisDeVries/outer-hex).
