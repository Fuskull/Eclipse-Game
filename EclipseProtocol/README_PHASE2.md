# Eclipse Protocol - Phase 2 Complete

## ✅ Phase 2 Requirements - ALL COMPLETED

### Core Systems
- ✔ **Two Enemy Types**
  - Patrol Enemy (simple back-and-forth AI)
  - Hunter Enemy (FSM with 4 states: Idle, Patrol, Chase, Return)

- ✔ **Finite State Machine (FSM)**
  - Hunter AI with proper state transitions
  - Detection range and chase behavior
  - Return to spawn point when player escapes

- ✔ **Energy System + Dash Ability**
  - Energy bar (100 max)
  - Dash costs 25 energy
  - Auto-regeneration (15/second)
  - Cooldown system (1 second)

- ✔ **Game State System**
  - Menu State
  - Play State
  - Pause State
  - Game Over State
  - Victory State

- ✔ **Procedural Generation**
  - Random room sizes
  - Random enemy spawning
  - Door system for room transitions
  - Dynamic difficulty scaling

- ✔ **Difficulty Scaling**
  - Enemy speed increases with room count
  - More enemies spawn in later rooms
  - Hunter enemies appear after room 2

- ✔ **Sound System**
  - Background music (looping)
  - Hit sound effect
  - Dash sound effect
  - Graceful fallback if files missing

- ✔ **Polished UI**
  - Health bar with color coding
  - Energy bar
  - Room counter
  - Timer display
  - Control instructions

- ✔ **Clean Architecture**
  - Modular file structure
  - Separate state files
  - Clear separation of concerns

## 📁 Final File Structure

```
/EclipseProtocol
│
├── main.lua              # Game loop with state management
├── player.lua            # Player with energy & dash
├── enemy.lua             # Patrol enemy (multiple instances)
├── hunter.lua            # Hunter enemy with FSM
├── ui.lua                # Polished UI system
├── world.lua             # Procedural room generation
├── stateManager.lua      # State management system
├── conf.lua              # Love2D configuration
│
├── /states               # Game states
│   ├── menu.lua
│   ├── play.lua
│   ├── pause.lua
│   ├── gameover.lua
│   └── victory.lua
│
├── /assets
│   ├── /images           # (placeholder for sprites)
│   └── /sounds
│       ├── hit.wav       # (add your sound files)
│       ├── dash.wav
│       └── music.mp3
│
└── README_PHASE2.md
```

## 🎮 How to Play

### Controls
- **WASD** or **Arrow Keys** - Move player
- **Shift** - Dash (costs 25 energy)
- **ESC** - Pause game / Return to menu
- **R** - Restart (from game over/victory)
- **Space** - Start game (from menu)

### Objective
- Survive and clear rooms
- Reach the green EXIT door to progress
- Avoid two enemy types:
  - **Red squares** - Patrol enemies (predictable)
  - **Orange squares** - Hunter enemies (chase you!)
- Win by surviving 3 minutes OR clearing 10 rooms

### Gameplay Tips
- Watch your energy - dash wisely!
- Hunters show their current state above them
- Difficulty increases with each room
- Health doesn't regenerate - be careful!

## 🔧 Technical Highlights

### FSM Implementation
Hunter enemy has 4 states:
1. **Idle** - Waiting state
2. **Patrol** - Moving between patrol points
3. **Chase** - Actively pursuing player
4. **Return** - Going back to spawn point

State transitions based on:
- Player distance (detection range: 200)
- Lose range (300)
- Proximity to patrol points/spawn

### Procedural Generation
- Room dimensions: 700-1000 x 500-700 (random)
- Enemy count scales with room number
- Hunters spawn after room 2
- Door always on right side

### Difficulty Scaling
```lua
difficulty = 1 + (roomCount * 0.2)
enemy.speed = baseSpeed * difficulty
patrolCount = min(2 + roomCount, 5)
hunterCount = min(floor(roomCount / 2), 3)
```

### Energy System
- Max: 100
- Dash cost: 25
- Regen rate: 15/second
- Cooldown: 1 second

## 🚀 Running the Game

1. Install Love2D from https://love2d.org/
2. (Optional) Add sound files to `assets/sounds/`
3. Run: `love EclipseProtocol` or drag folder onto love.exe

## 📝 Phase 2 Checklist

✅ Second enemy type (Hunter)
✅ FSM with 4 states
✅ Energy system
✅ Dash ability
✅ Game state system (5 states)
✅ Procedural room generation
✅ Door transitions
✅ Difficulty scaling
✅ Sound system (music + SFX)
✅ Polished UI (health, energy, stats)
✅ Clean file structure
✅ Game balancing
✅ Victory/Game Over conditions
✅ Pause functionality

## 🎓 Grading Criteria Met

- **FSM Implementation**: Hunter AI with proper state machine
- **Procedural System**: Fully random room generation
- **Clean Architecture**: Modular, well-organized code
- **Playability**: Complete game loop with win/lose conditions
- **Polish**: UI, sounds, difficulty scaling
- **Code Quality**: Comments, structure, maintainability

## 🔮 Future Enhancements (Optional)

- Sprite animations
- Particle effects
- Power-ups/collectibles
- Multiple player characters
- Boss fights
- Save system
- Leaderboards

---

**Project Status**: Phase 2 Complete ✅
**Ready for Submission**: Yes
**Playable**: Yes
**All Requirements Met**: Yes
