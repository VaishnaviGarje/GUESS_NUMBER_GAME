# GUESS_NUMBER_GAME
package codsoft;

import java.util.Scanner;

public class Task1 {
	public void numberguess() {

		int totalattempt = 3;
		int attempt = 1;
		int compno = (int) (Math.random() * 100);//generate random number between 1 to 100
		
		
		
		System.out.println("random number generated bettween 1 to 100=" + compno + "\n\n");
		System.out.println(".............plese enter your first name................." + "\n");
		@SuppressWarnings("resource")
		Scanner s = new Scanner(System.in);
		String name = s.next();// here i take name of user who plays game 
		while (attempt < 4) {

			System.out.println("........enter a number between 1 to 100.........");
			@SuppressWarnings("resource")
			Scanner sc = new Scanner(System.in);
			int userno = sc.nextInt();//here i take number from  user who plays game 

			if (userno == compno) {
				System.out.println(
						"Congradulations...!" + name + " you guesses a number in " + attempt + " attempts" + "\n");
				break;
			} else if (userno > compno) {
				System.out.println(name + " you entered greater number = " + userno + "\n");
				totalattempt = totalattempt - 1;
				attempt = attempt + 1;
				System.out.println("Remaining attempt are : " + totalattempt + "\n");
				if (totalattempt == 0) {
					System.out.println("attempts finish..The right number is = " + compno + "\n");
				}
			} else if (userno < compno) {
				System.out.println(name + " you entered less number = " + userno + "\n");
				attempt = attempt + 1;
				totalattempt = totalattempt - 1;
				System.out.println("Remaining attempt are : " + totalattempt + "\n");
				if (totalattempt == 0) {
					System.out.println("YOU LOSS..The right number is = " + compno + "\n");
				}
			}
		}
		numberguess();
	}
 public static void main(String[] args) {
	Task1 t=new Task1();
	t.numberguess();
}
}
