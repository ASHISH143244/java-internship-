# java-internship- task1 
NumberGuessingGame

code :
import java.util.Scanner;
public class NumberGuessingGame {
    public static void main(String[] args) {
        int attempt = 1;
        int noOfGuess = 0, score = 0;
        int originalno = (int)(Math.random()*99+1);
        System.out.println("\t+--------------------------+");
        System.out.println("\t| Welcome to Number Guessing Game|");
        System.out.println("\t+--------------------------+\n");

        System.out.println("Guess a Number Between 1 to 100\n");
        Scanner input = new Scanner(System.in);
        while(true)
        {
            if(input.hasNextInt())
            {
                noOfGuess = input.nextInt();
                if(noOfGuess == originalno)
                {
                    score = score+10;
                    System.out.println("Congrulations!! you won the Game");
                    System.out.println("Your Score is " + score + "and you guessed it in " + attempt + " attempts");
                    break;

                }
                else if(noOfGuess < originalno)
                {
                    System.out.println("Your Guess is too small!");
                    System.out.println("Attempts remaining = " + (10-attempt));
                    score--;

                }
                else if(noOfGuess > originalno)
                {
                    System.out.println("Your Guess is too high!");
                    System.out.println("Attempts remaining = " + (10-attempt));
                    score--;

                }
                if(attempt==10)
                {
                    System.out.println("You have exceeded the maximum number of attempts");
                    System.out.println("Better Luck Next Time!");
                    break;
                }
                attempt++;

            }
            else 
            {
                System.out.println("Enter the Valid Number!");
            }
        
        }


        
    }

    
}
