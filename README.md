import java.util.Scanner;

public class PrimeChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter a number to check: ");
        int number = scanner.nextInt();
        
        if (isPrime(number)) {
            System.out.println(number + " is a prime number.");
        } else {
            System.out.println(number + " is not a prime number.");
        }
        
        scanner.close();
    }

    public static boolean isPrime(int n) {
        // 1. Handle edge cases: numbers less than 2 are not prime
        if (n <= 1) {
            return false;
        }
        
        // 2. Check for divisibility from 2 up to sqrt(n)
        // Using i * i <= n is more efficient than calling Math.sqrt()
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0) {
                return false; // Found a factor, so it's not prime
            }
        }
        
        return true; // No factors found, it is prime
    }
}
