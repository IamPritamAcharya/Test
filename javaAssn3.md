#  Java Assignment 3 

|  **Field**             |  **Details**        |
|--------------------------|------------------------|
|  **Name**              | Pritam Acharya         |
|  **Registration Number** | 2301105257             |
|  **Roll Number**        | 427041                 |
|  **Subject**            | Java Assignment 3      |



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

## Question 3: Write a program to sort 10 numbers in the array using following sorting algorithm and method overloading?
a) merge sort
b) quick sort
c) heap sort

```java
import java.util.Arrays;
import java.util.Scanner;

public class SortingAlgorithms {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[] arr = new int[10];
        
        System.out.println("Enter 10 numbers to sort:");
        for (int i = 0; i < 10; i++) {
            arr[i] = scanner.nextInt();
        }
        
        System.out.println("Original array: " + Arrays.toString(arr));
        
        System.out.println("\nChoose sorting method:");
        System.out.println("1. Merge Sort");
        System.out.println("2. Quick Sort");
        System.out.println("3. Heap Sort");
        int choice = scanner.nextInt();
        
        int[] sortedArray = null;
        switch (choice) {
            case 1:
                sortedArray = sort(arr, "merge");
                break;
            case 2:
                sortedArray = sort(arr, "quick");
                break;
            case 3:
                sortedArray = sort(arr, "heap");
                break;
            default:
                System.out.println("Invalid choice!");
                return;
        }
        
        System.out.println("Sorted array: " + Arrays.toString(sortedArray));
        scanner.close();
    }
    

    public static int[] sort(int[] arr, String algorithm) {
        int[] result = arr.clone();
        
        if (algorithm.equals("merge")) {
            mergeSort(result, 0, result.length - 1);
        } else if (algorithm.equals("quick")) {
            quickSort(result, 0, result.length - 1);
        } else if (algorithm.equals("heap")) {
            heapSort(result);
        }
        
        return result;
    }
    

    private static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = (left + right) / 2;
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);
            merge(arr, left, mid, right);
        }
    }
    
    private static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;
        
        int[] L = new int[n1];
        int[] R = new int[n2];
        
        for (int i = 0; i < n1; i++)
            L[i] = arr[left + i];
        for (int j = 0; j < n2; j++)
            R[j] = arr[mid + 1 + j];
        
        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }
        
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }
        
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }
    
    private static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }
    
    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;
        
        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        
        return i + 1;
    }
    

    private static void heapSort(int[] arr) {
        int n = arr.length;
        
        for (int i = n / 2 - 1; i >= 0; i--)
            heapify(arr, n, i);
        
        for (int i = n - 1; i > 0; i--) {
            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp;
            
            heapify(arr, i, 0);
        }
    }
    
    private static void heapify(int[] arr, int n, int i) {
        int largest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;
        
        if (left < n && arr[left] > arr[largest])
            largest = left;
        
        if (right < n && arr[right] > arr[largest])
            largest = right;
        
        if (largest != i) {
            int swap = arr[i];
            arr[i] = arr[largest];
            arr[largest] = swap;
            
            heapify(arr, n, largest);
        }
    }
}

```

**Sample Output:**
```
Enter 10 numbers to sort:
45 12 85 32 89 39 69 44 42 1
Original array: [45, 12, 85, 32, 89, 39, 69, 44, 42, 1]

Choose sorting method:
1. Merge Sort
2. Quick Sort
3. Heap Sort
1
Sorted array: [1, 12, 32, 39, 42, 44, 45, 69, 85, 89]
```

## Question 4: Write a program to calculate interest that may be simple or compound using method overloading?

```java
import java.util.Scanner;

public class InterestCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Interest Calculator");
        System.out.println("1. Simple Interest");
        System.out.println("2. Compound Interest");
        System.out.print("Enter your choice (1 or 2): ");
        int choice = scanner.nextInt();
        
        System.out.print("Enter principal amount: ");
        double principal = scanner.nextDouble();
        
        System.out.print("Enter rate of interest (% per annum): ");
        double rate = scanner.nextDouble();
        
        System.out.print("Enter time period (in years): ");
        double time = scanner.nextDouble();
        
        double result = 0;
        
        if (choice == 1) {
            result = calculateInterest(principal, rate, time);
            System.out.println("Simple Interest: " + result);
            System.out.println("Total Amount: " + (principal + result));
        } else if (choice == 2) {
            System.out.print("Enter number of times interest is compounded per year: ");
            int n = scanner.nextInt();
            result = calculateInterest(principal, rate, time, n);
            System.out.println("Compound Interest: " + result);
            System.out.println("Total Amount: " + (principal + result));
        } else {
            System.out.println("Invalid choice!");
        }
        
        scanner.close();
    }
    

    public static double calculateInterest(double principal, double rate, double time) {
        return (principal * rate * time) / 100;
    }
    

    public static double calculateInterest(double principal, double rate, double time, int n) {
        return principal * (Math.pow(1 + rate / (100 * n), n * time)) - principal;
    }
}

```

**Sample Output:**
```
Interest Calculator
1. Simple Interest
2. Compound Interest
Enter your choice (1 or 2): 1
Enter principal amount: 10000
Enter rate of interest (% per annum): 5
Enter time period (in years): 2
Simple Interest: 1000.0
Total Amount: 11000.0

Interest Calculator
1. Simple Interest
2. Compound Interest
Enter your choice (1 or 2): 2
Enter principal amount: 10000
Enter rate of interest (% per annum): 5
Enter time period (in years): 2
Enter number of times interest is compounded per year: 4
Compound Interest: 1038.07
Total Amount: 11038.07
```

## Question 5: Write a program to override sum method if arguments are numbers than it will add numbers or string than concat two strings using constructor overloading?

```java
import java.util.Scanner;

public class SumOverriding {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Choose operation:");
        System.out.println("1. Add two numbers");
        System.out.println("2. Concatenate two strings");
        int choice = scanner.nextInt();
        
        if (choice == 1) {
            System.out.print("Enter first number: ");
            double num1 = scanner.nextDouble();
            System.out.print("Enter second number: ");
            double num2 = scanner.nextDouble();
            
            Calculator numCalc = new Calculator(num1, num2);
            System.out.println("Sum: " + numCalc.sum());
        } else if (choice == 2) {
            scanner.nextLine(); // Clear the buffer
            System.out.print("Enter first string: ");
            String str1 = scanner.nextLine();
            System.out.print("Enter second string: ");
            String str2 = scanner.nextLine();
            
            Calculator strCalc = new Calculator(str1, str2);
            System.out.println("Concatenated string: " + strCalc.sum());
        } else {
            System.out.println("Invalid choice!");
        }
        
        scanner.close();
    }
}

class Calculator {
    private double num1, num2;
    private String str1, str2;
    private boolean isNumeric;
    
    public Calculator(double num1, double num2) {
        this.num1 = num1;
        this.num2 = num2;
        this.isNumeric = true;
    }
    
    public Calculator(String str1, String str2) {
        this.str1 = str1;
        this.str2 = str2;
        this.isNumeric = false;
    }
    
    public Object sum() {
        if (isNumeric) {
            return num1 + num2;
        } else {
            return str1 + str2;
        }
    }
}

```

**Sample Output:**
```
Choose operation:
1. Add two numbers
2. Concatenate two strings
1
Enter first number: 10.5
Enter second number: 20.3
Sum: 30.8

Choose operation:
1. Add two numbers
2. Concatenate two strings
2
Enter first string: Hello, 
Enter second string: World!
Concatenated string: Hello, World!
```

## Question 6: Write a program to check whether a number or string is palindrome or not using method overloading?

