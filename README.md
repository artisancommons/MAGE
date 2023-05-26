
# delusinate
## Junk-RPG
- Crafting with junk found in the world or salvaged from mobs
- skills, learn/gain by doing
- inventory ui
  - simple grid style
  - unlimited object capacity
- combination crafting systems
- play your own way
  - many ways to do/achieve things
  - no one-playstyle fits all
- sound effects
  - entity jump, walk, action, etc..
  - 3D sound
- particle/hit effects
  - blood, ricochet
- Player Building
  - players can build in the wilderness or on plot
  - land is purchasable in the town of ownership
- Settlements
  - NPC Villages/Towns/etc..
  - Political positions
    - player can become mayor, etc..
  - entire cities/towns/settlements can be destroyed
  - seiges/attacks will happen periodically to settlements
  - the player can defend or join the attack
    - defending gains rep with the settlement
    - attacking reduces rep with the settlement
- Procedural Generation
  - Terrain
  - Dungeons/Levels
- Smart AI
  - NPCs and Mobs will interact with the world in unique ways
  - often predictable ways, the player can feel empowered this way
- Items
  - pickups
  - tools
  - weapons
- Player Health
  - player can heal with items
  - player respawns at the nearest medical center
- Map Menu
- Mini-Map
- 


# M.A.G.E.
## Modular Accessible Game Engine


# First Class Linux/Ubuntu & RPi4 Support
- Developed using Linux, for Linux users.
- (currently only Linux support. may not function as intended when using Windows/WSL or MacOS)
- Low-cost systems allow distribution on RPi3/4, possibly other similar devices as well

## Write 2D/3D Games and Simulations with Native C++ and/or Lua
- Powered by Raylib
  - raylib has no external dependencies, this project only depends on raylib.
  - minimal total wrapping over raylib methods

- Lightweight, Fast, and Safe
  - Written in 'Golden C++' (primarily idiomatic C, minimal usage of Standard Library & Template Library)
  - Carefully designed to minimize bloat
  - Much of the low-level code would be considered Pure C
  - Almost every door to the heap is managed through MemoryArena's (via ArenaManager's)

- Modular Design
  - Modular design is good for contributors :)
  - The Codebase is split into modules and sub-modules
  - Modules can be referenced by a project, via a config.json
  - Sub-modules are for organization (you can not select individual sub-modules to use)

- User-Created-Plugin support
  - the developers of this, as well as any public user, can create plugins
  - Plugins are hosted publicly
  - Plugins follow a simple format and are enabled/disabled via a project's config.json

- Lua Wrappers for module methods (expose functionality to Lua env)


### Native Editor App
- packaged as a distributable, hosted on something like itch.io
- Downloads the editor app (with engine code)
- Builds the engine components natively
- Lets you edit scene files
- you can save/load scenes
- scenes can be test ran
- an app can be generated based scenes list
- visual-scripting plugin
  - full scripting support
- app templates



#### Common (not a module, always included)
- Types 'Primitive'
- Types 'Advanced'
- Helper Define's
- Debug Util
- Misc Util


#### Assets (module)
- Utilities for loading meshes, models, textures, audio, prefabs, etc..
- Data types for managing assets
- Blender Support

#### Audio (module)
- Sound Mixing
- Clips  (one-off's)
- Tracks (songs, long-form)
- Effects

#### ECS (module)
- IEntity
  - interface for ECS

- SceneManager
  - loads Scene's
  - manages scene init and clean up
  - calls Scene's script file(s) (start, exit, etc..)

- Scene
  - references script files
  - dependent on a MemoryArena
  - can instantiate (T)object's
    - objects are copied into a MemoryArena
  - Has storage containers for Entity, Component, and Resource 

#### Events (module)
- Good ol fashioned Event System

#### GUI (module)
- UI Widget toolkit

#### Input (module)
- Helpers and Data-types for handling Keyboard/Mouse, Gamepads, and Touch Devices

#### Memory (module)
- MemoryArena
  - a wrapper for an allocated block of x bytes

- ArenaManager
  - a management class for MemoryArena's

- ArenaVar
  - a wrapper for (T*)data, located inside a MemoryArena

#### Network (module)
- Global Stat CRUD
  - leaderboards, etc..

- Rooms
  - clients join rooms
  - rooms allow communication to all room members

- Worlds
  - worlds are actual running instances of a scene/timeline

- Users can host rooms and worlds

- Synchronized Variables
  - owned by the server
  - data changes will be propagated to clients
  - can only be set by auth
  - clients can request to set the data

#### Physics (module)
- Global Forces (wind, objects, etc..)

- Box Sweep, Raycast

- Sphere Collision

- 2D/3D Particle physics

- Default System
  - filters through a Scene's entities for ones with physical characteristics
  - solves collision and physics forces
  - attempts to call callback for collided entities

#### Rendering (module)
- Screen Effects

- Procedural Meshes

- Particle Rendering systems

- Mesh Rendering

- Shader & Material Tables

- Model Rendering (.obj, ..?)

- Imposter rendering
  - renders a single object from multiple angles and projects it onto several quads
  - one shared object for many instances
  - a piece of geometry can be loaded a single time and be reused

- Animation Systems

- Default System
  - filters through a Scene's entities for renderable ones
  - calls the most appropriate/suited draw method 

#### Scripting (module)
- Lua helpers
  - Util for Lua Bindings

- Script Loading/Execution

- Scripting API
  - should mirror native scripting as much as possible

- Util types

#### Threading (module)
- Task management for parallel system execution
  - split homogenous system functions into batch calls

#### Window (module)
- Helpers for window open/close

- Utilities for screen related calculations






### Plugins
- editor app
  - scene editor

- game-maker tools
  - asset tools for creating mini-games

