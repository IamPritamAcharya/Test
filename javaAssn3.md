# Class and Object

## Question 1
Write a program to create simple calculator for addition, subtraction, division, multiplication, modulus, factorial, gcd, lcm, power, square root, cube root using class and object?

```java
import java.util.Scanner;
import java.lang.Math;

class Calculator {

    public double add(double a, double b) {
        return a + b;
    }
    

    public double subtract(double a, double b) {
        return a - b;
    }
    

    public double multiply(double a, double b) {
        return a * b;
    }
    

    public double divide(double a, double b) {
        if (b == 0) {
            System.out.println("Error: Division by zero");
            return 0;
        }
        return a / b;
    }
    

    public double modulus(double a, double b) {
        if (b == 0) {
            System.out.println("Error: Modulus by zero");
            return 0;
        }
        return a % b;
    }
    

    public long factorial(int n) {
        if (n < 0) {
            System.out.println("Error: Factorial not defined for negative numbers");
            return 0;
        }
        if (n == 0 || n == 1)
            return 1;
        
        long fact = 1;
        for (int i = 2; i <= n; i++) {
            fact *= i;
        }
        return fact;
    }
    

    public int gcd(int a, int b) {
        if (a < 0) a = -a;
        if (b < 0) b = -b;
        
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
    

    public int lcm(int a, int b) {
        if (a == 0 || b == 0)
            return 0;
        
        int absA = Math.abs(a);
        int absB = Math.abs(b);
        
        return absA / gcd(absA, absB) * absB;
    }
    

    public double power(double base, double exponent) {
        return Math.pow(base, exponent);
    }
    

    public double squareRoot(double n) {
        if (n < 0) {
            System.out.println("Error: Square root of negative number");
            return 0;
        }
        return Math.sqrt(n);
    }
    

    public double cubeRoot(double n) {
        return Math.cbrt(n);
    }
}

public class SimpleCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Calculator calc = new Calculator();
        
        int choice;
        do {
            System.out.println("\nSimple Calculator Menu:");
            System.out.println("1. Addition");
            System.out.println("2. Subtraction");
            System.out.println("3. Multiplication");
            System.out.println("4. Division");
            System.out.println("5. Modulus");
            System.out.println("6. Factorial");
            System.out.println("7. GCD");
            System.out.println("8. LCM");
            System.out.println("9. Power");
            System.out.println("10. Square Root");
            System.out.println("11. Cube Root");
            System.out.println("0. Exit");
            System.out.print("Enter your choice: ");
            
            choice = scanner.nextInt();
            
            switch (choice) {
                case 1:
                    System.out.print("Enter first number: ");
                    double a1 = scanner.nextDouble();
                    System.out.print("Enter second number: ");
                    double b1 = scanner.nextDouble();
                    System.out.println("Result: " + calc.add(a1, b1));
                    break;
                    
                case 2:
                    System.out.print("Enter first number: ");
                    double a2 = scanner.nextDouble();
                    System.out.print("Enter second number: ");
                    double b2 = scanner.nextDouble();
                    System.out.println("Result: " + calc.subtract(a2, b2));
                    break;
                    
                case 3:
                    System.out.print("Enter first number: ");
                    double a3 = scanner.nextDouble();
                    System.out.print("Enter second number: ");
                    double b3 = scanner.nextDouble();
                    System.out.println("Result: " + calc.multiply(a3, b3));
                    break;
                    
                case 4:
                    System.out.print("Enter first number: ");
                    double a4 = scanner.nextDouble();
                    System.out.print("Enter second number: ");
                    double b4 = scanner.nextDouble();
                    System.out.println("Result: " + calc.divide(a4, b4));
                    break;
                    
                case 5:
                    System.out.print("Enter first number: ");
                    double a5 = scanner.nextDouble();
                    System.out.print("Enter second number: ");
                    double b5 = scanner.nextDouble();
                    System.out.println("Result: " + calc.modulus(a5, b5));
                    break;
                    
                case 6:
                    System.out.print("Enter a number: ");
                    int n6 = scanner.nextInt();
                    System.out.println("Result: " + calc.factorial(n6));
                    break;
                    
                case 7:
                    System.out.print("Enter first number: ");
                    int a7 = scanner.nextInt();
                    System.out.print("Enter second number: ");
                    int b7 = scanner.nextInt();
                    System.out.println("Result: " + calc.gcd(a7, b7));
                    break;
                    
                case 8:
                    System.out.print("Enter first number: ");
                    int a8 = scanner.nextInt();
                    System.out.print("Enter second number: ");
                    int b8 = scanner.nextInt();
                    System.out.println("Result: " + calc.lcm(a8, b8));
                    break;
                    
                case 9:
                    System.out.print("Enter base: ");
                    double a9 = scanner.nextDouble();
                    System.out.print("Enter exponent: ");
                    double b9 = scanner.nextDouble();
                    System.out.println("Result: " + calc.power(a9, b9));
                    break;
                    
                case 10:
                    System.out.print("Enter a number: ");
                    double n10 = scanner.nextDouble();
                    System.out.println("Result: " + calc.squareRoot(n10));
                    break;
                    
                case 11:
                    System.out.print("Enter a number: ");
                    double n11 = scanner.nextDouble();
                    System.out.println("Result: " + calc.cubeRoot(n11));
                    break;
                    
                case 0:
                    System.out.println("Exiting calculator...");
                    break;
                    
                default:
                    System.out.println("Invalid choice! Please try again.");
            }
            
        } while (choice != 0);
        
        scanner.close();
    }
}
```

