import java.util.Scanner;

public class Dice {
    public static void main(String args[]) {
        Scanner Ozil = new Scanner(System.in);

        Dice2 object2 = new Dice2(1, 6);

        Dice2 object3 = new Dice2(1, 6);

        System.out.println(object2.rollANumber());
        System.out.println(object3.rollANumber());

        int computer;
        int computerNum;
        computer = (object2.rollANumber());

        if (computer >= 4) {
            computerNum = 1;

        } else if (computer <= 3) {
            computerNum = 0;

            int usermove;
            System.out.println("low(0) or high(1)");
            usermove = Ozil.nextInt();

            if (usermove == computerNum) {
                System.out.println("you win");
            } else if (usermove != computerNum && computerNum == 0) {
                System.out.println("you lose number was high");

            } else if (usermove != computerNum && computerNum == 1) {
                System.out.println("you lose number was low");

            }

        }
    }
}






public class Dice2 {
    int small,big;
    public Dice2(int low, int high) {
        small=low;
        big=high;
        
        }
        public int rollANumber(int small, int big) {
            int computer;
            computer=small + (int) (Math.random() * big);
            return computer;
            
        }

        public int rollANumber() {
            int computer2;
            computer2=small + (int) (Math.random() * big);
            return computer2;
        }
}
