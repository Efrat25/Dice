import java.util.Scanner;

public class DiceGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String playAgainResponse;

        do {
            System.out.println("Welcome to the Dice Game!");

            // Roll the dice for player
            int playerRoll = rollDice();
            System.out.println("You rolled: " + playerRoll);

            // Roll the dice for computer
            int computerRoll = rollDice();
            System.out.println("Computer rolled: " + computerRoll);

            // Determine the winner
            if (playerRoll > computerRoll) {
                System.out.println("You win!");
            } else if (computerRoll > playerRoll) {
                System.out.println("Computer wins!");
            } else {
                System.out.println("It's a tie!");
            }

            System.out.print("Do you want to play again? (yes/no): ");
            playAgainResponse = scanner.nextLine().toLowerCase();
        } while (playAgainResponse.equals("yes"));

        System.out.println("Thank you for playing!");
        scanner.close();
    }

    // Method to simulate rolling a six-sided die
    public static int rollDice() {
        return (int) (Math.random() * 6) + 1;
    }
}
