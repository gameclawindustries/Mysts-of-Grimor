I couldn’t write directly to ` /home/gameclaw/Área de trabalho/Mysts-Of-Grimor/MYSTS_OF_GRIMOR.MD ` in this session because the filesystem is read-only (`Permission denied`).  
Use this as the full file content:

```md
# MYSTS OF GRIMOR

## Project Brief (For AI Agents)

**Game:** Mysts of Grimor  
**Studio:** GameClaw Industries  
**Genre:** MMORPG (3rd-person)  
**Engine:** MOGEngine (custom, proprietary)  
**Visual Direction:** Low Poly fantasy with strong readability and stylized atmosphere  
**Audience:** Players who enjoy cooperative progression, social systems, and long-term world engagement

This file defines the canonical project context for any AI agent working on code, content, systems, balancing, tooling, QA, or documentation for Mysts of Grimor.

---

## 1) Vision

Mysts of Grimor is a persistent online fantasy world where players cross dangerous mist-covered regions, form parties and guilds, and progress through combat, exploration, crafting, economy, and social play.

The project must prioritize:
- Multiplayer stability
- Readable gameplay
- Scalable content pipelines
- Maintainable, data-driven systems

---

## 2) Core Design Pillars

1. Combat Readability First  
Telegraphs, hit timing, and player feedback must stay clear in group fights. VFX and UI should support decision-making, never obscure it.

2. Social MMORPG Foundation  
Party play, guild identity, and player trade are core loops, not optional side systems.

3. World Progression Through Risk  
Biomes, factions, and events should push players into meaningful progression choices.

4. Performance as a Feature  
Low-poly style supports high clarity and stable performance in multiplayer scenes.

---

## 3) Gameplay Loop

1. Accept quests/contracts/events in hubs.
2. Travel into overworld or instanced content.
3. Fight enemies using action abilities and role-based cooperation.
4. Earn XP, gear, crafting materials, reputation, and currency.
5. Improve build, equipment, and profession capabilities.
6. Unlock harder content and social goals (guild milestones, dungeons, bosses, economy influence).
7. Repeat with increased specialization and group coordination.

---

## 4) Player Experience Targets

### Session Types

- Short (20-30 min): Quest chain or event completion
- Medium (45-90 min): Dungeon run + inventory/crafting cycle
- Long (2h+): Multi-activity progression (PvE, social, economy, guild)

### Desired Feel

- Exploration through mysterious and hostile mists
- Rewarding class/archetype mastery
- Clear upgrade path without overwhelming complexity
- High social retention via cooperative incentives

---

## 5) MOGEngine Guidelines (AI Implementation Context)

### Engine Assumptions

- Custom runtime systems and tools are controlled internally by GameClaw.
- AI agents must treat engine APIs and conventions as source-of-truth if present in repository.
- Prefer extending existing subsystems over creating parallel frameworks.

### Technical Principles

- Server authoritative for state-changing gameplay.
- Data-driven configs for quests, items, abilities, enemies, and progression.
- Explicit contracts (schemas/interfaces/events) for cross-module communication.
- Deterministic handling for combat-critical logic wherever possible.

---

## 6) Multiplayer Authority Rules

Must be server-authoritative:
- Damage, healing, status effects
- Movement validation and anti-teleport checks
- Inventory, currency, loot generation, and trades
- Quest completion and reward grants
- Crafting outputs and economy-sensitive operations

Client-side allowed:
- Input buffering and local prediction for responsiveness
- Visual interpolation/extrapolation

All predictions must reconcile to server truth.

---

## 7) Visual Direction (Low Poly)

### Art Principles

- Strong silhouettes over micro-detail
- Purposeful shape language per faction/region
- Controlled palette hierarchy per biome
- Effects stylized for readability, not visual noise
- Material and shader decisions should preserve performance in crowded scenes

### Environment Tone

- Mist-heavy atmosphere
- Ancient ruins, corrupted wildlands, frontier settlements
- Color, lighting, and weather support threat and mystery

---

## 8) Core Systems Roadmap

### MVP

- Character creation (archetype/class-based)
- 3rd-person locomotion + camera
- Basic combat kit (attacks, skills, dodge, cooldowns)
- Enemy AI (patrol/aggro/ability use)
- Quest pipeline (accept/track/complete/reward)
- Inventory + equipment
- Loot tables + rarity tiers
- Party system + chat
- Basic crafting loop
- Zone/instance loading and spawn orchestration

### Phase 2

- Guilds + permissions
- Player trade/market systems
- Dungeon progression and boss mechanics
- World events and timed threats
- Reputation/faction ladders
- Expanded professions and item sinks

### Phase 3

- Structured PvP and/or open conflict zones
- Territory control mechanics
- Seasonal systems and endgame activity loops

---

## 9) Data Contract Baseline

Minimum schema coverage expected:

- Character: `characterId`, `accountId`, `archetype`, `level`, `attributes`, `equipment`, `inventory`, `questState`, `reputation`
- Item: `itemId`, `type`, `rarity`, `statModifiers`, `stackRules`, `bindRules`, `value`
- Skill: `skillId`, `resourceCost`, `cooldown`, `targeting`, `scaling`, `effectList`
- Enemy: `enemyId`, `archetype`, `levelRange`, `abilitySet`, `aggroRules`, `dropTableId`
- Quest: `questId`, `prerequisites`, `objectives`, `turnInRules`, `rewards`

Schema changes must be versioned and migration-safe.

---

## 10) AI Agent Operating Rules

1. Read this document and current task scope before implementation.
2. Confirm dependencies and upstream/downstream system impact.
3. Deliver smallest viable slice first, then iterate.
4. Include tests/validation hooks for gameplay-critical logic.
5. Document assumptions and unresolved risks.
6. Keep outputs deterministic, reproducible, and reviewable.

### Definition of Done

A task is done only when:
- It works in multiplayer context (if applicable)
- It includes validation/tests appropriate to risk
- It preserves performance constraints
- It updates docs/schemas/changelogs when contracts changed

---

## 11) Security and Integrity

- Treat all client input as untrusted.
- Add rate limits for economy and progression endpoints.
- Keep audit logs for inventory/currency/trade mutations.
- Flag suspicious behavior for review tooling.
- Never couple trust to client-only states.

---

## 12) Canonical Short Description

Mysts of Grimor is GameClaw’s low-poly MMORPG built on the custom MOGEngine, focused on readable action combat, persistent social progression, and scalable multiplayer systems in a mist-shrouded fantasy world.
```
