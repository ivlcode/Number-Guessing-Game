# Number-Guessing-Game
Number Guessing Game in Java, This game asks the user to guess a randomly generated number within a limited number of attempts and it Stops for max attempts or correct guess.


//Number GuessingGame
//Author: Yarin Frhat
/*This game asks the user to guess a random number within a limited number of attempts*/

import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        //initialize Scanner and Random objects
        Random rand = new Random();
        Scanner scanner = new Scanner(System.in);

        //declaration of variables
        int guess;
        Random random = new Random();
        int attempts = 0;
        int maxAttempts = 5;

        //generate a random number between 1 and 50
        int min = 1;
        int max = 50;
        int randomNumber = random.nextInt(min, max + 1);


        System.out.println("Welcome to the Number Guessing Game"); //print welcome message to the user
        System.out.println("Guess the number between 1-50: "); //ask the user to enter a guess


        //Main loop: repeats until the user guesses the correct answer
        do {
            System.out.println("Enter a guess: ");
            guess = scanner.nextInt();
            attempts++; //increment the attempt counter

            //check the user's guess
            if (guess < randomNumber) {
                System.out.println("too low!");
            }
            else if (guess > randomNumber) {
                System.out.println("too high!");
            }
            else {
                System.out.println("CONGRATULATIONS! The number was" + randomNumber); //print a CONGRATULATIONS message if the user's guesses the correct number
                System.out.println("# of attempts:" + attempts); //gives the user's number of attempts
            }
            if (maxAttempts > attempts) {
                System.out.println("Attempts left: " + (maxAttempts - attempts));  //informing user of remaining attempts if the game is not finished

            }
            if(guess > max){
                System.out.println("the number is higher than 50" + "\uD83E\uDEE2"); //stop the game if the guess is bigger than the max allowed.
            }
        }while (guess != randomNumber && attempts < maxAttempts) ; //End the game loop

        if(guess != randomNumber){
            System.out.println("GAME OVER!\nThe correct answer was: " + randomNumber + " \uD83E\uDD2A");
        }

        scanner.close(); //closing the scanner for free resource :)
    }
}

