package FirstJava;
import java.util.Scanner;
public class PaymentSystem {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        double totalAmount;
        String paymentToPay;

        System.out.print("Enter total bill amount (BND): ");
        totalAmount = scanner.nextDouble();
        scanner.nextLine(); 

        System.out.println("Choose payment method:");
        System.out.println("1. Cash");
        System.out.println("2. Credit/Debit Card");
        System.out.println("3. E-Wallet");
        System.out.print("Enter your choice (1-3): ");
        int selection = scanner.nextInt();
        scanner.nextLine(); 

        switch (selection) {
            case 1:
                paymentToPay = "Cash";
                System.out.print("Enter amount paid (BND): ");
                double cashPaid = scanner.nextDouble();
                if (cashPaid >= totalAmount) {
                    double change = cashPaid - totalAmount;
                    System.out.println("Payment successful!");
                    System.out.printf("Change: BND%.2f%n", change);
                } else {
                    System.out.println("Insufficient cash. Transaction failed.");
                }
                break;

            case 2:
            	paymentToPay = "Card";
            	System.out.println("Please tap your card on the screen");
                System.out.print("Enter card number (last 4 digits): ");
                String cardNumber = scanner.nextLine();
                System.out.println("Processing card payment....");
                System.out.println("Payment successful via Card!");
                break;
                
            case 3:
                paymentToPay = "E-Wallet";
                System.out.print("Enter e-wallet name: ");
                String walletName = scanner.nextLine();
                System.out.print("Enter the token number: ");  
                String token = scanner.nextLine(); 
                System.out.println("Please scan the QR code on the screen using your e-wallet app");
                System.out.println("Scanning QR....");
                System.out.println("Payment successful via " + walletName + "!");
                break;

            default:
                paymentToPay = "Unknown";
                System.out.println("Invalid payment method selected.");
        }

        if (!paymentToPay.equals("Unknown")) {
            System.out.println("\n--- Receipt ---");
            System.out.printf("Total Amount: BND%.2f%n", totalAmount);
            System.out.println("Payment Method: " + paymentToPay);
            System.out.println("Thank you for dining with us!");
        }

        scanner.close();
    }
}
jjjj