### Sample Output
```
Simple Calculator Menu:
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Modulus
6. Factorial
7. GCD
8. LCM
9. Power
10. Square Root
11. Cube Root
0. Exit
Enter your choice: 1
Enter first number: 10
Enter second number: 20
Result: 30.0

Simple Calculator Menu:
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Modulus
6. Factorial
7. GCD
8. LCM
9. Power
10. Square Root
11. Cube Root
0. Exit
Enter your choice: 6
Enter a number: 5
Result: 120

Simple Calculator Menu:
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Modulus
6. Factorial
7. GCD
8. LCM
9. Power
10. Square Root
11. Cube Root
0. Exit
Enter your choice: 0
Exiting calculator...
```

## Question 2
Write a program to give information about any number such as whether it is even odd, prime or not prime, or positive or negative, palindrome or not using class and object?

```java
import java.util.Scanner;

class NumberInfo {

    public String checkEvenOdd(int num) {
        return (num % 2 == 0) ? "Even" : "Odd";
    }
    

    public String checkSign(int num) {
        if (num > 0)
            return "Positive";
        else if (num < 0)
            return "Negative";
        else
            return "Zero";
    }
    

    public boolean isPrime(int num) {
        if (num <= 1)
            return false;
        
        if (num <= 3)
            return true;
        
        if (num % 2 == 0 || num % 3 == 0)
            return false;
        
        for (int i = 5; i * i <= num; i += 6) {
            if (num % i == 0 || num % (i + 2) == 0)
                return false;
        }
        
        return true;
    }
    

    public boolean isPalindrome(int num) {
        int originalNum = num;
        int reversed = 0;
        
        while (num > 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        
        return originalNum == reversed;
    }
    

    public void displayInfo(int num) {
        System.out.println("Number: " + num);
        System.out.println("Type: " + checkEvenOdd(num));
        System.out.println("Sign: " + checkSign(num));
        System.out.println("Prime: " + (isPrime(num) ? "Yes" : "No"));
        System.out.println("Palindrome: " + (isPalindrome(Math.abs(num)) ? "Yes" : "No"));
    }
}

public class NumberInfoChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        NumberInfo info = new NumberInfo();
        
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();
        
        info.displayInfo(number);
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter a number: 121
Number: 121
Type: Odd
Sign: Positive
Prime: No
Palindrome: Yes

Enter a number: 23
Number: 23
Type: Odd
Sign: Positive
Prime: Yes
Palindrome: No
```

## Question 3
Write a program to find area and perimeter of rectangle using class and object?

```java
import java.util.Scanner;

class Rectangle {
    private double length;
    private double width;
    

    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }
    

    public double calculateArea() {
        return length * width;
    }
    

    public double calculatePerimeter() {
        return 2 * (length + width);
    }
    

    public void displayResults() {
        System.out.println("Rectangle dimensions: Length = " + length + ", Width = " + width);
        System.out.println("Area of rectangle: " + calculateArea());
        System.out.println("Perimeter of rectangle: " + calculatePerimeter());
    }
}

public class RectangleCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter length of rectangle: ");
        double length = scanner.nextDouble();
        
        System.out.print("Enter width of rectangle: ");
        double width = scanner.nextDouble();
        
        Rectangle rect = new Rectangle(length, width);
        rect.displayResults();
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter length of rectangle: 5
Enter width of rectangle: 3
Rectangle dimensions: Length = 5.0, Width = 3.0
Area of rectangle: 15.0
Perimeter of rectangle: 16.0
```

## Question 4
Write a program to find area and perimeter of square using class and object?

```java
import java.util.Scanner;

class Square {
    private double side;
    

    public Square(double side) {
        this.side = side;
    }
    

    public double calculateArea() {
        return side * side;
    }
    

    public double calculatePerimeter() {
        return 4 * side;
    }
    

    public void displayResults() {
        System.out.println("Square side length: " + side);
        System.out.println("Area of square: " + calculateArea());
        System.out.println("Perimeter of square: " + calculatePerimeter());
    }
}

public class SquareCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter side length of square: ");
        double side = scanner.nextDouble();
        
        Square square = new Square(side);
        square.displayResults();
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter side length of square: 4
Square side length: 4.0
Area of square: 16.0
Perimeter of square: 16.0
```

## Question 5
Write a program to find area and perimeter of triangle having 3 sides using class and object?