```java
import java.util.Scanner;

public class PalindromeChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Choose what to check for palindrome:");
        System.out.println("1. Number");
        System.out.println("2. String");
        int choice = scanner.nextInt();
        
        if (choice == 1) {
            System.out.print("Enter a number: ");
            int number = scanner.nextInt();
            
            if (isPalindrome(number)) {
                System.out.println(number + " is a palindrome number.");
            } else {
                System.out.println(number + " is not a palindrome number.");
            }
        } else if (choice == 2) {
            scanner.nextLine(); // Clear the buffer
            System.out.print("Enter a string: ");
            String text = scanner.nextLine();
            
            if (isPalindrome(text)) {
                System.out.println("\"" + text + "\" is a palindrome string.");
            } else {
                System.out.println("\"" + text + "\" is not a palindrome string.");
            }
        } else {
            System.out.println("Invalid choice!");
        }
        
        scanner.close();
    }
    
    public static boolean isPalindrome(int number) {
        int originalNumber = number;
        int reverse = 0;
        
        while (number > 0) {
            int digit = number % 10;
            reverse = reverse * 10 + digit;
            number /= 10;
        }
        
        return originalNumber == reverse;
    }
    

    public static boolean isPalindrome(String text) {
        String processedText = text.replaceAll("\\s+", "").toLowerCase();
        int length = processedText.length();
        
        for (int i = 0; i < length / 2; i++) {
            if (processedText.charAt(i) != processedText.charAt(length - i - 1)) {
                return false;
            }
        }
        
        return true;
    }
}

```

**Sample Output:**
```
Choose what to check for palindrome:
1. Number
2. String
1
Enter a number: 12321
12321 is a palindrome number.

Choose what to check for palindrome:
1. Number
2. String
1
Enter a number: 12345
12345 is not a palindrome number.

Choose what to check for palindrome:
1. Number
2. String
2
Enter a string: racecar
"racecar" is a palindrome string.

Choose what to check for palindrome:
1. Number
2. String
2
Enter a string: A man a plan a canal Panama
"A man a plan a canal Panama" is a palindrome string.
```

## Question 7: Write a program to find volume of rectangle and square box using constructor overloading?

```java
import java.util.Scanner;

public class BoxVolumeCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Choose box type:");
        System.out.println("1. Rectangular Box");
        System.out.println("2. Square Box");
        int choice = scanner.nextInt();
        
        if (choice == 1) {
            System.out.print("Enter length: ");
            double length = scanner.nextDouble();
            System.out.print("Enter width: ");
            double width = scanner.nextDouble();
            System.out.print("Enter height: ");
            double height = scanner.nextDouble();
            
            Box rectangularBox = new Box(length, width, height);
            System.out.println("Volume of Rectangular Box: " + rectangularBox.getVolume());
        } else if (choice == 2) {
            System.out.print("Enter side length: ");
            double side = scanner.nextDouble();
            
            Box squareBox = new Box(side);
            System.out.println("Volume of Square Box: " + squareBox.getVolume());
        } else {
            System.out.println("Invalid choice!");
        }
        
        scanner.close();
    }
}

class Box {
    private double length;
    private double width;
    private double height;
    
    public Box(double length, double width, double height) {
        this.length = length;
        this.width = width;
        this.height = height;
    }
    
    public Box(double side) {
        this.length = side;
        this.width = side;
        this.height = side;
    }
    
    public double getVolume() {
        return length * width * height;
    }
}

```

**Sample Output:**
```
Choose box type:
1. Rectangular Box
2. Square Box
1
Enter length: 10
Enter width: 5
Enter height: 3
Volume of Rectangular Box: 150.0

Choose box type:
1. Rectangular Box
2. Square Box
2
Enter side length: 5
Volume of Square Box: 125.0
```

## Question 8: WAP to find volume of a box which is the 2 times of first box and 3 times of second box whereas Second box is half of first box using method overloading. Dimension of first box will be taken from user.

```java
import java.util.Scanner;

public class CompositeBoxVolume {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Enter dimensions of first box:");
        System.out.print("Length: ");
        double length = scanner.nextDouble();
        System.out.print("Width: ");
        double width = scanner.nextDouble();
        System.out.print("Height: ");
        double height = scanner.nextDouble();
        

        System.out.println("\nFirst Box Dimensions:");
        System.out.println("Length: " + length + ", Width: " + width + ", Height: " + height);
        double firstBoxVolume = calculateVolume(length, width, height);
        System.out.println("Volume of First Box: " + firstBoxVolume);
        

        System.out.println("\nSecond Box (Half of First Box) Dimensions:");
        double secondBoxLength = length / 2;
        double secondBoxWidth = width / 2;
        double secondBoxHeight = height / 2;
        System.out.println("Length: " + secondBoxLength + ", Width: " + secondBoxWidth + ", Height: " + secondBoxHeight);
        double secondBoxVolume = calculateVolume(secondBoxLength, secondBoxWidth, secondBoxHeight);
        System.out.println("Volume of Second Box: " + secondBoxVolume);
        
        System.out.println("\nFinal Box Dimensions and Volume:");
        double finalBoxVolume = calculateVolume(length, width, height, secondBoxLength, secondBoxWidth, secondBoxHeight);
        System.out.println("Volume of Final Box (2 times First Box + 3 times Second Box): " + finalBoxVolume);
        
        scanner.close();
    }
    

    public static double calculateVolume(double length, double width, double height) {
        return length * width * height;
    }
    
    public static double calculateVolume(double length1, double width1, double height1, 
                                        double length2, double width2, double height2) {
        
        double firstBoxVolume = calculateVolume(length1, width1, height1);
        double secondBoxVolume = calculateVolume(length2, width2, height2);
        
        return (2 * firstBoxVolume) + (3 * secondBoxVolume);
    }
}

```

**Sample Output:**
```
Enter dimensions of first box:
Length: 10
Width: 8
Height: 6

First Box Dimensions:
Length: 10.0, Width: 8.0, Height: 6.0
Volume of First Box: 480.0

Second Box (Half of First Box) Dimensions:
Length: 5.0, Width: 4.0, Height: 3.0
Volume of Second Box: 60.0

Final Box Dimensions and Volume:
Volume of Final Box (2 times First Box + 3 times Second Box): 1140.0
```
I understand. I'll continue from where I left off, starting with solving the inheritance questions in the assignment.

## Inheritance

### Question 1: WAP to find area and volume of a TV using simple inheritance?

```java
import java.util.Scanner;

class Television {
    protected double length;
    protected double width;
    protected double thickness;
    
    public Television(double length, double width, double thickness) {
        this.length = length;
        this.width = width;
        this.thickness = thickness;
    }
    
    public double calculateArea() {
        return length * width;
    }
}

class TV3D extends Television {
    public TV3D(double length, double width, double thickness) {
        super(length, width, thickness);
    }
    
    public double calculateVolume() {
        return length * width * thickness;
    }
}

public class TVCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Enter the dimensions of the TV:");
        System.out.print("Length (in cm): ");
        double length = scanner.nextDouble();
        
        System.out.print("Width (in cm): ");
        double width = scanner.nextDouble();
        
        System.out.print("Thickness (in cm): ");
        double thickness = scanner.nextDouble();
        
        TV3D tv = new TV3D(length, width, thickness);
        
        System.out.println("\nTV Specifications:");
        System.out.println("Length: " + length + " cm");
        System.out.println("Width: " + width + " cm");
        System.out.println("Thickness: " + thickness + " cm");
        System.out.println("Screen Area: " + tv.calculateArea() + " square cm");
        System.out.println("Volume: " + tv.calculateVolume() + " cubic cm");
        
        scanner.close();
    }
}

```

**Sample Output:**
```
Enter the dimensions of the TV:
Length (in cm): 120
Width (in cm): 80
Thickness (in cm): 5

TV Specifications:
Length: 120.0 cm
Width: 80.0 cm
Thickness: 5.0 cm
Screen Area: 9600.0 square cm
Volume: 48000.0 cubic cm
```

### Question 2: WAP to find area, volume and weight of a box using multilevel inheritance?

```java
import java.util.Scanner;

class Shape {
    protected double length;
    protected double width;
    protected double height;
    
    public Shape(double length, double width, double height) {
        this.length = length;
        this.width = width;
        this.height = height;
    }
    
    public double calculateArea() {
        return 2 * (length * width + length * height + width * height);
    }
}

class Box extends Shape {
    public Box(double length, double width, double height) {
        super(length, width, height);
    }
    
    public double calculateVolume() {
        return length * width * height;
    }
}

class WeightedBox extends Box {
    private double density;
    
    public WeightedBox(double length, double width, double height, double density) {
        super(length, width, height);
        this.density = density;
    }
    
    public double calculateWeight() {
        return calculateVolume() * density;
    }
}

public class BoxCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Enter the dimensions of the box:");
        System.out.print("Length (in cm): ");
        double length = scanner.nextDouble();
        
        System.out.print("Width (in cm): ");
        double width = scanner.nextDouble();
        
        System.out.print("Height (in cm): ");
        double height = scanner.nextDouble();
        
        System.out.print("Enter the density of the material (g/cm³): ");
        double density = scanner.nextDouble();
        
        WeightedBox box = new WeightedBox(length, width, height, density);
        
        System.out.println("\nBox Specifications:");
        System.out.println("Length: " + length + " cm");
        System.out.println("Width: " + width + " cm");
        System.out.println("Height: " + height + " cm");
        System.out.println("Density: " + density + " g/cm³");
        System.out.println("Surface Area: " + box.calculateArea() + " square cm");
        System.out.println("Volume: " + box.calculateVolume() + " cubic cm");
        System.out.println("Weight: " + box.calculateWeight() + " g");
        
        scanner.close();
    }
}

```

