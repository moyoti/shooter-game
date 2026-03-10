# AGENTS.md - Agentic Coding Guidelines

## Project Overview
This is a vanilla HTML/CSS/JavaScript space shooter game using Phaser.js. Single-file architecture (index.html) with embedded styles and scripts.

## Build/Test Commands

Since this is a static HTML file with no build system:

```bash
# Serve the game locally (no build required)
python3 -m http.server 8080
# or
npx serve .

# Open in browser
open index.html
```

No lint, test, or typecheck commands exist - this is a simple browser game.

## Code Style Guidelines

### Language & Comments
- Use Chinese (zh-CN) for all user-facing text and comments
- Use emojis liberally in UI labels (e.g., `❤️ 生命值`, `🎯 得分`)
- English for variable names, constants, and code logic

### Naming Conventions
- **Constants**: UPPER_SNAKE_CASE (e.g., `CONFIG`, `DIFFICULTIES`, `ENEMY_TYPES`)
- **Classes**: PascalCase (e.g., `MainScene`)
- **Variables/Functions**: camelCase (e.g., `gameState`, `playerState`, `handleMovement`)
- **Private methods**: Leading underscore is NOT used (Phaser convention)
- **Boolean states**: Use `is`/`has` prefix (e.g., `isPaused`, `isShopOpen`)

### Code Structure
- Single-file architecture: HTML structure → CSS styles → JavaScript
- Organize code into logical sections with comment headers:
  ```javascript
  // ==================== Game Configuration ====================
  // ==================== Game State ====================
  // ==================== Weapon Definitions ====================
  ```

### JavaScript Patterns
- Use `const` for constants and immutable references
- Use `let` for mutable variables
- Avoid `var` entirely
- Use arrow functions for callbacks and simple functions
- Use traditional functions for class methods
- Destructure objects when accessing multiple properties

### CSS Patterns
- Use CSS custom properties sparingly (inline colors preferred)
- Chinese comments for CSS sections
- Flexbox for layouts
- Use `transform` for animations

### Game Architecture
- Phaser.js Scene-based structure
- State objects for game and player data
- Physics groups for game entities (bullets, enemies, drops)
- Collision detection via `physics.add.overlap()`

### Error Handling
- Minimal try-catch (game logic rarely throws)
- Defensive checks for object existence before operations
- Graceful degradation for missing DOM elements

## Project Structure
```
index.html          # Complete game in single file (HTML + CSS + JS)
```

## Dependencies
- Phaser 3.60.0 (loaded via CDN: `https://cdn.jsdelivr.net/npm/phaser@3.60.0/dist/phaser.min.js`)
- No package.json, no npm dependencies
- No build tools or bundlers

## Important Notes
- Game runs entirely client-side
- No backend or API calls
- LocalStorage used for leaderboard persistence
- Canvas-based rendering via Phaser
- Responsive design with fixed aspect ratio (1280x720)