```java
import java.util.Scanner;
import java.lang.Math;

class Triangle {
    private double side1;
    private double side2;
    private double side3;
    

    public Triangle(double side1, double side2, double side3) {
        this.side1 = side1;
        this.side2 = side2;
        this.side3 = side3;
    }
    

    public boolean isValid() {
        return (side1 + side2 > side3) && 
               (side1 + side3 > side2) && 
               (side2 + side3 > side1);
    }
    

    public double calculatePerimeter() {
        return side1 + side2 + side3;
    }
    

    public double calculateArea() {
        if (!isValid()) {
            return 0;
        }
        
        double s = calculatePerimeter() / 2;
        return Math.sqrt(s * (s - side1) * (s - side2) * (s - side3));
    }
    

    public void displayResults() {
        if (!isValid()) {
            System.out.println("Invalid triangle! The sum of the lengths of any two sides must be greater than the length of the remaining side.");
            return;
        }
        
        System.out.println("Triangle sides: " + side1 + ", " + side2 + ", " + side3);
        System.out.println("Area of triangle: " + calculateArea());
        System.out.println("Perimeter of triangle: " + calculatePerimeter());
    }
}

public class TriangleCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter length of first side: ");
        double side1 = scanner.nextDouble();
        
        System.out.print("Enter length of second side: ");
        double side2 = scanner.nextDouble();
        
        System.out.print("Enter length of third side: ");
        double side3 = scanner.nextDouble();
        
        Triangle triangle = new Triangle(side1, side2, side3);
        triangle.displayResults();
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter length of first side: 3
Enter length of second side: 4
Enter length of third side: 5
Triangle sides: 3.0, 4.0, 5.0
Area of triangle: 6.0
Perimeter of triangle: 12.0
```

## Question 6
Write a program to display type of triangle using sides of triangle?

```java
import java.util.Scanner;

class TriangleClassifier {
    private double side1;
    private double side2;
    private double side3;
    

    public TriangleClassifier(double side1, double side2, double side3) {
        this.side1 = side1;
        this.side2 = side2;
        this.side3 = side3;
    }
    

    public boolean isValid() {
        return (side1 + side2 > side3) && 
               (side1 + side3 > side2) && 
               (side2 + side3 > side1);
    }
    

    public String determineType() {
        if (!isValid()) {
            return "Not a valid triangle";
        }
        
        if (side1 == side2 && side2 == side3) {
            return "Equilateral Triangle";
        } else if (side1 == side2 || side1 == side3 || side2 == side3) {
            return "Isosceles Triangle";
        } else {
            return "Scalene Triangle";
        }
    }
    

    public boolean isRightTriangle() {
        if (!isValid()) {
            return false;
        }
        
        double[] sides = {side1, side2, side3};
        java.util.Arrays.sort(sides);
        

        return Math.abs(Math.pow(sides[0], 2) + Math.pow(sides[1], 2) - Math.pow(sides[2], 2)) < 0.000001;
    }
    

    public void displayResults() {
        System.out.println("Triangle sides: " + side1 + ", " + side2 + ", " + side3);
        System.out.println("Triangle type: " + determineType());
        
        if (isValid() && isRightTriangle()) {
            System.out.println("This is also a Right Triangle");
        }
    }
}

public class TriangleTypeClassifier {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter length of first side: ");
        double side1 = scanner.nextDouble();
        
        System.out.print("Enter length of second side: ");
        double side2 = scanner.nextDouble();
        
        System.out.print("Enter length of third side: ");
        double side3 = scanner.nextDouble();
        
        TriangleClassifier triangle = new TriangleClassifier(side1, side2, side3);
        triangle.displayResults();
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter length of first side: 3
Enter length of second side: 4
Enter length of third side: 5
Triangle sides: 3.0, 4.0, 5.0
Triangle type: Scalene Triangle
This is also a Right Triangle

Enter length of first side: 5
Enter length of second side: 5
Enter length of third side: 5
Triangle sides: 5.0, 5.0, 5.0
Triangle type: Equilateral Triangle
```

## Question 7
Write a java program to create banking application to perform following using using class and object?
a) Initialize with initial balance Rs 3000
b) Deposit amount if balance is more than 1000 otherwise take Rs 100 as penalty for deposit
c) Withdraw amount if balance is more than 1000 otherwise alert user for low balance
d) check for balance