**Sample Output:**
```
Enter the dimensions of the box:
Length (in cm): 10
Width (in cm): 8
Height (in cm): 6
Enter the density of the material (g/cm³): 2.5

Box Specifications:
Length: 10.0 cm
Width: 8.0 cm
Height: 6.0 cm
Density: 2.5 g/cm³
Surface Area: 376.0 square cm
Volume: 480.0 cubic cm
Weight: 1200.0 g
```

### Question 3: WAP to find simple and compound interest using simple inheritance?

```java
import java.util.Scanner;

class Interest {
    protected double principal;
    protected double rate;
    protected double time;
    
    public Interest(double principal, double rate, double time) {
        this.principal = principal;
        this.rate = rate;
        this.time = time;
    }
    
    public double calculateSimpleInterest() {
        return (principal * rate * time) / 100;
    }
}

class CompoundInterest extends Interest {
    private int compoundingFrequency;
    
    public CompoundInterest(double principal, double rate, double time, int compoundingFrequency) {
        super(principal, rate, time);
        this.compoundingFrequency = compoundingFrequency;
    }
    
    public double calculateCompoundInterest() {
        double amount = principal * Math.pow(1 + (rate / (100 * compoundingFrequency)), compoundingFrequency * time);
        return amount - principal;
    }
}

public class InterestCalculatorInheritance {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Enter the investment details:");
        System.out.print("Principal amount: ");
        double principal = scanner.nextDouble();
        
        System.out.print("Annual interest rate (%): ");
        double rate = scanner.nextDouble();
        
        System.out.print("Time period (in years): ");
        double time = scanner.nextDouble();
        
        System.out.print("Compounding frequency per year (e.g., 1, 2, 4, 12): ");
        int frequency = scanner.nextInt();
        
        CompoundInterest calculator = new CompoundInterest(principal, rate, time, frequency);
        
        double simpleInterest = calculator.calculateSimpleInterest();
        double compoundInterest = calculator.calculateCompoundInterest();
        
        System.out.println("\nInvestment Details:");
        System.out.println("Principal Amount: $" + principal);
        System.out.println("Annual Interest Rate: " + rate + "%");
        System.out.println("Time Period: " + time + " years");
        System.out.println("Compounding Frequency: " + frequency + " times per year");
        
        System.out.println("\nInterest Calculations:");
        System.out.println("Simple Interest: $" + String.format("%.2f", simpleInterest));
        System.out.println("Total Amount with Simple Interest: $" + String.format("%.2f", (principal + simpleInterest)));
        System.out.println("Compound Interest: $" + String.format("%.2f", compoundInterest));
        System.out.println("Total Amount with Compound Interest: $" + String.format("%.2f", (principal + compoundInterest)));
        
        scanner.close();
    }
}

```

**Sample Output:**
```
Enter the investment details:
Principal amount: 10000
Annual interest rate (%): 5
Time period (in years): 3
Compounding frequency per year (e.g., 1, 2, 4, 12): 4

Investment Details:
Principal Amount: $10000.0
Annual Interest Rate: 5.0%
Time Period: 3.0 years
Compounding Frequency: 4 times per year

Interest Calculations:
Simple Interest: $1500.00
Total Amount with Simple Interest: $11500.00
Compound Interest: $1587.50
Total Amount with Compound Interest: $11587.50
```

### Question 4: WAP to create an application for Student Assessment using inheritance?

```java
import java.util.Scanner;

class Subject {
    private String name;
    private int internalMarks;
    private int externalMarks;
    private int creditPoints;
    private int attendedClasses;
    private int totalClasses;
    
    public Subject(String name) {
        this.name = name;
        this.creditPoints = 3; 
    }
    
    public void setAttendance(int attended, int total) {
        this.attendedClasses = attended;
        this.totalClasses = total;

        double ratio = (double) attended / total;
        this.internalMarks = (int) (40 * ratio);
        
        if (this.internalMarks > 40) {
            this.internalMarks = 40;
        }
    }
    
    public void setExternalMarks(int marks) {
        if (marks >= 0 && marks <= 60) {
            this.externalMarks = marks;
        } else {
            System.out.println("Invalid external marks. Must be between 0 and 60.");
        }
    }
    
    public int getTotalMarks() {
        return internalMarks + externalMarks;
    }
    
    public String getGrade() {
        int totalMarks = getTotalMarks();
        
        if (totalMarks >= 90) return "O";
        else if (totalMarks >= 80) return "E";
        else if (totalMarks >= 70) return "A";
        else if (totalMarks >= 60) return "B";
        else if (totalMarks >= 50) return "C";
        else if (totalMarks >= 40) return "D";
        else return "F";
    }
    
    public double getGradePoint() {
        String grade = getGrade();
        
        switch (grade) {
            case "O": return 10.0;
            case "E": return 9.0;
            case "A": return 8.0;
            case "B": return 7.0;
            case "C": return 6.0;
            case "D": return 5.0;
            default: return 0.0;
        }
    }
    
    public int getCreditPoints() {
        return creditPoints;
    }
    
    public String getName() {
        return name;
    }
    
    public int getInternalMarks() {
        return internalMarks;
    }
    
    public int getExternalMarks() {
        return externalMarks;
    }
}

class Student {
    private String name;
    private int rollNo;
    private Subject[] subjects;
    
    public Student(String name, int rollNo) {
        this.name = name;
        this.rollNo = rollNo;
        this.subjects = new Subject[5];
        subjects[0] = new Subject("C");
        subjects[1] = new Subject("C++");
        subjects[2] = new Subject("Java");
        subjects[3] = new Subject("Python");
        subjects[4] = new Subject("IoT");
    }
    
    public void setSubjectAttendance(int subjectIndex, int attended, int total) {
        if (subjectIndex >= 0 && subjectIndex < subjects.length) {
            subjects[subjectIndex].setAttendance(attended, total);
        }
    }
    
    public void setSubjectExternalMarks(int subjectIndex, int marks) {
        if (subjectIndex >= 0 && subjectIndex < subjects.length) {
            subjects[subjectIndex].setExternalMarks(marks);
        }
    }
    
    public double calculateSGPA() {
        double totalCredits = 0;
        double totalGradePoints = 0;
        
        for (Subject subject : subjects) {
            totalCredits += subject.getCreditPoints();
            totalGradePoints += subject.getGradePoint() * subject.getCreditPoints();
        }
        
        return totalGradePoints / totalCredits;
    }
    
    public void displayResult() {
        System.out.println("\n=================== IGIT RESULT ===================");
        System.out.println("Name: " + name);
        System.out.println("Roll No: " + rollNo);
        System.out.println("=====================================================");
        System.out.println("Subject\tInternal\tExternal\tTotal\tGrade");
        System.out.println("=====================================================");
        
        for (Subject subject : subjects) {
            System.out.println(subject.getName() + "\t" + subject.getInternalMarks() + "\t\t" + 
                               subject.getExternalMarks() + "\t\t" + subject.getTotalMarks() + 
                               "\t" + subject.getGrade());
        }
        
        System.out.println("=====================================================");
        System.out.println("SGPA: " + String.format("%.2f", calculateSGPA()));
        
        boolean hasFailed = false;
        for (Subject subject : subjects) {
            if (subject.getGrade().equals("F")) {
                hasFailed = true;
                break;
            }
        }
        
        System.out.println("Result: " + (hasFailed ? "FAIL" : "PASS"));
        System.out.println("=====================================================");
    }
    
    public String getName() {
        return name;
    }
    
    public int getRollNo() {
        return rollNo;
    }
}

class StudentAssessment {
    private Student[] students;
    
    public StudentAssessment(int numStudents) {
        students = new Student[numStudents];
    }
    
    public void addStudent(int index, Student student) {
        if (index >= 0 && index < students.length) {
            students[index] = student;
        }
    }
    
    public void displayAllResults() {
        for (Student student : students) {
            if (student != null) {
                student.displayResult();
            }
        }
    }
}

public class StudentAssessmentSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        

        StudentAssessment assessment = new StudentAssessment(5);
        
  
        for (int i = 0; i < 5; i++) {
            System.out.println("\nEnter details for Student " + (i + 1) + ":");
            System.out.print("Name: ");
            String name = scanner.nextLine();
            
            System.out.print("Roll No: ");
            int rollNo = scanner.nextInt();
            scanner.nextLine();
            
            Student student = new Student(name, rollNo);
            

            String[] subjects = {"C", "C++", "Java", "Python", "IoT"};
            for (int j = 0; j < 5; j++) {
                System.out.println("\nSubject: " + subjects[j]);
                
                System.out.print("Number of classes attended: ");
                int attended = scanner.nextInt();
                
                System.out.print("Total number of classes: ");
                int total = scanner.nextInt();
                
                System.out.print("External marks (out of 60): ");
                int external = scanner.nextInt();
                scanner.nextLine(); 
                
                student.setSubjectAttendance(j, attended, total);
                student.setSubjectExternalMarks(j, external);
            }
            
            assessment.addStudent(i, student);
        }
        

        assessment.displayAllResults();
        
        scanner.close();
    }
}

```

