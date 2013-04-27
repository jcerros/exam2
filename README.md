import java.util.Scanner;

public class Dice {
    static boolean playing = true;
	static boolean conversion = false;

	public static void main(String args[]) {
		Scanner Ozil = new Scanner(System.in);

		Dice2 object1 = new Dice2(1, 6);

		Dice2 object2 = new Dice2(1, 6);

		int computer;
		int computer2;

		computer = (object1.rollANumber1());
		computer2 = (object2.rollANumber2());
		System.out.println(computer);
		System.out.println(computer2);
		
		// convert dice2 objects to a usable variable
		do {

			int TotalValue;

			TotalValue = computer + computer2;
			System.out.println(TotalValue);

			int computerNum = 0;

			if (TotalValue <= 6) {
				computerNum = 0;
				
			} else if (TotalValue >= 7) {
				computerNum = 1;
				
				// high-low game
			}
			do {
				System.out
						.println("1-6 is low and 7-12 is high \n guess whether the dices number is low(select 0) or high(select 1):");

				int usermove;

				usermove = Ozil.nextInt();

				if (usermove == computerNum) {
					System.out.println("you win\n" + "dices rolled "
							+ TotalValue);
					playing = false;
				} else if (usermove != computerNum && computerNum == 0) {
					System.out.println("you lose!\n number was low\n"
							+ "dices rolled " + TotalValue);
					playing = false;
				} else if (usermove != computerNum && computerNum == 1) {
					System.out.println("you lose!\n number was high\n"
							+ "dices rolled " + TotalValue);
					playing = false;
				}
				// get out of game
			} while (playing);
			System.out.println("done!!");
			//leave second loop
		} while (conversion);
		System.out.println("goodbye!!");
		conversion=true;
		// end game
	}
}



public class Dice2 {
    int small,big; 
	public Dice2(int low, int high) { 
		small=low; big=high;

    }
    public int rollANumber1() {
       
        return small + (int) (Math.random() * big);
        

    }

    public int rollANumber2() {
      
        return small + (int) (Math.random() * big);
        
    }

}