```java
import java.util.Scanner;

class BankAccount {
    private double balance;
    private String accountNumber;
    private String accountHolder;
    

    public BankAccount(String accountNumber, String accountHolder) {
        this.accountNumber = accountNumber;
        this.accountHolder = accountHolder;
        this.balance = 3000; // Initial balance of Rs 3000
    }
    

    public void deposit(double amount) {
        if (amount <= 0) {
            System.out.println("Invalid deposit amount. Amount must be positive.");
            return;
        }
        
        if (balance < 1000) {
            System.out.println("Low balance penalty of Rs 100 applied for deposit.");
            balance = balance + amount - 100; // Apply penalty
        } else {
            balance += amount;
        }
        
        System.out.println("Rs " + amount + " deposited successfully.");
        checkBalance();
    }
    

    public void withdraw(double amount) {
        if (amount <= 0) {
            System.out.println("Invalid withdrawal amount. Amount must be positive.");
            return;
        }
        
        if (balance < 1000) {
            System.out.println("Alert: Low balance! Withdrawal not allowed.");
            return;
        }
        
        if (amount > balance) {
            System.out.println("Insufficient funds for withdrawal.");
            return;
        }
        
        balance -= amount;
        System.out.println("Rs " + amount + " withdrawn successfully.");
        checkBalance();
    }
    

    public void checkBalance() {
        System.out.println("Current Balance: Rs " + balance);
    }
    

    public void displayAccountDetails() {
        System.out.println("\nAccount Details:");
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Account Holder: " + accountHolder);
        checkBalance();
    }
}

public class BankingApplication {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        

        System.out.print("Enter Account Number: ");
        String accountNumber = scanner.nextLine();
        
        System.out.print("Enter Account Holder Name: ");
        String accountHolder = scanner.nextLine();
        
        BankAccount account = new BankAccount(accountNumber, accountHolder);
        account.displayAccountDetails();
        
        int choice;
        do {
            System.out.println("\nBanking Menu:");
            System.out.println("1. Deposit Money");
            System.out.println("2. Withdraw Money");
            System.out.println("3. Check Balance");
            System.out.println("4. Display Account Details");
            System.out.println("0. Exit");
            System.out.print("Enter your choice: ");
            
            choice = scanner.nextInt();
            
            switch (choice) {
                case 1:
                    System.out.print("Enter amount to deposit: ");
                    double depositAmount = scanner.nextDouble();
                    account.deposit(depositAmount);
                    break;
                    
                case 2:
                    System.out.print("Enter amount to withdraw: ");
                    double withdrawAmount = scanner.nextDouble();
                    account.withdraw(withdrawAmount);
                    break;
                    
                case 3:
                    account.checkBalance();
                    break;
                    
                case 4:
                    account.displayAccountDetails();
                    break;
                    
                case 0:
                    System.out.println("Thank you for using our banking services!");
                    break;
                    
                default:
                    System.out.println("Invalid choice! Please try again.");
            }
            
        } while (choice != 0);
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter Account Number: ACC123456
Enter Account Holder Name: John Doe

Account Details:
Account Number: ACC123456
Account Holder: John Doe
Current Balance: Rs 3000.0

Banking Menu:
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Display Account Details
0. Exit
Enter your choice: 1
Enter amount to deposit: 2000
Rs 2000.0 deposited successfully.
Current Balance: Rs 5000.0

Banking Menu:
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Display Account Details
0. Exit
Enter your choice: 2
Enter amount to withdraw: 4500
Rs 4500.0 withdrawn successfully.
Current Balance: Rs 500.0

Banking Menu:
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Display Account Details
0. Exit
Enter your choice: 2
Enter amount to withdraw: 200
Alert: Low balance! Withdrawal not allowed.

Banking Menu:
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Display Account Details
0. Exit
Enter your choice: 1
Enter amount to deposit: 1000
Low balance penalty of Rs 100 applied for deposit.
Rs 1000.0 deposited successfully.
Current Balance: Rs 1400.0

Banking Menu:
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Display Account Details
0. Exit
Enter your choice: 0
Thank you for using our banking services!
```

## Question 8
Write a program to search for a user defined number in array of 20 numbers using linear search and binary search using class and object? Allow user to choose searching method.

```java
import java.util.Arrays;
import java.util.Scanner;
import java.util.Random;

class SearchOperations {
    private int[] arr;
    

    public SearchOperations(int[] arr) {
        this.arr = arr;
    }

    public int linearSearch(int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i; 
            }
        }
        return -1;
    }
    

    public int binarySearch(int target) {
        int left = 0;
        int right = arr.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            // Check if target is present at mid
            if (arr[mid] == target) {
                return mid;
            }
            
            // If target greater, ignore left half
            if (arr[mid] < target) {
                left = mid + 1;
            }
            // If target is smaller, ignore right half
            else {
                right = mid - 1;
            }
        }
        
        return -1; 
    }
    

    public int[] getArray() {
        return arr;
    }
    

    public int[] getSortedArray() {
        int[] sortedArr = Arrays.copyOf(arr, arr.length);
        Arrays.sort(sortedArr);
        return sortedArr;
    }
}

public class SearchProgram {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        
        int[] numbers = new int[20];
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = random.nextInt(100);
        }
        
        SearchOperations search = new SearchOperations(numbers);
        

        System.out.println("Generated array of 20 numbers:");
        displayArray(numbers);
        

        System.out.print("\nEnter the number to search for: ");
        int target = scanner.nextInt();
        

        System.out.println("\nChoose search method:");
        System.out.println("1. Linear Search");
        System.out.println("2. Binary Search");
        System.out.print("Enter your choice (1 or 2): ");
        
        int choice = scanner.nextInt();
        
        int result;
        switch (choice) {
            case 1: 
                result = search.linearSearch(target);
                if (result != -1) {
                    System.out.println("Linear Search: Element found at index " + result);
                } else {
                    System.out.println("Linear Search: Element not found in the array");
                }
                break;
                
            case 2:

                int[] sortedArray = search.getSortedArray();
                System.out.println("\nSorted array for binary search:");
                displayArray(sortedArray);
                

                SearchOperations sortedSearch = new SearchOperations(sortedArray);
                result = sortedSearch.binarySearch(target);
                
                if (result != -1) {
                    System.out.println("Binary Search: Element found at index " + result + " in the sorted array");
                } else {
                    System.out.println("Binary Search: Element not found in the array");
                }
                break;
                
            default:
                System.out.println("Invalid choice!");
        }
        
        scanner.close();
    }
    

    private static void displayArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
            if ((i + 1) % 10 == 0) {
                System.out.println();
            }
        }
        if (arr.length % 10 != 0) {
            System.out.println();
        }
    }
}
```