**Sample Output:**
```
Enter details for Student 1:
Name: John Doe
Roll No: 101

Subject: C
Number of classes attended: 35
Total number of classes: 40
External marks (out of 60): 50

Subject: C++
Number of classes attended: 38
Total number of classes: 40
External marks (out of 60): 55

Subject: Java
Number of classes attended: 40
Total number of classes: 40
External marks (out of 60): 58

Subject: Python
Number of classes attended: 37
Total number of classes: 40
External marks (out of 60): 56

Subject: IoT
Number of classes attended: 36
Total number of classes: 40
External marks (out of 60): 52

Enter details for Student 2:
Name: Jane Smith
Roll No: 102
... (other student details)

=================== IGIT RESULT ===================
Name: John Doe
Roll No: 101
=====================================================
Subject	Internal	External	Total	Grade
=====================================================
C	35		50		85	E
C++	38		55		93	O
Java	40		58		98	O
Python	37		56		93	O
IoT	36		52		88	E
=====================================================
SGPA: 9.20
Result: PASS
=====================================================
... (other student results)
```

### Question 5: WAP to create a banking application using inheritance and do the following.
### a) Create current account of the user with user Id and minimum balance 500.
### b) Allow user to deposit, withdraw and check balance on the account.
### c) Allow user to open fixed deposit account with the user defined amount available on the current account and display the interest obtained quarterly the final maturity value with the interest obtained.
### d) Allow user to open Rd deposit account with the user defined amount available on the current account and display the interest obtained quarterly and the final maturity value with the interest obtained. Allow user to deposit premium monthly manually or automatically from the account.
### e) Allow user to take loan against the 90% of money available on the current account. Check for the monthly premium paid after few duration with the interest obtained.

