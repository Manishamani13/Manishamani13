import java.util.Scanner; import java.util.Random; 
 
public class NumberGame {public static void main(String[] args)} 
        Scanner scanner = new Scanner(System.in); 
        Random random = new Random(); 
        int minRange = 1;         
        int maxRange = 100;         
        int maxAttempts = 5;         
        int score = 0;         
        boolean playAgain = true;         
        System.out.println("Welcome to the Number Guessing Game!"); 
             while (playAgain) {int secretNumber = random.nextInt(maxRange - minRange + 1) + minRange; 
        int attempts = 0;            
        boolean guessedCorrectly = false; 
         
        System.out.println("I have selected a number between " + minRange + " and " + maxRange + ". Can you guess it?"); 
         
        while (attempts < maxAttempts && !guessedCorrectly) 
        { 
            System.out.print("Attempt " + (attempts + 1) + "/" + maxAttempts + ": Enter your guess: ");                 
            int guess = scanner.nextInt();                 
            attempts++; 
             
            if (guess < secretNumber) 
            { 
                System.out.println("Too low! Try again."); 
            } else if (guess > secretNumber) { 
                System.out.println("Too high! Try again."); 
            } else { guessedCorrectly = true; 
                System.out.println("Congratulations! You guessed the number " + secretNumber + " correctly in " + attempts + " attempts!"); 
                score++; 
            } 
        } 
         
        if (!guessedCorrectly) { 
            System.out.println("Sorry, you've run out of attempts. The correct number was: " + secretNumber); 
        } 
         
        System.out.print("Do you want to play again? (yes/no): ");             
        String playAgainInput = scanner.next().toLowerCase();             
        playAgain = playAgainInput.equals("yes"); 
    } 
     
    System.out.println("Game over! Your final score is: " + score);         
    scanner.close(); 
} 

                   
       