### Sample Output
```
Generated array of 20 numbers:
62 31 84 96 19 47 35 89 70 28 
51 44 16 78 23 99 54 18 65 77 

Enter the number to search for: 47

Choose search method:
1. Linear Search
2. Binary Search
Enter your choice (1 or 2): 1
Linear Search: Element found at index 5

Generated array of 20 numbers:
62 31 84 96 19 47 35 89 70 28 
51 44 16 78 23 99 54 18 65 77 

Enter the number to search for: 47

Choose search method:
1. Linear Search
2. Binary Search
Enter your choice (1 or 2): 2

Sorted array for binary search:
16 18 19 23 28 31 35 44 47 51 
54 62 65 70 77 78 84 89 96 99 
Binary Search: Element found at index 8 in the sorted array
```

## Question 9
Write a program to implement stack and perform following using class
a) create an stack of size 10 using array
b) insert 10 elements into stack using push and isfull method
c) find factorial of difference between largest and smallest element of stack
d) search any user defined element in stack using peak method
e) delete 3 elements from stack using pop and isempty method
f) display remaining element of stack

```java
import java.util.Scanner;

class Stack {
    private int maxSize;
    private int[] stackArray;
    private int top;
    

    public Stack(int size) {
        maxSize = size;
        stackArray = new int[maxSize];
        top = -1; // Stack is initially empty
    }
    

    public boolean isFull() {
        return (top == maxSize - 1);
    }
    

    public boolean isEmpty() {
        return (top == -1);
    }
    

    public void push(int value) {
        if (isFull()) {
            System.out.println("Stack is full. Cannot push element.");
            return;
        }
        stackArray[++top] = value;
    }
    

    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack is empty. Cannot pop element.");
            return -1;
        }
        return stackArray[top--];
    }
    

    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty. No element to peek.");
            return -1;
        }
        return stackArray[top];
    }
    

    public int getMin() {
        if (isEmpty()) {
            System.out.println("Stack is empty.");
            return -1;
        }
        
        int min = stackArray[0];
        for (int i = 1; i <= top; i++) {
            if (stackArray[i] < min) {
                min = stackArray[i];
            }
        }
        return min;
    }
    

    public int getMax() {
        if (isEmpty()) {
            System.out.println("Stack is empty.");
            return -1;
        }
        
        int max = stackArray[0];
        for (int i = 1; i <= top; i++) {
            if (stackArray[i] > max) {
                max = stackArray[i];
            }
        }
        return max;
    }
    

    public int search(int element) {
        for (int i = top; i >= 0; i--) {
            if (stackArray[i] == element) {
                return top - i; 
            }
        }
        return -1; 
    }
    

    public long factorial(int n) {
        if (n < 0) {
            System.out.println("Factorial not defined for negative numbers");
            return -1;
        }
        if (n == 0 || n == 1) {
            return 1;
        }
        
        long fact = 1;
        for (int i = 2; i <= n; i++) {
            fact *= i;
        }
        return fact;
    }
    

    public void display() {
        if (isEmpty()) {
            System.out.println("Stack is empty.");
            return;
        }
        
        System.out.println("Stack elements:");
        for (int i = top; i >= 0; i--) {
            System.out.println(stackArray[i]);
        }
    }
    

    public int size() {
        return top + 1;
    }
}

public class StackOperations {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        

        Stack stack = new Stack(10);

        System.out.println("Enter 10 elements to push into the stack:");
        for (int i = 0; i < 10; i++) {
            if (!stack.isFull()) {
                System.out.print("Enter element " + (i+1) + ": ");
                int element = scanner.nextInt();
                stack.push(element);
            } else {
                System.out.println("Stack is full. Cannot push more elements.");
                break;
            }
        }
        
        System.out.println("\nStack after inserting 10 elements:");
        stack.display();
        

        int max = stack.getMax();
        int min = stack.getMin();
        int difference = max - min;
        long factorial = stack.factorial(difference);
        
        System.out.println("\nLargest element: " + max);
        System.out.println("Smallest element: " + min);
        System.out.println("Difference: " + difference);
        System.out.println("Factorial of difference: " + factorial);
        

        System.out.print("\nEnter an element to search in the stack: ");
        int searchElement = scanner.nextInt();
        int position = stack.search(searchElement);
        
        if (position != -1) {
            System.out.println("Element " + searchElement + " found at position " + position + " from the top.");
        } else {
            System.out.println("Element " + searchElement + " not found in the stack.");
        }
        
        System.out.println("\nPopping 3 elements from stack:");
        for (int i = 0; i < 3; i++) {
            if (!stack.isEmpty()) {
                int popped = stack.pop();
                System.out.println("Popped: " + popped);
            } else {
                System.out.println("Stack is empty. Cannot pop more elements.");
                break;
            }
        }
        

        System.out.println("\nRemaining elements in the stack:");
        stack.display();
        System.out.println("Number of elements remaining: " + stack.size());
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter 10 elements to push into the stack:
Enter element 1: 5
Enter element 2: 10
Enter element 3: 15
Enter element 4: 20
Enter element 5: 25
Enter element 6: 30
Enter element 7: 35
Enter element 8: 40
Enter element 9: 45
Enter element 10: 50

Stack after inserting 10 elements:
Stack elements:
50
45
40
35
30
25
20
15
10
5

Largest element: 50
Smallest element: 5
Difference: 45
Factorial of difference: 119622220865480194561963161495657715064383733760000000000

Enter an element to search in the stack: 30
Element 30 found at position 5 from the top.

Popping 3 elements from stack:
Popped: 50
Popped: 45
Popped: 40

Remaining elements in the stack:
Stack elements:
35
30
25
20
15
10
5
Number of elements remaining: 7
```