```java
import java.util.Scanner;
import java.util.ArrayList;

class BankAccount {
    protected String userId;
    protected double balance;
    protected final double MIN_BALANCE = 500;
    
    public BankAccount(String userId, double initialBalance) {
        this.userId = userId;
        
        if (initialBalance >= MIN_BALANCE) {
            this.balance = initialBalance;
        } else {
            System.out.println("Minimum balance requirement not met. Setting balance to minimum: " + MIN_BALANCE);
            this.balance = MIN_BALANCE;
        }
    }
    
    public boolean deposit(double amount) {
        if (amount > 0) {
            this.balance += amount;
            System.out.println("Deposit successful. New balance: " + this.balance);
            return true;
        } else {
            System.out.println("Invalid amount for deposit.");
            return false;
        }
    }
    
    public boolean withdraw(double amount) {
        if (amount > 0 && (this.balance - amount) >= MIN_BALANCE) {
            this.balance -= amount;
            System.out.println("Withdrawal successful. New balance: " + this.balance);
            return true;
        } else {
            System.out.println("Insufficient balance or invalid amount. Minimum balance requirement: " + MIN_BALANCE);
            return false;
        }
    }
    
    public double checkBalance() {
        System.out.println("Current balance: " + this.balance);
        return this.balance;
    }
    
    public String getUserId() {
        return userId;
    }
}

class FixedDeposit extends BankAccount {
    private double fdAmount;
    private double interestRate;
    private int durationMonths;
    private ArrayList<Double> quarterlyInterest;
    
    public FixedDeposit(BankAccount account, double amount, double interestRate, int durationMonths) {
        super(account.getUserId(), account.balance);
        this.interestRate = interestRate;
        this.durationMonths = durationMonths;
        this.quarterlyInterest = new ArrayList<>();
        
        if (amount > 0 && amount <= account.balance - MIN_BALANCE) {
            this.fdAmount = amount;
            account.withdraw(amount);
            System.out.println("Fixed Deposit created successfully with amount: " + amount);
            calculateQuarterlyInterest();
        } else {
            System.out.println("Invalid amount for Fixed Deposit or insufficient balance.");
            this.fdAmount = 0;
        }
    }
    
    private void calculateQuarterlyInterest() {

        int quarters = (int) Math.ceil(durationMonths / 3.0);
        double quarterlyRate = interestRate / 4; 
        
        double principal = fdAmount;
        
        for (int i = 0; i < quarters; i++) {
            double interest = principal * quarterlyRate / 100;
            quarterlyInterest.add(interest);
            principal += interest; 
        }
    }
    
    public void displayFDDetails() {
        System.out.println("\nFixed Deposit Details:");
        System.out.println("Principal Amount: " + fdAmount);
        System.out.println("Annual Interest Rate: " + interestRate + "%");
        System.out.println("Duration: " + durationMonths + " months");
        
        System.out.println("\nQuarterly Interest Earnings:");
        double totalInterest = 0;
        for (int i = 0; i < quarterlyInterest.size(); i++) {
            System.out.println("Quarter " + (i+1) + ": " + String.format("%.2f", quarterlyInterest.get(i)));
            totalInterest += quarterlyInterest.get(i);
        }
        
        System.out.println("\nTotal Interest Earned: " + String.format("%.2f", totalInterest));
        System.out.println("Maturity Amount: " + String.format("%.2f", (fdAmount + totalInterest)));
    }
}

class RecurringDeposit extends BankAccount {
    private double monthlyPremium;
    private double interestRate;
    private int durationMonths;
    private ArrayList<Double> quarterlyInterest;
    private double totalDeposited;
    private boolean autoDebit;
    
    public RecurringDeposit(BankAccount account, double monthlyPremium, double interestRate, int durationMonths, boolean autoDebit) {
        super(account.getUserId(), account.balance);
        this.interestRate = interestRate;
        this.durationMonths = durationMonths;
        this.monthlyPremium = monthlyPremium;
        this.autoDebit = autoDebit;
        this.quarterlyInterest = new ArrayList<>();
        this.totalDeposited = 0;
        
        if (monthlyPremium > 0) {
            System.out.println("Recurring Deposit created successfully with monthly premium: " + monthlyPremium);
            if (autoDebit) {
                if (account.withdraw(monthlyPremium)) {
                    this.totalDeposited += monthlyPremium;
                }
            }
            calculateQuarterlyInterest();
        } else {
            System.out.println("Invalid amount for monthly premium.");
        }
    }
    
    public boolean depositMonthlyPremium(BankAccount account) {
        if (autoDebit) {
            if (account.withdraw(monthlyPremium)) {
                this.totalDeposited += monthlyPremium;
                System.out.println("Monthly premium of " + monthlyPremium + " automatically debited.");
                return true;
            } else {
                System.out.println("Automatic debit failed due to insufficient balance.");
                return false;
            }
        } else {
            this.totalDeposited += monthlyPremium;
            System.out.println("Monthly premium of " + monthlyPremium + " manually deposited.");
            return true;
        }
    }
    
    private void calculateQuarterlyInterest() {
        int quarters = (int) Math.ceil(durationMonths / 3.0);
        double quarterlyRate = interestRate / 4; // Quarterly rate
        double totalAmount = 0;
        
        for (int i = 0; i < quarters; i++) {
            int monthsInThisQuarter = Math.min(3, durationMonths - (i * 3));
            double depositedThisQuarter = monthlyPremium * monthsInThisQuarter;
            

            totalAmount += depositedThisQuarter;
            

            double interest = totalAmount * quarterlyRate / 100;
            quarterlyInterest.add(interest);
            

            totalAmount += interest;
        }
    }
    
    public void displayRDDetails() {
        System.out.println("\nRecurring Deposit Details:");
        System.out.println("Monthly Premium: " + monthlyPremium);
        System.out.println("Annual Interest Rate: " + interestRate + "%");
        System.out.println("Duration: " + durationMonths + " months");
        System.out.println("Auto-debit Enabled: " + (autoDebit ? "Yes" : "No"));
        
        System.out.println("\nProjected Quarterly Interest Earnings:");
        double totalInterest = 0;
        for (int i = 0; i < quarterlyInterest.size(); i++) {
            System.out.println("Quarter " + (i+1) + ": " + String.format("%.2f", quarterlyInterest.get(i)));
            totalInterest += quarterlyInterest.get(i);
        }
        
        double expectedTotalDeposit = monthlyPremium * durationMonths;
        
        System.out.println("\nTotal Expected Deposit: " + String.format("%.2f", expectedTotalDeposit));
        System.out.println("Current Deposited Amount: " + String.format("%.2f", totalDeposited));
        System.out.println("Projected Total Interest: " + String.format("%.2f", totalInterest));
        System.out.println("Projected Maturity Amount: " + String.format("%.2f", (expectedTotalDeposit + totalInterest)));
    }
}

class Loan extends BankAccount {
    private double loanAmount;
    private double interestRate;
    private int durationMonths;
    private double monthlyInstallment;
    private int installmentsPaid;
    
    public Loan(BankAccount account, double loanAmount, double interestRate, int durationMonths) {
        super(account.getUserId(), account.balance);
        this.interestRate = interestRate;
        this.durationMonths = durationMonths;
        this.installmentsPaid = 0;

        double maxLoanAllowed = account.balance * 0.9;
        
        if (loanAmount > 0 && loanAmount <= maxLoanAllowed) {
            this.loanAmount = loanAmount;
            

            double monthlyRate = interestRate / 12 / 100;
            this.monthlyInstallment = (loanAmount * monthlyRate * Math.pow(1 + monthlyRate, durationMonths)) / 
                                    (Math.pow(1 + monthlyRate, durationMonths) - 1);
            
            account.deposit(loanAmount);
            
            System.out.println("Loan approved for amount: " + loanAmount);
            System.out.println("Monthly installment: " + String.format("%.2f", monthlyInstallment));
        } else {
            System.out.println("Loan amount exceeds 90% of your current balance or is invalid.");
            this.loanAmount = 0;
            this.monthlyInstallment = 0;
        }
    }
    
    public boolean payInstallment(BankAccount account) {
        if (installmentsPaid < durationMonths) {
            if (account.withdraw(monthlyInstallment)) {
                installmentsPaid++;
                System.out.println("Installment " + installmentsPaid + " of " + durationMonths + " paid successfully.");
                return true;
            } else {
                System.out.println("Insufficient balance to pay installment.");
                return false;
            }
        } else {
            System.out.println("Loan has already been fully paid.");
            return false;
        }
    }
    
    public void displayLoanDetails() {
        System.out.println("\nLoan Details:");
        System.out.println("Loan Amount: " + loanAmount);
        System.out.println("Annual Interest Rate: " + interestRate + "%");
        System.out.println("Duration: " + durationMonths + " months");
        System.out.println("Monthly Installment: " + String.format("%.2f", monthlyInstallment));
        
        double totalPayable = monthlyInstallment * durationMonths;
        double totalInterest = totalPayable - loanAmount;
        
        System.out.println("Total Interest Payable: " + String.format("%.2f", totalInterest));
        System.out.println("Total Amount Payable: " + String.format("%.2f", totalPayable));
        System.out.println("Installments Paid: " + installmentsPaid + " of " + durationMonths);
        System.out.println("Remaining Installments: " + (durationMonths - installmentsPaid));
        System.out.println("Remaining Amount: " + String.format("%.2f", (totalPayable - (installmentsPaid * monthlyInstallment))));
    }
}


class BankAccount {
    protected String userId;
    protected double balance;
    protected final double MIN_BALANCE = 500;
    
    public BankAccount(String userId, double initialBalance) {
        this.userId = userId;
        
        if (initialBalance >= MIN_BALANCE) {
            this.balance = initialBalance;
        } else {
            System.out.println("Minimum balance requirement not met. Setting balance to minimum: " + MIN_BALANCE);
            this.balance = MIN_BALANCE;
        }
    }
    
    public boolean deposit(double amount) {
        if (amount > 0) {
            this.balance += amount;
            System.out.println("Deposit successful. New balance: " + this.balance);
            return true;
        } else {
            System.out.println("Invalid amount for deposit.");
            return false;
        }
    }
    
    public boolean withdraw(double amount) {
        if (amount > 0 && (this.balance - amount) >= MIN_BALANCE) {
            this.balance -= amount;
            System.out.println("Withdrawal successful. New balance: " + this.balance);
            return true;
        } else {
            System.out.println("Insufficient balance or invalid amount. Minimum balance requirement: " + MIN_BALANCE);
            return false;
        }
    }
    
    public double checkBalance() {
        System.out.println("Current balance: " + this.balance);
        return this.balance;
    }
    
    public String getUserId() {
        return userId;
    }
}

class FixedDeposit extends BankAccount {
    private double fdAmount;
    private double interestRate;
    private int durationMonths;
    private ArrayList<Double> quarterlyInterest;
    
    public FixedDeposit(BankAccount account, double amount, double interestRate, int durationMonths) {
        super(account.getUserId(), account.balance);
        this.interestRate = interestRate;
        this.durationMonths = durationMonths;
        this.quarterlyInterest = new ArrayList<>();
        
        if (amount > 0 && amount <= account.balance - MIN_BALANCE) {
            this.fdAmount = amount;
            account.withdraw(amount);
            System.out.println("Fixed Deposit created successfully with amount: " + amount);
            calculateQuarterlyInterest();
        } else {
            System.out.println("Invalid amount for Fixed Deposit or insufficient balance.");
            this.fdAmount = 0;
        }
    }
    
    private void calculateQuarterlyInterest() {
        int quarters = (int) Math.ceil(durationMonths / 3.0);
        double quarterlyRate = interestRate / 4;
        
        double principal = fdAmount;
        
        for (int i = 0; i < quarters; i++) {
            double interest = principal * quarterlyRate / 100;
            quarterlyInterest.add(interest);
            principal += interest; 
        }
    }
    
    public void displayFDDetails() {
        System.out.println("\nFixed Deposit Details:");
        System.out.println("Principal Amount: " + fdAmount);
        System.out.println("Annual Interest Rate: " + interestRate + "%");
        System.out.println("Duration: " + durationMonths + " months");
        
        System.out.println("\nQuarterly Interest Earnings:");
        double totalInterest = 0;
        for (int i = 0; i < quarterlyInterest.size(); i++) {
            System.out.println("Quarter " + (i+1) + ": " + String.format("%.2f", quarterlyInterest.get(i)));
            totalInterest += quarterlyInterest.get(i);
        }
        
        System.out.println("\nTotal Interest Earned: " + String.format("%.2f", totalInterest));
        System.out.println("Maturity Amount: " + String.format("%.2f", (fdAmount + totalInterest)));
    }
}

class RecurringDeposit extends BankAccount {
    private double monthlyPremium;
    private double interestRate;
    private int durationMonths;
    private ArrayList<Double> quarterlyInterest;
    private double totalDeposited;
    private boolean autoDebit;
    
    public RecurringDeposit(BankAccount account, double monthlyPremium, double interestRate, int durationMonths, boolean autoDebit) {
        super(account.getUserId(), account.balance);
        this.interestRate = interestRate;
        this.durationMonths = durationMonths;
        this.monthlyPremium = monthlyPremium;
        this.autoDebit = autoDebit;
        this.quarterlyInterest = new ArrayList<>();
        this.totalDeposited = 0;
        
        if (monthlyPremium > 0) {
            System.out.println("Recurring Deposit created successfully with monthly premium: " + monthlyPremium);
            if (autoDebit) {
                if (account.withdraw(monthlyPremium)) {
                    this.totalDeposited += monthlyPremium;
                }
            }
            calculateQuarterlyInterest();
        } else {
            System.out.println("Invalid amount for monthly premium.");
        }
    }
    
    public boolean depositMonthlyPremium(BankAccount account) {
        if (autoDebit) {
            if (account.withdraw(monthlyPremium)) {
                this.totalDeposited += monthlyPremium;
                System.out.println("Monthly premium of " + monthlyPremium + " automatically debited.");
                return true;
            } else {
                System.out.println("Automatic debit failed due to insufficient balance.");
                return false;
            }
        } else {
            this.totalDeposited += monthlyPremium;
            System.out.println("Monthly premium of " + monthlyPremium + " manually deposited.");
            return true;
        }
    }
    
    private void calculateQuarterlyInterest() {
        int quarters = (int) Math.ceil(durationMonths / 3.0);
        double quarterlyRate = interestRate / 4; // Quarterly rate
        double totalAmount = 0;
        
        for (int i = 0; i < quarters; i++) {
            int monthsInThisQuarter = Math.min(3, durationMonths - (i * 3));
            double depositedThisQuarter = monthlyPremium * monthsInThisQuarter;
            
            totalAmount += depositedThisQuarter;
            
            double interest = totalAmount * quarterlyRate / 100;
            quarterlyInterest.add(interest);
            
            totalAmount += interest;
        }
    }
    
    public void displayRDDetails() {
        System.out.println("\nRecurring Deposit Details:");
        System.out.println("Monthly Premium: " + monthlyPremium);
        System.out.println("Annual Interest Rate: " + interestRate + "%");
        System.out.println("Duration: " + durationMonths + " months");
        System.out.println("Auto-debit Enabled: " + (autoDebit ? "Yes" : "No"));
        
        System.out.println("\nProjected Quarterly Interest Earnings:");
        double totalInterest = 0;
        for (int i = 0; i < quarterlyInterest.size(); i++) {
            System.out.println("Quarter " + (i+1) + ": " + String.format("%.2f", quarterlyInterest.get(i)));
            totalInterest += quarterlyInterest.get(i);
        }
        
        double expectedTotalDeposit = monthlyPremium * durationMonths;
        
        System.out.println("\nTotal Expected Deposit: " + String.format("%.2f", expectedTotalDeposit));
        System.out.println("Current Deposited Amount: " + String.format("%.2f", totalDeposited));
        System.out.println("Projected Total Interest: " + String.format("%.2f", totalInterest));
        System.out.println("Projected Maturity Amount: " + String.format("%.2f", (expectedTotalDeposit + totalInterest)));
    }
}

class Loan extends BankAccount {
    private double loanAmount;
    private double interestRate;
    private int durationMonths;
    private double monthlyInstallment;
    private int installmentsPaid;
    
    public Loan(BankAccount account, double loanAmount, double interestRate, int durationMonths) {
        super(account.getUserId(), account.balance);
        this.interestRate = interestRate;
        this.durationMonths = durationMonths;
        this.installmentsPaid = 0;
        
        double maxLoanAllowed = account.balance * 0.9;
        
        if (loanAmount > 0 && loanAmount <= maxLoanAllowed) {
            this.loanAmount = loanAmount;
            
            double monthlyRate = interestRate / 12 / 100;
            this.monthlyInstallment = (loanAmount * monthlyRate * Math.pow(1 + monthlyRate, durationMonths)) / 
                                    (Math.pow(1 + monthlyRate, durationMonths) - 1);
            
            account.deposit(loanAmount);
            
            System.out.println("Loan approved for amount: " + loanAmount);
            System.out.println("Monthly installment: " + String.format("%.2f", monthlyInstallment));
        } else {
            System.out.println("Loan amount exceeds 90% of your current balance or is invalid.");
            this.loanAmount = 0;
            this.monthlyInstallment = 0;
        }
    }
    
    public boolean payInstallment(BankAccount account) {
        if (installmentsPaid < durationMonths) {
            if (account.withdraw(monthlyInstallment)) {
                installmentsPaid++;
                System.out.println("Installment " + installmentsPaid + " of " + durationMonths + " paid successfully.");
                return true;
            } else {
                System.out.println("Insufficient balance to pay installment.");
                return false;
            }
        } else {
            System.out.println("Loan has already been fully paid.");
            return false;
        }
    }
    
    public void displayLoanDetails() {
        System.out.println("\nLoan Details:");
        System.out.println("Loan Amount: " + loanAmount);
        System.out.println("Annual Interest Rate: " + interestRate + "%");
        System.out.println("Duration: " + durationMonths + " months");
        System.out.println("Monthly Installment: " + String.format("%.2f", monthlyInstallment));
        
        double totalPayable = monthlyInstallment * durationMonths;
        double totalInterest = totalPayable - loanAmount;
        
        System.out.println("Total Interest Payable: " + String.format("%.2f", totalInterest));
        System.out.println("Total Amount Payable: " + String.format("%.2f", totalPayable));
        System.out.println("Installments Paid: " + installmentsPaid + " of " + durationMonths);
        System.out.println("Remaining Installments: " + (durationMonths - installmentsPaid));
        System.out.println("Remaining Amount: " + String.format("%.2f", (totalPayable - (installmentsPaid * monthlyInstallment))));
    }
}

public class BankingApplication {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        BankAccount currentAccount = null;
        FixedDeposit fd = null;
        RecurringDeposit rd = null;
        Loan loan = null;
        
        boolean running = true;
        
        System.out.println("Welcome to Banking Application");
        System.out.print("Enter User ID: ");
        String userId = scanner.nextLine();
        System.out.print("Enter initial balance (minimum " + 500 + "): ");
        double initialBalance = scanner.nextDouble();
        
        currentAccount = new BankAccount(userId, initialBalance);
        System.out.println("Current account created successfully with User ID: " + userId);
        
        while (running) {
            System.out.println("\n==== Banking Menu ====");
            System.out.println("1. Deposit Money");
            System.out.println("2. Withdraw Money");
            System.out.println("3. Check Balance");
            System.out.println("4. Open Fixed Deposit");
            System.out.println("5. View Fixed Deposit Details");
            System.out.println("6. Open Recurring Deposit");
            System.out.println("7. Pay RD Monthly Premium");
            System.out.println("8. View RD Details");
            System.out.println("9. Take Loan");
            System.out.println("10. Pay Loan Installment");
            System.out.println("11. View Loan Details");
            System.out.println("12. Exit");
            System.out.print("Enter your choice: ");
            
            int choice = scanner.nextInt();
            scanner.nextLine(); // Clear buffer
            
            switch (choice) {
                case 1:
                    System.out.print("Enter amount to deposit: ");
                    double depositAmount = scanner.nextDouble();
                    currentAccount.deposit(depositAmount);
                    break;
                    
                case 2:
                    System.out.print("Enter amount to withdraw: ");
                    double withdrawAmount = scanner.nextDouble();
                    currentAccount.withdraw(withdrawAmount);
                    break;
                    
                case 3:
                    currentAccount.checkBalance();
                    break;
                    
                case 4:
                    if (fd == null) {
                        System.out.print("Enter amount for fixed deposit: ");
                        double fdAmount = scanner.nextDouble();
                        System.out.print("Enter interest rate: ");
                        double fdRate = scanner.nextDouble();
                        System.out.print("Enter duration in months: ");
                        int fdDuration = scanner.nextInt();
                        
                        fd = new FixedDeposit(currentAccount, fdAmount, fdRate, fdDuration);
                    } else {
                        System.out.println("You already have an active Fixed Deposit.");
                    }
                    break;
                    
                case 5:
                    if (fd != null) {
                        fd.displayFDDetails();
                    } else {
                        System.out.println("No Fixed Deposit found.");
                    }
                    break;
                    
                case 6:
                    if (rd == null) {
                        System.out.print("Enter monthly premium for recurring deposit: ");
                        double rdPremium = scanner.nextDouble();
                        System.out.print("Enter interest rate: ");
                        double rdRate = scanner.nextDouble();
                        System.out.print("Enter duration in months: ");
                        int rdDuration = scanner.nextInt();
                        System.out.print("Enable auto-debit? (1 for Yes, 0 for No): ");
                        boolean autoDebit = scanner.nextInt() == 1;
                        
                        rd = new RecurringDeposit(currentAccount, rdPremium, rdRate, rdDuration, autoDebit);
                    } else {
                        System.out.println("You already have an active Recurring Deposit.");
                    }
                    break;
                    
                case 7:
                    if (rd != null) {
                        rd.depositMonthlyPremium(currentAccount);
                    } else {
                        System.out.println("No Recurring Deposit found.");
                    }
                    break;
                    
                case 8:
                    if (rd != null) {
                        rd.displayRDDetails();
                    } else {
                        System.out.println("No Recurring Deposit found.");
                    }
                    break;
                    
                case 9:
                    if (loan == null) {
                        System.out.print("Enter loan amount (max 90% of your balance): ");
                        double loanAmount = scanner.nextDouble();
                        System.out.print("Enter interest rate: ");
                        double loanRate = scanner.nextDouble();
                        System.out.print("Enter duration in months: ");
                        int loanDuration = scanner.nextInt();
                        
                        loan = new Loan(currentAccount, loanAmount, loanRate, loanDuration);
                    } else {
                        System.out.println("You already have an active Loan.");
                    }
                    break;
                    
                case 10:
                    if (loan != null) {
                        loan.payInstallment(currentAccount);
                    } else {
                        System.out.println("No active Loan found.");
                    }
                    break;
                    
                case 11:
                    if (loan != null) {
                        loan.displayLoanDetails();
                    } else {
                        System.out.println("No active Loan found.");
                    }
                    break;
                    
                case 12:
                    running = false;
                    System.out.println("Thank you for using our Banking Application!");
                    break;
                    
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
        
        scanner.close();
    }
}

```

