# group-project.-cse115.-
Text-Based Adventure Game: Create an interactive text-based adventure game where players navigate through a story by making choices and solving puzzles

/* Function Prototypes */
void initializeRoom(Room *room);
void initializePlayer(Player *player);
void showRoom(Room *room);
void takeItem(Room *room, Player *player);
void showInventory(Player *player);
int hasItem(Player *player, char itemName[]);
void solvePuzzle(Room *room, Player *player);
