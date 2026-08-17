---
layout: project
id: carts_3d
title: Carts 3D
summary: An RTS where deck-building is the tech tree
platform: Godot 4, C#
logo: assets/images/projects/Carts3D/GameplayOverviewPlaceholder.svg
date: 2026-08-17
start_date: 2026-08-09
ongoing: true
---

## Project Overview

**Carts 3D** is a solo hobby project that combines the base building and battlefield control of a real-time strategy game with the progression of a deck-builder. Instead of using a traditional build menu or separate technology tree, the player grows their economy, deploys units, places buildings, and unlocks upgrades by drawing and playing cards.

The goal is a focused, single-player PvE experience with matches of roughly thirty minutes. Each match starts slowly as the player establishes an economy, then steadily increases the pressure through enemy waves and exploration until the player is ready to confront the final boss. The project is still at an early, experimental stage, so these ideas will continue to change as I prototype them.

<div class="project-images">
  <img src="/assets/images/projects/Carts3D/GameplayOverviewPlaceholder.svg" alt="Placeholder for a Carts 3D gameplay overview" class="project-image" />
  <p><b>Suggested screenshot:</b> An in-game view showing the current state of the experiment, ideally with the card hand and some of the playable world visible.</p>
</div>

---

## The Core Experiment

The deck is both the player's build menu and technology tree. Unit cards deploy combat units, building cards expand the base and economy, upgrade cards improve what is already on the field, and spell cards create one-time effects. New cards are earned through exploration, technology buildings, and objectives.

The main experiment is the deterministic card cycle. When the draw pile runs out, the discard pile becomes the new deck **without being shuffled**. The order in which cards are played therefore determines the order in which they return, making card sequencing a resource the player can plan around.

The planned map consists of connected hexagonal nodes containing outposts, optional objectives, enemy camps, and a final boss. Enemy waves create the pressure to keep expanding, while exploring can reward the player with new cards or weaken the boss before the final fight.

---

## Technical Direction and Scope

The game is being developed in **Godot 4** as a 3D project with **C#/.NET** scripting and a top-down camera. The first target is one complete single-player match with a fixed starting deck, exploration, escalating waves, and a final boss. The focus is currently on testing the core loop rather than producing lots of content or polished artwork.

## Reflection

**Carts 3D** has only just started, so there is no real outcome to reflect on yet. At this stage, it is deliberately experimental: a place where I can try ideas, discover what works, and change direction without being tied to a finished design.

It is also a project I use to unwind and get my mind off other things. Working on a small piece of the game gives me a way to reset while still creating something. For now, I am enjoying the experimentation and focusing on finding out whether the combination of RTS mechanics and deterministic deck-building is as fun to play as it is to think about.

### Source Code

You can follow the project's development on [GitHub](https://github.com/FlorisDeVries/carts-3d).