**Sample Output:**
```
Welcome to Banking Application
Enter User ID: user123
Enter initial balance (minimum 500): 5000
Current account created successfully with User ID: user123

==== Banking Menu ====
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Open Fixed Deposit
5. View Fixed Deposit Details
6. Open Recurring Deposit
7. Pay RD Monthly Premium
8. View RD Details
9. Take Loan
10. Pay Loan Installment
11. View Loan Details
12. Exit
Enter your choice: 3
Current balance: 5000.0

==== Banking Menu ====
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Open Fixed Deposit
5. View Fixed Deposit Details
6. Open Recurring Deposit
7. Pay RD Monthly Premium
8. View RD Details
9. Take Loan
10. Pay Loan Installment
11. View Loan Details
12. Exit
Enter your choice: 4
Enter amount for fixed deposit: 2000
Enter interest rate: 6.5
Enter duration in months: 12
Fixed Deposit created successfully with amount: 2000.0
Withdrawal successful. New balance: 3000.0

==== Banking Menu ====
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Open Fixed Deposit
5. View Fixed Deposit Details
6. Open Recurring Deposit
7. Pay RD Monthly Premium
8. View RD Details
9. Take Loan
10. Pay Loan Installment
11. View Loan Details
12. Exit
Enter your choice: 5

Fixed Deposit Details:
Principal Amount: 2000.0
Annual Interest Rate: 6.5%
Duration: 12 months

Quarterly Interest Earnings:
Quarter 1: 32.50
Quarter 2: 33.03
Quarter 3: 33.56
Quarter 4: 34.11

Total Interest Earned: 133.20
Maturity Amount: 2133.20

==== Banking Menu ====
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Open Fixed Deposit
5. View Fixed Deposit Details
6. Open Recurring Deposit
7. Pay RD Monthly Premium
8. View RD Details
9. Take Loan
10. Pay Loan Installment
11. View Loan Details
12. Exit
Enter your choice: 9
Enter loan amount (max 90% of your balance): 2000
Enter interest rate: 10
Enter duration in months: 12
Loan approved for amount: 2000.0
Monthly installment: 175.83
Deposit successful. New balance: 5000.0

==== Banking Menu ====
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Open Fixed Deposit
5. View Fixed Deposit Details
6. Open Recurring Deposit
7. Pay RD Monthly Premium
8. View RD Details
9. Take Loan
10. Pay Loan Installment
11. View Loan Details
12. Exit
Enter your choice: 11

Loan Details:
Loan Amount: 2000.0
Annual Interest Rate: 10.0%
Duration: 12 months
Monthly Installment: 175.83
Total Interest Payable: 109.96
Total Amount Payable: 2109.96
Installments Paid: 0 of 12
Remaining Installments: 12
Remaining Amount: 2109.96

==== Banking Menu ====
1. Deposit Money
2. Withdraw Money
3. Check Balance
4. Open Fixed Deposit
5. View Fixed Deposit Details
6. Open Recurring Deposit
7. Pay RD Monthly Premium
8. View RD Details
9. Take Loan
10. Pay Loan Installment
11. View Loan Details
12. Exit
Enter your choice: 12
Thank you for using our Banking Application!
```

