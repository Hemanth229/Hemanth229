import java.util.Scanner;

public class ATM{
    private double balance;
    
   
    public ATM(double initialBalance) {
        balance = initialBalance;
    }
    
   
    public double checkBalance() {
        return balance;
    }
    
    public void deposit(double amount) {
        if (amount > 0 &&amount<1000000) {
            balance += amount;
            System.out.println("Successfully deposited: " + amount);
        } else {
            System.out.println("Deposit amount must be positive and <200000.");
        }
    }
    
   
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Successfully withdrew: " + amount);
        } else if (amount > balance) {
            System.out.println("Insufficient funds.");
        } else {
            System.out.println("Withdrawal amount must be positive.");
        }
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
       
        
        ATM atm = new ATM(1000);
        
        while (true) {
            System.out.println("\nATM Menu:");
            System.out.println("1. Check Balance");
            System.out.println("2. Deposit");
            System.out.println("3. Withdraw");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            
            int choice = scanner.nextInt();
            
            switch (choice) {
                case 1:
                    System.out.println("Current balance: " + atm.checkBalance());
                    break;
                case 2:
                    System.out.print("Enter amount to deposit: ");
                    double depositAmount = scanner.nextDouble();
                    atm.deposit(depositAmount);
                    break;
                case 3:
                    System.out.print("Enter amount to withdraw: ");
                    double withdrawAmount = scanner.nextDouble();
                    atm.withdraw(withdrawAmount);
                    break;
                case 4:
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    scanner.close();
                    System.exit(0);
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        }
    }
}
OUTPUT
ATM Menu:
1. Check Balance
2. Deposit      
3. Withdraw     
4. Exit
Choose an option: 2
Enter amount to deposit: 5000
Successfully deposited: 5000.0

ATM Menu:
1. Check Balance
2. Deposit
3. Withdraw
4. Exit
Choose an option: 1
Current balance: 6000.0

ATM Menu:
1. Check Balance
2. Deposit
3. Withdraw
4. Exit
Choose an option: 3
Enter amount to withdraw: 5000
Successfully withdrew: 5000.0

ATM Menu:
1. Check Balance
2. Deposit
3. Withdraw
4. Exit
Choose an option: 1
Current balance: 1000.0