## Question 10
Write a program to implement queue and perform following using class and object?
a) create an queue of size 10 using array
b) insert 10 elements into queue using insert method
c) replace even numbers available in queue with nearest prime numbers
d) display number of odd and prime numbers.
e) delete 3 elements from queue using delete method
f) display remaining element of queue.

```java
import java.util.Scanner;

class Queue {
    private int maxSize;
    private int[] queueArray;
    private int front;
    private int rear;
    private int nItems;
    

    public Queue(int size) {
        maxSize = size;
        queueArray = new int[maxSize];
        front = 0;
        rear = -1;
        nItems = 0;
    }
    

    public boolean isFull() {
        return (nItems == maxSize);
    }
    

    public boolean isEmpty() {
        return (nItems == 0);
    }
    
    public void insert(int value) {
        if (isFull()) {
            System.out.println("Queue is full. Cannot insert element.");
            return;
        }
        
        if (rear == maxSize - 1) { 
            rear = -1;
        }
        
        queueArray[++rear] = value;
        nItems++;
    }
    

    public int delete() {
        if (isEmpty()) {
            System.out.println("Queue is empty. Cannot delete element.");
            return -1;
        }
        
        int temp = queueArray[front++];
        if (front == maxSize) { // Deal with circular queue
            front = 0;
        }
        
        nItems--;
        return temp;
    }
    

    public int peekFront() {
        if (isEmpty()) {
            System.out.println("Queue is empty. No element to peek.");
            return -1;
        }
        return queueArray[front];
    }
    

    public int size() {
        return nItems;
    }
    

    public boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        
        if (num <= 3) {
            return true;
        }
        
        if (num % 2 == 0 || num % 3 == 0) {
            return false;
        }
        
        for (int i = 5; i * i <= num; i += 6) {
            if (num % i == 0 || num % (i + 2) == 0) {
                return false;
            }
        }
        
        return true;
    }
    

    public int findNearestPrime(int num) {
        if (isPrime(num)) {
            return num;
        }
        

        int nextPrime = num + 1;
        while (!isPrime(nextPrime)) {
            nextPrime++;
        }
        
        return nextPrime;
    }
    

    public void replaceEvenWithPrime() {
        for (int i = 0; i < nItems; i++) {
            int index = (front + i) % maxSize;
            if (queueArray[index] % 2 == 0) { // If number is even
                queueArray[index] = findNearestPrime(queueArray[index]);
            }
        }
    }
    

    public int countOdd() {
        int count = 0;
        for (int i = 0; i < nItems; i++) {
            int index = (front + i) % maxSize;
            if (queueArray[index] % 2 != 0) { // If number is odd
                count++;
            }
        }
        return count;
    }
    

    public int countPrime() {
        int count = 0;
        for (int i = 0; i < nItems; i++) {
            int index = (front + i) % maxSize;
            if (isPrime(queueArray[index])) { // If number is prime
                count++;
            }
        }
        return count;
    }
    

    public void display() {
        if (isEmpty()) {
            System.out.println("Queue is empty.");
            return;
        }
        
        System.out.println("Queue elements (front to rear):");
        for (int i = 0; i < nItems; i++) {
            int index = (front + i) % maxSize;
            System.out.print(queueArray[index] + " ");
        }
        System.out.println();
    }
}

public class QueueOperations {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        

        Queue queue = new Queue(10);
        

        System.out.println("Enter 10 elements to insert into the queue:");
        for (int i = 0; i < 10; i++) {
            if (!queue.isFull()) {
                System.out.print("Enter element " + (i+1) + ": ");
                int element = scanner.nextInt();
                queue.insert(element);
            } else {
                System.out.println("Queue is full. Cannot insert more elements.");
                break;
            }
        }
        

        System.out.println("\nQueue after inserting 10 elements:");
        queue.display();
        

        queue.replaceEvenWithPrime();
        System.out.println("\nQueue after replacing even numbers with nearest prime numbers:");
        queue.display();
        

        int oddCount = queue.countOdd();
        int primeCount = queue.countPrime();
        System.out.println("\nNumber of odd numbers in queue: " + oddCount);
        System.out.println("Number of prime numbers in queue: " + primeCount);
        

        System.out.println("\nDeleting 3 elements from queue:");
        for (int i = 0; i < 3; i++) {
            if (!queue.isEmpty()) {
                int deleted = queue.delete();
                System.out.println("Deleted: " + deleted);
            } else {
                System.out.println("Queue is empty. Cannot delete more elements.");
                break;
            }
        }
        
        System.out.println("\nRemaining elements in the queue:");
        queue.display();
        System.out.println("Number of elements remaining: " + queue.size());
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter 10 elements to insert into the queue:
Enter element 1: 4
Enter element 2: 7
Enter element 3: 12
Enter element 4: 15
Enter element 5: 18
Enter element 6: 23
Enter element 7: 30
Enter element 8: 37
Enter element 9: 42
Enter element 10: 45

Queue after inserting 10 elements:
Queue elements (front to rear):
4 7 12 15 18 23 30 37 42 45

Queue after replacing even numbers with nearest prime numbers:
Queue elements (front to rear):
5 7 13 15 19 23 31 37 43 45

Number of odd numbers in queue: 10
Number of prime numbers in queue: 8

Deleting 3 elements from queue:
Deleted: 5
Deleted: 7
Deleted: 13

Remaining elements in the queue:
Queue elements (front to rear):
15 19 23 31 37 43 45
Number of elements remaining: 7
```

