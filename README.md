# Amiblitz 3 Platformer

A multi-level platformer game written in **Amiblitz 3** (Blitz Basic 2) for the Amiga. Levels are designed in Tiled and converted to Amiblitz 3 data using **Tiled2Retro**. The initial game loop was bootstrapped via the exporter for a quick start, but all gameplay code has since been rewritten by hand.

## Features

- 3 playable levels
- 16×16 pixel tiles on a 20×16 grid (320×256 screen)
- 3-bitplane graphics (8 colors)
- Tile-based collision (floors, walls, ladders)
- Player physics: gravity, jumping, ladder climbing
- Joystick input (port 1)
- Double-buffered rendering

## Requirements

- Amiga with 68000+ processor (or an emulator like **WinUAE** / **FS-UAE**)
- **Amiblitz 3** compiler (Blitz Basic 2 compatible)
- Kickstart 2.0+

## How to Run

1. Open **Amiblitz 3** on your Amiga or emulator.
2. Load `game.ab3` as the main source file.
3. Ensure the `includes/` folder is in the same directory.
4. Compile and run via **Run → Compile & Run** (or press **F5**).

The game will start immediately. Use a joystick in port 1 to move, and press **Q** to quit.

## Level Selection

Open `game.ab3` and change the constant near the top:

```blitzbasic
#CURRENT_LEVEL = 0   ; change to 0, 1, or 2
```

Then recompile.

## Project Structure

```
├── game.ab3              Main game source (game loop, init)
├── assets/
│   └── tiles_3bp.iff     Tileset image (3 bitplanes)
├── includes/
│   ├── map.ab3           Tile map loader & renderer
│   ├── mapdata.ab3       Level data (tile indices + flags)
│   ├── player.ab3        Player newtype & physics
└── README.md
```

## Controls

| Input        | Action          |
| ------------ | --------------- |
| Joystick Left/Right | Move       |
| Joystick Up        | Climb ladder |
| Joystick Fire      | Jump         |
| Q                  | Quit game    |

## License

Open source — do whatever you like with it.