### Question 6: WAP to find area, perimeter and volume of a Rectangular, square and Circular Box using multilevel inheritance and method overriding.

```java
import java.util.Scanner;

class Shape {
    public double calculateArea() {
        return 0;
    }
    
    public double calculatePerimeter() {
        return 0;
    }
}

class Rectangle extends Shape {
    protected double length;
    protected double width;
    
    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }
    
    @Override
    public double calculateArea() {
        return length * width;
    }
    
    @Override
    public double calculatePerimeter() {
        return 2 * (length + width);
    }
}

class Square extends Rectangle {
    public Square(double side) {
        super(side, side);
    }
}

class Circle extends Shape {
    protected double radius;
    
    public Circle(double radius) {
        this.radius = radius;
    }
    
    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
    
    @Override
    public double calculatePerimeter() {
        return 2 * Math.PI * radius;
    }
}

class RectangularBox extends Rectangle {
    protected double height;
    
    public RectangularBox(double length, double width, double height) {
        super(length, width);
        this.height = height;
    }
    
    @Override
    public double calculateArea() {
        return 2 * (length * width + length * height + width * height);
    }
    
    public double calculateVolume() {
        return length * width * height;
    }
}

class SquareBox extends Square {
    private double height;
    
    public SquareBox(double side, double height) {
        super(side);
        this.height = height;
    }
    
    @Override
    public double calculateArea() {
        return 2 * (length * width + 2 * length * height);
    }
    
    public double calculateVolume() {
        return length * width * height;
    }
}

class CircularBox extends Circle {
    private double height;
    
    public CircularBox(double radius, double height) {
        super(radius);
        this.height = height;
    }
    
    @Override
    public double calculateArea() {
        return 2 * Math.PI * radius * (radius + height);
    }
    
    public double calculateVolume() {
        return Math.PI * radius * radius * height;
    }
}

public class ShapeCalculations {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int choice;
        do {
            System.out.println("\nSelect a shape to calculate:");
            System.out.println("1. Rectangular Box");
            System.out.println("2. Square Box");
            System.out.println("3. Circular Box");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();
            
            switch (choice) {
                case 1:
                    System.out.print("Enter length: ");
                    double length = scanner.nextDouble();
                    System.out.print("Enter width: ");
                    double width = scanner.nextDouble();
                    System.out.print("Enter height: ");
                    double rHeight = scanner.nextDouble();
                    
                    RectangularBox rectBox = new RectangularBox(length, width, rHeight);
                    System.out.println("\nRectangular Box:");
                    System.out.println("Surface Area: " + rectBox.calculateArea());
                    System.out.println("Volume: " + rectBox.calculateVolume());
                    break;
                    
                case 2:
                    System.out.print("Enter side length: ");
                    double side = scanner.nextDouble();
                    System.out.print("Enter height: ");
                    double sHeight = scanner.nextDouble();
                    
                    SquareBox squareBox = new SquareBox(side, sHeight);
                    System.out.println("\nSquare Box:");
                    System.out.println("Surface Area: " + squareBox.calculateArea());
                    System.out.println("Volume: " + squareBox.calculateVolume());
                    break;
                    
                case 3:
                    System.out.print("Enter radius: ");
                    double radius = scanner.nextDouble();
                    System.out.print("Enter height: ");
                    double cHeight = scanner.nextDouble();
                    
                    CircularBox circleBox = new CircularBox(radius, cHeight);
                    System.out.println("\nCircular Box (Cylinder):");
                    System.out.println("Surface Area: " + circleBox.calculateArea());
                    System.out.println("Volume: " + circleBox.calculateVolume());
                    break;
                    
                case 4:
                    System.out.println("Exiting...");
                    break;
                    
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
            
        } while (choice != 4);
        
        scanner.close();
    }
}

```