## Question 11
Write a program to swap two numbers without using 3rd variable and with using 3rd variable using class and object?

```java
import java.util.Scanner;

class NumberSwapper {

    public void swapUsingThirdVariable(int a, int b) {
        System.out.println("Before swapping (with 3rd variable):");
        System.out.println("a = " + a + ", b = " + b);
        
        int temp = a;
        a = b;
        b = temp;
        
        System.out.println("After swapping (with 3rd variable):");
        System.out.println("a = " + a + ", b = " + b);
    }
    

    public void swapWithoutThirdVariableUsingAddSub(int a, int b) {
        System.out.println("Before swapping (without 3rd variable, using +/-):");
        System.out.println("a = " + a + ", b = " + b);
        
        a = a + b;
        b = a - b;
        a = a - b;
        
        System.out.println("After swapping (without 3rd variable, using +/-):");
        System.out.println("a = " + a + ", b = " + b);
    }
    

    public void swapWithoutThirdVariableUsingXOR(int a, int b) {
        System.out.println("Before swapping (without 3rd variable, using XOR):");
        System.out.println("a = " + a + ", b = " + b);
        
        a = a ^ b;
        b = a ^ b;
        a = a ^ b;
        
        System.out.println("After swapping (without 3rd variable, using XOR):");
        System.out.println("a = " + a + ", b = " + b);
    }
    

    public void swapWithoutThirdVariableUsingMultDiv(int a, int b) {

        if (a == 0 || b == 0) {
            System.out.println("Multiplication/Division method requires both numbers to be non-zero");
            return;
        }
        
        System.out.println("Before swapping (without 3rd variable, using */):");
        System.out.println("a = " + a + ", b = " + b);
        
        a = a * b;
        b = a / b;
        a = a / b;
        
        System.out.println("After swapping (without 3rd variable, using */):");
        System.out.println("a = " + a + ", b = " + b);
    }
}

public class NumberSwapDemo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter first number (a): ");
        int num1 = scanner.nextInt();
        
        System.out.print("Enter second number (b): ");
        int num2 = scanner.nextInt();
        
        NumberSwapper swapper = new NumberSwapper();
        
        swapper.swapUsingThirdVariable(num1, num2);
        
        System.out.println(); 
        

        swapper.swapWithoutThirdVariableUsingAddSub(num1, num2);
        
        System.out.println(); // Line break for readability
        

        swapper.swapWithoutThirdVariableUsingXOR(num1, num2);
        
        System.out.println();
        

        swapper.swapWithoutThirdVariableUsingMultDiv(num1, num2);
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter first number (a): 10
Enter second number (b): 20

Before swapping (with 3rd variable):
a = 10, b = 20
After swapping (with 3rd variable):
a = 20, b = 10

Before swapping (without 3rd variable, using +/-):
a = 10, b = 20
After swapping (without 3rd variable, using +/-):
a = 20, b = 10

Before swapping (without 3rd variable, using XOR):
a = 10, b = 20
After swapping (without 3rd variable, using XOR):
a = 20, b = 10

Before swapping (without 3rd variable, using */):
a = 10, b = 20
After swapping (without 3rd variable, using */):
a = 20, b = 10
```

# Polymorphism

## Question 1
Write a program to find area and perimeter of circle, square, rectangle and triangle using method overloading?

```java
import java.util.Scanner;

class ShapeCalculator {

    private static final double PI = 3.14159265359;
    

    public double area(double radius) {
        return PI * radius * radius;
    }
    

    public double area(int side) {
        return side * side;
    }

    public double area(double length, double width) {
        return length * width;
    }
    
    public double area(double side1, double side2, double side3) {

        double s = (side1 + side2 + side3) / 2;
        return Math.sqrt(s * (s - side1) * (s - side2) * (s - side3));
    }
    

    public double perimeter(double radius) {
        return 2 * PI * radius;
    }
    

    public double perimeter(int side) {
        return 4 * side;
    }
    

    public double perimeter(double length, double width) {
        return 2 * (length + width);
    }
    
    public double perimeter(double side1, double side2, double side3) {
        return side1 + side2 + side3;
    }
}

public class ShapeCalculation {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ShapeCalculator calc = new ShapeCalculator();
        
        int choice;
        do {
            System.out.println("\nShape Calculator Menu:");
            System.out.println("1. Circle");
            System.out.println("2. Square");
            System.out.println("3. Rectangle");
            System.out.println("4. Triangle");
            System.out.println("0. Exit");
            System.out.print("Enter your choice: ");
            
            choice = scanner.nextInt();
            
            switch (choice) {
                case 1: 
                    System.out.print("Enter radius of circle: ");
                    double radius = scanner.nextDouble();
                    
                    System.out.println("Area of circle: " + calc.area(radius));
                    System.out.println("Perimeter (Circumference) of circle: " + calc.perimeter(radius));
                    break;
                    
                case 2: 
                    System.out.print("Enter side length of square: ");
                    int side = scanner.nextInt();
                    
                    System.out.println("Area of square: " + calc.area(side));
                    System.out.println("Perimeter of square: " + calc.perimeter(side));
                    break;
                    
                case 3:
                    System.out.print("Enter length of rectangle: ");
                    double length = scanner.nextDouble();
                    System.out.print("Enter width of rectangle: ");
                    double width = scanner.nextDouble();
                    
                    System.out.println("Area of rectangle: " + calc.area(length, width));
                    System.out.println("Perimeter of rectangle: " + calc.perimeter(length, width));
                    break;
                    
                case 4: 
                    System.out.print("Enter length of first side: ");
                    double side1 = scanner.nextDouble();
                    System.out.print("Enter length of second side: ");
                    double side2 = scanner.nextDouble();
                    System.out.print("Enter length of third side: ");
                    double side3 = scanner.nextDouble();
                    
                    if (side1 + side2 > side3 && side1 + side3 > side2 && side2 + side3 > side1) {
                        System.out.println("Area of triangle: " + calc.area(side1, side2, side3));
                        System.out.println("Perimeter of triangle: " + calc.perimeter(side1, side2, side3));
                    } else {
                        System.out.println("Invalid triangle! The sum of any two sides must be greater than the third side.");
                    }
                    break;
                    
                case 0:
                    System.out.println("Exiting...");
                    break;
                    
                default:
                    System.out.println("Invalid choice! Please try again.");
            }
            
        } while (choice != 0);
        
        scanner.close();
    }
}
```

