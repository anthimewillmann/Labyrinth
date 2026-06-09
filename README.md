# Labyrinth

**A Java Swing maze game with keyboard controls, difficulty modes, and Dijkstra-based pursuers.**

Labyrinth is a small desktop game built as a Java/OOP project. The player moves through a fixed 15x15 maze, tries to reach the goal, and avoids pursuers that move randomly or chase the player using pathfinding depending on the selected difficulty.

## Screenshots

<p align="center">
  <img src="Screenshots/Bildschirmfoto 2026-06-09 um 11.26.10.jpeg" width="45%"/>
  <img src="Screenshots/Bildschirmfoto 2026-06-09 um 11.27.01.jpeg" width="45%"/>
</p>

<p align="center">
  <img src="Screenshots/Bildschirmfoto 2026-06-09 um 11.27.42.jpeg" width="45%"/>
  <img src="Screenshots/Bildschirmfoto 2026-06-09 um 11.29.15.jpeg" width="45%"/>
</p>

## Features

- Java Swing desktop UI
- 15x15 grid-based maze
- Keyboard-controlled player movement
- Three difficulty modes
- Random and Dijkstra-based pursuer movement
- Win and loss screens
- Restart with `ENTER`
- Exit with `ESC`
- Graphical view with image assets
- Console view for ASCII-style debugging/output

## Gameplay

1. Start the game.
2. Select a difficulty:
   - `1` Easy
   - `2` Medium
   - `3` Difficult
3. Move with the arrow keys.
4. Reach the goal to win.
5. Avoid the pursuers.
6. Press `ENTER` to restart or `ESC` to quit.

## Controls

| Key | Action |
|---|---|
| `1` | Easy mode |
| `2` | Medium mode |
| `3` | Difficult mode |
| Arrow keys | Move player |
| `ENTER` | Restart game |
| `ESC` | Exit game |

## Difficulty Modes

| Mode | Pursuers | Behavior |
|---|---:|---|
| Easy | 2 | Random movement |
| Medium | 3 | Alternates between random movement and pathfinding |
| Difficult | 4 | Dijkstra-based pathfinding |

## Architecture

The project follows a simple controller/model/view structure.

```text
Keyboard Input
      |
      v
controller.Controller
      |
      v
model.World
      |
      +--> model.Direction
      |
      +--> view.GraphicView
      |
      +--> view.ConsoleView
```

### Packages

```text
controller/
  Labyrinth.java      Application entry point
  Controller.java     Keyboard input and window control

model/
  World.java          Game state, maze, rules, pursuers
  Direction.java      Movement directions and Dijkstra pathfinding

view/
  View.java           View interface
  GraphicView.java    Swing rendering
  ConsoleView.java    Console rendering
```

## Tech Stack

| Area | Technology |
|---|---|
| Language | Java |
| GUI | Java Swing |
| Rendering/Input | Java AWT |
| Images | ImageIO, BufferedImage |
| Pathfinding | Dijkstra algorithm |
| IDE Project | IntelliJ IDEA project files |
| Build | IntelliJ or manual `javac` |

No Maven, Gradle, Docker, database, backend service, or CI/CD pipeline is currently included.

## Requirements

- Java JDK
- IntelliJ IDEA or another Java IDE

The project documentation mentions Oracle OpenJDK 22.0.1, while the IDE metadata references `openjdk-26`. The exact required JDK version should be clarified.

## Running in IntelliJ IDEA

1. Open the project in IntelliJ IDEA.
2. Make sure `src` is marked as the source folder.
3. Configure a compatible JDK.
4. Run:

```text
controller.Labyrinth
```

## Running from the Command Line

Compile:

```bash
javac -d /tmp/labyrinth-classes $(find src -name '*.java')
```

Copy image assets into the classpath root:

```bash
cp src/*.jpeg /tmp/labyrinth-classes/
```

Run:

```bash
java -cp /tmp/labyrinth-classes controller.Labyrinth
```

## Project Status

The Java source code compiles successfully with `javac`.

Current repository limitations:

- No automated tests
- No Maven or Gradle build
- No CI/CD pipeline
- No packaging or release workflow
- Maze layout is hard-coded
- Asset paths differ from the existing documentation
- Documentation mentions `Main.java`, but the actual entry point is `controller.Labyrinth`
- Potential bounds issue when moving the player outside the grid
- Difficulty is modeled with multiple booleans instead of a single enum

## Known Limitations

- No save games
- No score system
- No level editor
- No external level files
- No configurable grid size
- No test coverage
- No standardized build command
- No deployment artifact such as a `.jar`

## Roadmap Ideas

- Add a `README.md` with screenshots
- Add Maven or Gradle
- Package the game as a runnable `.jar`
- Add JUnit tests for `World` and `Direction`
- Load maze layouts from files
- Replace difficulty booleans with an enum
- Add bounds checks before grid access
- Add multiple levels
- Add score or timer
- Add sound effects
- Add CI for compile/test checks

## License

No license information is currently documented.
