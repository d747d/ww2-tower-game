# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a WWII-themed tower defense game implemented as a single HTML file with embedded CSS and JavaScript. The game features:
- Multiple tower types (Machine Gun, Artillery, Anti-Air, Sniper) with different targeting capabilities
- Various enemy types (Infantry, Tank, Heavy Tank, Aircraft) following a predefined path
- Difficulty levels (Normal, Hard, Veteran) that modify enemy stats and resource availability
- Tower upgrade system with damage, range, and fire rate improvements
- Ammo system requiring towers to reload after depleting ammunition
- Wave-based gameplay with increasing difficulty and elite enemies

## Development Commands

This project uses no build system or package manager. To run the game:
- Open `index.html` directly in a web browser
- No compilation, bundling, or server setup required
- The game is fully self-contained in the single HTML file

## Architecture

### Game Structure
- **Game State**: Central `gameState` object tracks resources, lives, waves, towers, enemies, bullets
- **Game Loop**: Uses `requestAnimationFrame` for smooth 60fps gameplay with delta time calculations
- **Entity System**: Separate arrays for towers, enemies, and bullets with collision detection
- **Path System**: Enemies follow a predefined path with segment-based movement

### Key Systems
- **Tower Targeting**: Each tower type has specific target types (e.g., Anti-Air only targets aircraft)
- **Ammunition System**: Towers have limited ammo and must reload, affecting tactical gameplay
- **Upgrade System**: Towers can be upgraded for damage, range, and fire rate with escalating costs
- **Difficulty Scaling**: Three difficulty levels modify enemy health, speed, and resource multipliers
- **Elite Enemies**: Special enemies with enhanced stats appear in later waves

### Core Game Objects
- **Towers**: Positioned entities with range, damage, fire rate, and targeting restrictions
- **Enemies**: Path-following entities with health, speed, damage, and type-specific vulnerabilities
- **Bullets**: Projectiles with collision detection and special behaviors (artillery splash damage)

## File Structure
- `index.html`: Complete game implementation including HTML structure, CSS styling, and JavaScript logic
- `README.md`: Basic project description with screenshot

## Game Balance
The game is designed around resource management and strategic tower placement:
- Starting resources: 150
- Tower costs: MG (25), Artillery (50), AA (40), Sniper (60)
- Upgrade costs scale with upgrade level
- Enemies provide resources and score when destroyed
- 12 waves total with victory condition