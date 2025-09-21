import java.util.Random;
import java.util.Scanner;

public class NumberGame {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Random random = new Random();
        int score = 0;
        String playAgain;

        do {
            int number = random.nextInt(100) + 1; // Random number 1–100
            int attempts = 0;
            int guess = 0;
            int maxAttempts = 7; // Limit attempts

            System.out.println("Guess the Number (1 to 100):");

            while (attempts < maxAttempts && guess != number) {
                System.out.print("Enter your guess: ");
                guess = sc.nextInt();
                attempts++;

                if (guess == number) {
                    System.out.println("Correct! You guessed it in " + attempts + " tries.");
                    score++;
                } else if (guess > number) {
                    System.out.println("Too high! Try again.");
                } else {
                    System.out.println("Too low! Try again.");
                }
            }

            if (guess != number) {
                System.out.println("Out of attempts! The number was: " + number);
            }

            System.out.print("Do you want to play again? (yes/no): ");
            playAgain = sc.next();

        } while (playAgain.equalsIgnoreCase("yes"));

        System.out.println("Final Score: " + score);
        sc.close();
    }
}
