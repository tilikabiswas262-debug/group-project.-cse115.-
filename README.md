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
   
      
      //MAIN FUNCTION

int main(){

      Room rooms[NUM_ROOMS];

      Player player;

      int choice;

      int running =1;

      scrand(time(NULL));

      initializeROOMS(rooms);
      initializeplayer(&player);

      printf("===============================\n\n");
       printf("ESCAPE THE HAUNTED MANSION\n");
      printf("===============================\n\n");

       printf("ENTER YOUR NAME:");


       fgets(player.name, sizeof(player.name), stdin);

      player.name[strcspn(player.name, "\n")] = '\0';

}







while(running)
    {
        showRoom(rooms, &player);

        printf("\n");
        printf("1. Move North\n");
        printf("2. Move South\n");
        printf("3. Move East\n");
        printf("4. Move West\n");
        printf("5. Take Item\n");
        printf("6. Show Inventory\n");
        printf("7. Solve Puzzle\n");
        printf("8. Exit Game\n");

        printf("\nEnter choice: ");
        scanf("%d", &choice);

        while(getchar() != '\n');

        switch(choice)
        {
            case 1:
                movePlayer(rooms, &player, NORTH);
                break;

            case 2:
                movePlayer(rooms, &player, SOUTH);
                break;

            case 3:
                movePlayer(rooms, &player, EAST);
                break;

            case 4:
                movePlayer(rooms, &player, WEST);
                break;

            case 5:
                takeItem(rooms, &player);
                break;

            case 6:
                showInventory(&player);
                break;

            case 7:
                solvePuzzle(rooms, &player);
                break;
            case 8:
                printf("\nGame Over.\n");
                running = 0;
                break;

            default:
                printf("\nInvalid choice.\n");
        }
        
        
    }

   

   //WIN CONDITION


     if(player.currentRoom == 0 && hasItem(&player, "Master Key"))
        {
            printf("\n=====================================\n");
            printf(" YOU ESCAPED THE HAUNTED MANSION!\n");
            printf("=====================================\n");

            running = 0;
        }


