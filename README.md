# RandomNumberGuesser

import java.util.Scanner;

/*
 * Class: CMSC203 
 * Instructor:Thai
 * Description: The program randomly generates a number and then the user has 7 chances to guess the number
 * Due: 10/08/2022
 * Platform/compiler: eclipse
 * I pledge that I have completed the programming 
 * assignment independently. I have not copied the code 
 * from a student or any source. I have not given my code 
 * to any student.
   Print your Name here: Naomi Samson
*/


public class RandomNumberGuesser {

	public static void main(String[] args) {
		System.out.println("This application generates a random integer between 0 and 100 and asks the user to guess repeatedly until they guess correctly.");
		int randInt=RNG.rand();
		System.out.println("Enter your first guess: ");
		Scanner keyboard = new Scanner(System.in);
		int guess = keyboard.nextInt();
		for(int counter=0; counter<=7; counter++) {
		if (guess==randInt) {
			System.out.println("Congratulations, you guessed correctly");
			System.out.println("Try Again? (yes or no)");
			Scanner keyboard1 = new Scanner(System.in);
			String choice = keyboard1.nextLine();
			RNG.resetCount();
			System.out.println("Enter your next guess: ");
			Scanner keyboard2 = new Scanner(System.in);
			guess = keyboard2.nextInt();
			
		}
		
		else if(guess>randInt) {
			System.out.println("Your guess is too high");
			RNG.inputValidation(guess,0, guess);
			counter = RNG.getCount();
			System.out.println("Number of gusses is: "+counter);
			System.out.println("Enter your next guess: ");
			Scanner keyboard1 = new Scanner(System.in);
			guess = keyboard1.nextInt();
		}
		
		else if(guess<randInt) {
			System.out.println("Your guess is too low");
			RNG.inputValidation(guess,guess, 100);
			counter = RNG.getCount();
			System.out.println("Number of gusses is: "+counter);
			System.out.println("Enter your next guess: ");
			Scanner keyboard1 = new Scanner(System.in);
			 guess = keyboard1.nextInt();
			
		}
		
	}
		System.out.println("You Failed!");
	}
}
