import java.util.Random;
import java.util.Scanner;

public class Main1 {

    static int[][] player = new int[4][3];
    
    public static void main(String[] args) {
        //String array of all the rooms in the house
        String[][] houseRooms = new String[3][3];
        houseRooms[0][0] = "Computer Room";
        houseRooms[0][1] = "Living Room";
        houseRooms[0][2] = "Deck";
        houseRooms[1][0] = "Hallway";
        houseRooms[1][1] = "Bathroom";
        houseRooms[1][2] = "Living Room 2";
        houseRooms[2][0] = "Dining Room";
        houseRooms[2][1] = "Kitchen";
        houseRooms[2][2] = "Laundary Room";
             
        room(houseRooms);
        movement(houseRooms);
        mvement(houseRooms);
    }

    public static void room(String[][] args) {
        // Randomizer to where the player and the dog will apear
        Random room = new Random();
        int startingLocationX = room.nextInt(3);
        int startingLocationY = room.nextInt(3);
        int finishLocationX = room.nextInt(3);
        int finishLocationY = room.nextInt(3);
        player[startingLocationX][startingLocationY] = 2;
        player[finishLocationX][finishLocationY] = 3;
        // Tells player where they are as well as where the dog is. 
            System.out.println("You have started in: " + args[startingLocationX][startingLocationY]);
        System.out.println("The Dog has appeared in: " + args[finishLocationX][finishLocationY]);
        
        if (startingLocationX == finishLocationX && startingLocationY == finishLocationY) {
            System.out.println("You have started in the same position as the Dog!");
            System.exit(0);
        }
        
    }
        // Gives the winning and losing conditions 
    public static void movement(String[][] args){
        //tells what directions the player can move as well as the starting location
        //of the player and the dog 
        int directionNum[]={0,1,2,3};
        String directionCump[]={"North","South","East","West"};
        position =[startingLocationX][startingLocationY];
        dogLocation=[finishLocationX][finishLocationY];
        int inv=0;
        int x=0; 

        do{
            if( position != dogLocation)
                position=move(position,dogLocation,houseRooms,directionCump)
                inv=0;
                x++;}
            else {
                    inv=1
                }
           
            while(inventory == 0 || x == 10);
		
		
		if(inventory == 1 && x != 10)
		{
			System.out.println("You found the dog now take him outside");		
		}
		else if (inventory == 1 && x == 10)
		{
			System.out.println("You found the dog now take him outside");
		}
		else
		{
			System.out.println("You didn't find the dog in time but you can smell what is waiting for you.");
					
		}
       }
// Where the player will chose their movement as well as telling the player where they are in the room.
   public static int mvement(int position, int dogLocation,int Movement[][],String houseRooms[][], String directionCump[], int directionNum[])
   {
	   // Declare Scanner.
	   Scanner num1;
	      num1 = new Scanner(System.in);
	   int movementChoice;
	   int posnum;
	 
	   // Print out options.
		   System.out.println("You are in the " + position + ", where would you like to go?");
	   		if(Movement[position][0] != 0)
	   			System.out.println("Type 0 to go " + directionCump[0]);
	   				if(Movement[position][1] != 0)
	   					System.out.println("Type 1 to go " + directionCump[1]);
	   					if(Movement[position][2] != 0)
	   						System.out.println("Type 2 to go " + directionCump[2]);
	   							if(Movement[position][3] != 0)
	   								System.out.println("Type 3 to go " + directionCump[3]);
       // Get the movement choice.
	   movementChoice = num1.nextInt();
	   // If possible choice is selected then the player will move.
	   if(Movement[position][movementChoice] != 0 && movementChoice < 4 && movementChoice > -1)
	   {
		   posnum = Movement[position][movementChoice];
		   return posnum;
	   }
	   // if movment is not possible says there is no room there.
	   else
	   {
		   System.out.println("There is no room there");
	       posnum = position;
	       return posnum;
	   }
   }
}
