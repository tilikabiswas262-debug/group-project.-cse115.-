# ESCAPING THE HAUNTED MANSION

A text-based adventure game developed in C for CSE115.

## 📖 Project Overview

**Escaping the Haunted Mansion** is a console-based adventure game where the player explores a six-room haunted mansion, collects items, solves two puzzles, survives ghost attacks, and tries to escape.

The player starts in the **Entrance Hall**. To escape, the player must collect the **Master Key** and return to the Entrance Hall.

The game uses C programming concepts such as structures, arrays, strings, functions, loops, conditional statements, `switch`, and basic pointer use in function parameters.

\---

## 🎮 Game Features

The final program includes:

* Six rooms
* North, South, East, and West movement
* Item collection and inventory
* Player health and score
* Two ghost encounters
* Med Kit and Medicine
* Two puzzles
* Silver Key and Master Key
* Locked Basement
* Locked Secret Chamber
* Game Over condition
* Winning condition
* Main menu and player name input

\---

## 🏚️ Rooms

The six rooms in the program are:

|Room|Item / Feature|
|-|-|
|**Entrance Hall**|Starting point and final escape point|
|**Living Room**|Flashlight|
|**Kitchen**|Med Kit and ghost|
|**Library**|First puzzle and Silver Key|
|**Basement**|Medicine and ghost|
|**Secret Chamber**|Second puzzle and Master Key|

### Room Connections

The actual room connections in the program are:

```text
Entrance Hall
      |
     EAST
      ↓
Living Room
      |
    SOUTH
      ↓
   Kitchen
      |
    NORTH
      ↓
   Library
      |
     WEST
      ↓
   Basement
      |
     EAST
      ↓
Secret Chamber
      |
    NORTH
      ↓
Entrance Hall
```

The program also defines the reverse directions where they exist. For example, the Living Room connects back **West** to the Entrance Hall, the Kitchen connects **North** to the Library, the Library connects **South** to the Kitchen, and so on.

\---

## 🎒 Items

The game contains five important items.

|Item|Purpose|
|-|-|
|**Flashlight**|Required to enter the Basement|
|**Med Kit**|Restores 35 health|
|**Medicine**|Restores 20 health|
|**Silver Key**|Required to enter the Secret Chamber|
|**Master Key**|Required to escape the mansion|

Items collected by the player are stored in the player's inventory.

Each collected item increases the player's score by **10 points**.

The two puzzle rewards also increase the score:

* Silver Key puzzle: **+20 points**
* Master Key puzzle: **+30 points**

\---

## 👻 Ghost Attacks

There are two rooms containing ghosts:

* **Kitchen**
* **Basement**

When the player enters a room containing a ghost, the ghost attacks once and reduces the player's health.

The Kitchen ghost has a base damage of **15**, while the Basement ghost has a base damage of **25**. The program adds a random value from 0 to 5 to the base damage.

After attacking, the ghost is marked as defeated and will not attack again during that game.

If the player's health reaches **0**, the game ends.

\---

## ❤️ Health and Healing

The player starts with:

```text
Health = 100
Score  = 0
```

The two healing items work as follows:

```text
Med Kit   → restores 35 health
Medicine  → restores 20 health
```

Health cannot exceed the maximum value of **100**.

When a healing item is used, it is removed from the inventory.

\---

## 🧩 Puzzles

The game contains exactly **two puzzles**.

### Library Puzzle

The player is asked:

```text
Which device has keys but no locks?

1. Keyboard
2. Book
3. Chair
```

The correct answer is:

```text
1. Keyboard
```

After solving the puzzle, a **Silver Key** appears in the Library and the player receives **20 points**.

The Silver Key is required to enter the Secret Chamber.

### Secret Chamber Puzzle

The player is asked:

```text
Complete: 1  3  5  7  ?

1. 8
2. 9
3. 10
```

The correct answer is:

```text
2. 9
```

After solving the puzzle, a **Master Key** appears in the Secret Chamber and the player receives **30 points**.

\---

## 🔐 Locked Areas

### Basement

The Basement cannot be entered until the player has collected the **Flashlight**.

If the player tries to enter without it, the program displays a message explaining that the Basement is too dark.

### Secret Chamber

The Secret Chamber cannot be entered until the player has collected the **Silver Key**.

The Silver Key is obtained by correctly solving the Library puzzle.

\---

## 🏆 Winning the Game

The winning sequence is:

```text
Start at Entrance Hall
        ↓
Go East to Living Room
        ↓
Collect Flashlight
        ↓
Go South to Kitchen
        ↓
Survive the Ghost
        ↓
Go North to Library
        ↓
Solve the Library Puzzle
        ↓
Get Silver Key
        ↓
Go West to Basement
        ↓
Collect Medicine / Survive Ghost
        ↓
Go East to Secret Chamber
        ↓
Solve the Final Puzzle
        ↓
Get Master Key
        ↓
Go North to Entrance Hall
        ↓
ESCAPE!
```

The player wins when they return to the Entrance Hall while carrying the **Master Key**.

The program then displays the player's final score and remaining health.

\---

## 💻 C Programming Concepts Used

The project uses concepts appropriate to the CSE115 course.

### Structures

Two structures are used:

```c
Room
Player
```

`Room` stores information about each room, including its name, description, item, exits, puzzle status, and ghost information.

`Player` stores the player's name, inventory, health, score, current room, and number of items.

### Arrays

Arrays are used for:

* The six rooms
* Room exits
* Player inventory
* Character strings

### Strings

Strings are used for:

* Player name
* Room names
* Room descriptions
* Item names
* Inventory items

The program uses functions such as `strcpy`, `strcmp`, `strlen`, and `strcspn` to work with strings.

### Functions

The program is divided into functions for different tasks, including:

```text
menu()
setRoom()
initializeRooms()
initializePlayer()
showRoom()
movePlayer()
takeItem()
showInventory()
useHealingItem()
solvePuzzle()
hasItem()
main()
```

### Loops

Loops are used for:

* The main game loop
* Menu input
* Initializing rooms
* Searching through the inventory
* Moving inventory items after a healing item is used

### Conditional Statements

`if`, `else if`, and `else` statements are used to:

* Check room exits
* Check whether required items are available
* Trigger ghost attacks
* Check puzzle answers
* Check health
* Check item types
* Check the winning condition

### Switch Statement

The main gameplay menu uses a `switch` statement to process the player's choices.

### Pointers and Function Parameters

The program uses pointers and function parameters to allow functions to work with the original `Room` and `Player` data.

For example:

```c
void initializePlayer(Player \\\*p)
```

and:

```c
void movePlayer(Room r\\\[], Player \\\*p, int direction)
```

This allows the functions to modify the actual game data used by `main()`.

\---

## 🕹️ How to Play

After starting the game, the player enters their name.

During gameplay, the following choices are available:

```text
1. Move North
2. Move South
3. Move East
4. Move West
5. Take Item
6. Show Inventory
7. Use Healing Item
8. Solve Puzzle
9. Exit Game
```

The player should explore the mansion, collect required items, solve the puzzles, manage health, and return to the Entrance Hall with the Master Key.

\---

## 🧪 Testing

The game includes handling for the main gameplay situations, including:

* Starting the game
* Exiting from the main menu
* Player name input
* Movement in all four directions
* Invalid movement
* Taking available items
* Attempting to take an item twice
* Full inventory
* Viewing inventory
* Using Medicine
* Using a Med Kit
* Attempting to heal at full health
* Ghost attacks
* Health reaching zero
* Entering the Basement without the Flashlight
* Entering the Secret Chamber without the Silver Key
* Solving the Library puzzle
* Solving the Secret Chamber puzzle
* Obtaining the Silver Key
* Obtaining the Master Key
* Returning to the Entrance Hall
* Winning the game
* Exiting during gameplay
* Invalid menu choices

\---

## 👥 Group Project

This project was completed as a **three-member CSE115 group project**.

|Member|Main Contribution|
|-|-|
|**Syed Mohammad Aqif Reza**|Program setup, constants, Room structure, Player structure, and initial game setup|
|**Humayra Mahjuba Zaman**|Gameplay and room interaction|
|**Tilika Biswas**|Puzzles, ghost attacks, items, and final game progression|

The project was divided into separate sections so each member could understand and present their part.

The code was divided among the group members for development and presentation.

The initial section of the project includes:

* Header files
* Constants
* Room structure
* Player structure
* Function prototypes
* Main menu
* Room initialization
* Player initialization
* Room display

The complete program combines these sections with movement, ghost attacks, items and inventory, healing, puzzles, keys, and the final game loop.

\---

## 📁 Project Files

```text
Escaping-The-Haunted-Mansion/
│
├── main.c
└── README.md
```

`main.c` contains the complete C program.

`README.md` explains the project, gameplay, rooms, items, puzzles, and programming concepts used.

\---

## 🎓 Course Information

**Course:** CSE115  
**Project:** Escaping the Haunted Mansion  
**Project Type:** Text-Based Adventure Game  
**Programming Language:** C