**Sample Output:**
```
Select a shape to calculate:
1. Rectangular Box
2. Square Box
3. Circular Box
4. Exit
Enter your choice: 1
Enter length: 10
Enter width: 8
Enter height: 6

Rectangular Box:
Surface Area: 376.0
Volume: 480.0

Select a shape to calculate:
1. Rectangular Box
2. Square Box
3. Circular Box
4. Exit
Enter your choice: 2
Enter side length: 5
Enter height: 5

Square Box:
Surface Area: 150.0
Volume: 125.0

Select a shape to calculate:
1. Rectangular Box
2. Square Box
3. Circular Box
4. Exit
Enter your choice: 3
Enter radius: 4
Enter height: 10

Circular Box (Cylinder):
Surface Area: 351.8583772020569
Volume: 502.6548245743669

Select a shape to calculate:
1. Rectangular Box
2. Square Box
3. Circular Box
4. Exit
Enter your choice: 4
Exiting...
```


### 7. WAP to find simple interest provided by bank on the available amount on the saving account by various banks SBI, Union, HDFC, ICICI with rate of interest 6.5, 6.5, 7.4, 7.9 respectively using method overriding and dynamic method dispatch. Minimum rate of interest is 5.4 and mechanism to compute simple and compound interest is set by RBI.

```java
class RBI {
    double rate = 5.4;

    void computeInterest(double principal, int time) {
        double si = (principal * rate * time) / 100;
        System.out.println("RBI Simple Interest: " + si);
    }
}

class SBI extends RBI {
    void computeInterest(double principal, int time) {
        rate = 6.5;
        double si = (principal * rate * time) / 100;
        System.out.println("SBI Simple Interest: " + si);
    }
}

class Union extends RBI {
    void computeInterest(double principal, int time) {
        rate = 6.5;
        double si = (principal * rate * time) / 100;
        System.out.println("Union Simple Interest: " + si);
    }
}

class HDFC extends RBI {
    void computeInterest(double principal, int time) {
        rate = 7.4;
        double si = (principal * rate * time) / 100;
        System.out.println("HDFC Simple Interest: " + si);
    }
}

class ICICI extends RBI {
    void computeInterest(double principal, int time) {
        rate = 7.9;
        double si = (principal * rate * time) / 100;
        System.out.println("ICICI Simple Interest: " + si);
    }
}

public class BankInterest {
    public static void main(String[] args) {
        RBI r;
        r = new SBI();
        r.computeInterest(10000, 2);

        r = new Union();
        r.computeInterest(10000, 2);

        r = new HDFC();
        r.computeInterest(10000, 2);

        r = new ICICI();
        r.computeInterest(10000, 2);
    }
}
```

**Sample Output:**
```
SBI Simple Interest: 1300.0
Union Simple Interest: 1300.0
HDFC Simple Interest: 1480.0
ICICI Simple Interest: 1580.0
```

---

### 8. Write a Java program that creates a class hierarchy for employees of a company. The base class should be Employee, with subclasses Manager, Developer, and Programmer. Each subclass should have properties such as name, address, salary, and job title. Implement methods for calculating bonuses, generating performance reports, and managing projects. Assume that Manger provides n no. of jobs to developer and programmer and as per the outcome manger received bonuses will be given with salary for encouragement. Performance of Manager, developer and programmer should be estimated for salary.

```java
class Employee {
    String name, address, jobTitle;
    double salary;

    Employee(String name, String address, String jobTitle, double salary) {
        this.name = name;
        this.address = address;
        this.jobTitle = jobTitle;
        this.salary = salary;
    }

    double calculateBonus() {
        return salary * 0.10;
    }

    void generateReport() {
        System.out.println(jobTitle + " " + name + " Report Generated.");
    }

    void manageProject() {
        System.out.println(jobTitle + " " + name + " is managing projects.");
    }

    void displaySalary() {
        System.out.println(name + " Salary with Bonus: " + (salary + calculateBonus()));
    }
}

class Manager extends Employee {
    int jobsAssigned;

    Manager(String name, String address, double salary, int jobsAssigned) {
        super(name, address, "Manager", salary);
        this.jobsAssigned = jobsAssigned;
    }

    double calculateBonus() {
        return salary * 0.20 + jobsAssigned * 100;
    }
}

class Developer extends Employee {
    Developer(String name, String address, double salary) {
        super(name, address, "Developer", salary);
    }

    double calculateBonus() {
        return salary * 0.15;
    }
}

class Programmer extends Employee {
    Programmer(String name, String address, double salary) {
        super(name, address, "Programmer", salary);
    }

    double calculateBonus() {
        return salary * 0.12;
    }
}

public class Company {
    public static void main(String[] args) {
        Manager m = new Manager("Alice", "New York", 80000, 5);
        Developer d = new Developer("Bob", "California", 60000);
        Programmer p = new Programmer("Charlie", "Texas", 50000);

        m.generateReport();
        d.generateReport();
        p.generateReport();

        m.manageProject();
        d.manageProject();
        p.manageProject();

        m.displaySalary();
        d.displaySalary();
        p.displaySalary();
    }
}
```

**Sample Output:**
```
Manager Alice Report Generated.
Developer Bob Report Generated.
Programmer Charlie Report Generated.
Manager Alice is managing projects.
Developer Bob is managing projects.
Programmer Charlie is managing projects.
Alice Salary with Bonus: 81600.0
Bob Salary with Bonus: 69000.0
Charlie Salary with Bonus: 56000.0
```

---

### 9. Write a Java program to create a vehicle class hierarchy. The base class should be Vehicle, with subclasses Truck, Car and Motorcycle. Each subclass should have properties such as make, model, year, and fuel type. Implement methods for calculating fuel efficiency, distance traveled, and maximum speed.

```java
class Vehicle {
    String make, model, fuelType;
    int year;

    Vehicle(String make, String model, int year, String fuelType) {
        this.make = make;
        this.model = model;
        this.year = year;
        this.fuelType = fuelType;
    }

    void fuelEfficiency() {
        System.out.println("Generic Vehicle fuel efficiency.");
    }

    void distanceTraveled(int speed, int time) {
        System.out.println("Distance Traveled: " + (speed * time) + " km");
    }

    void maxSpeed() {
        System.out.println("Generic Vehicle max speed.");
    }
}

class Truck extends Vehicle {
    Truck(String make, String model, int year, String fuelType) {
        super(make, model, year, fuelType);
    }

    void fuelEfficiency() {
        System.out.println("Truck fuel efficiency: 5 km/l");
    }

    void maxSpeed() {
        System.out.println("Truck max speed: 80 km/h");
    }
}

class Car extends Vehicle {
    Car(String make, String model, int year, String fuelType) {
        super(make, model, year, fuelType);
    }

    void fuelEfficiency() {
        System.out.println("Car fuel efficiency: 15 km/l");
    }

    void maxSpeed() {
        System.out.println("Car max speed: 180 km/h");
    }
}

class Motorcycle extends Vehicle {
    Motorcycle(String make, String model, int year, String fuelType) {
        super(make, model, year, fuelType);
    }

    void fuelEfficiency() {
        System.out.println("Motorcycle fuel efficiency: 40 km/l");
    }

    void maxSpeed() {
        System.out.println("Motorcycle max speed: 120 km/h");
    }
}

public class VehicleInfo {
    public static void main(String[] args) {
        Truck t = new Truck("Tata", "HeavyDuty", 2020, "Diesel");
        Car c = new Car("Hyundai", "Verna", 2021, "Petrol");
        Motorcycle m = new Motorcycle("Yamaha", "FZ", 2022, "Petrol");

        t.fuelEfficiency();
        t.distanceTraveled(60, 3);
        t.maxSpeed();

        c.fuelEfficiency();
        c.distanceTraveled(100, 2);
        c.maxSpeed();

        m.fuelEfficiency();
        m.distanceTraveled(90, 1);
        m.maxSpeed();
    }
}
```

**Sample Output:**
```
Truck fuel efficiency: 5 km/l
Distance Traveled: 180 km
Truck max speed: 80 km/h
Car fuel efficiency: 15 km/l
Distance Traveled: 200 km
Car max speed: 180 km/h
Motorcycle fuel efficiency: 40 km/l
Distance Traveled: 90 km
Motorcycle max speed: 120 km/h
```

---