### Sample Output
```
Shape Calculator Menu:
1. Circle
2. Square
3. Rectangle
4. Triangle
0. Exit
Enter your choice: 1
Enter radius of circle: 5
Area of circle: 78.53981633975
Perimeter (Circumference) of circle: 31.4159265359

Shape Calculator Menu:
1. Circle
2. Square
3. Rectangle
4. Triangle
0. Exit
Enter your choice: 2
Enter side length of square: 4
Area of square: 16.0
Perimeter of square: 16.0

Shape Calculator Menu:
1. Circle
2. Square
3. Rectangle
4. Triangle
0. Exit
Enter your choice: 3
Enter length of rectangle: 5
Enter width of rectangle: 3
Area of rectangle: 15.0
Perimeter of rectangle: 16.0

Shape Calculator Menu:
1. Circle
2. Square
3. Rectangle
4. Triangle
0. Exit
Enter your choice: 4
Enter length of first side: 3
Enter length of second side: 4
Enter length of third side: 5
Area of triangle: 6.0
Perimeter of triangle: 12.0

Shape Calculator Menu:
1. Circle
2. Square
3. Rectangle
4. Triangle
0. Exit
Enter your choice: 0
Exiting...
```

## Question 2
Write program to display following pattern using method overloading and constructor overloading?

Odd number based pyramid starts from value n received from user
```
n+1
n+3 n+6
n+5 n+10 n+15
n+7 n+14 n+21 n+28
```

even number based pyramid starts from value n received from user
```
n+2
n+4 n+6
n+6 n+10 n+14
n+8 n+14 n+20 n+26
```

user defined character suppose entered character is k
```
k
k k
k k k
k k k k
```

```java
import java.util.Scanner;

class PatternGenerator {
    private int n;
    private char ch;
    

    public PatternGenerator(int n) {
        this.n = n;
    }
    

    public PatternGenerator(char ch) {
        this.ch = ch;
    }
    

    public void generatePattern(boolean isOdd) {
        System.out.println("Generating " + (isOdd ? "Odd" : "Even") + " number pattern for n = " + n);
        
        if (isOdd) {

            for (int i = 1; i <= 4; i++) {
                for (int j = 1; j <= i; j++) {
                    int value = n + (2 * i - 1) + (j - 1) * i;
                    System.out.print(value + " ");
                }
                System.out.println();
            }
        } else {

            for (int i = 1; i <= 4; i++) {
                for (int j = 1; j <= i; j++) {
                    int value = n + (2 * i) + (j - 1) * i;
                    System.out.print(value + " ");
                }
                System.out.println();
            }
        }
    }
    

    public void generatePattern() {
        System.out.println("Generating character pattern for character: " + ch);
        
        for (int i = 1; i <= 4; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(ch + " ");
            }
            System.out.println();
        }
    }
}

public class PatternDisplay {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter value of n for number patterns: ");
        int n = scanner.nextInt();
        

        PatternGenerator numPattern = new PatternGenerator(n);
        
        numPattern.generatePattern(true);
        
        System.out.println();
        

        numPattern.generatePattern(false);
        
        System.out.println(); 
        

        System.out.print("Enter a character for character pattern: ");
        char ch = scanner.next().charAt(0);
        

        PatternGenerator charPattern = new PatternGenerator(ch);
        

        charPattern.generatePattern();
        
        scanner.close();
    }
}
```

### Sample Output
```
Enter value of n for number patterns: 5
Generating Odd number pattern for n = 5
6 
8 11 
10 15 20 
12 19 26 33 

Generating Even number pattern for n = 5
7 
9 11 
11 15 19 
13 19 25 31 

Enter a character for character pattern: k
Generating character pattern for character: k
k 
k k 
k k k 
k k k k 
```



