I'll provide answers for all 43 questions from the assignment, focusing on Python whenever applicable.

## 1. Write an algorithm to find sum of first n natural numbers

```python
def sum_of_natural_numbers(n):
    """
    Calculate the sum of first n natural numbers
    """
    # Method 1: Using formula
    return (n * (n + 1)) // 2
    
    # Method 2: Using iteration
    # sum = 0
    # for i in range(1, n + 1):
    #     sum += i
    # return sum
```

## 2. How will you analyze the efficiency of an algorithm?

Algorithm efficiency can be analyzed using:

1. Time complexity: Measures how execution time grows as input size increases
2. Space complexity: Measures how memory usage grows as input size increases

We typically use Big O notation (O(n), O(log n), O(n²), etc.) to express these complexities. In Python, we can measure actual execution time using the `time` module or `timeit` module, and analyze memory usage using libraries like `memory_profiler`.

## 3. What is the use of algorithm, Flowchart and Pseudocode in the perspective of problem solving?

- **Algorithm**: Provides a step-by-step logical procedure to solve a problem systematically
- **Flowchart**: Visual representation of an algorithm using standardized symbols, making it easier to understand the logic flow
- **Pseudocode**: A semi-formal way to describe algorithms using a mix of natural language and programming constructs

In Python programming, these tools help us design the solution before coding, making the implementation process more efficient and reducing errors.

## 4. Distinguish between algorithm and program.

| Algorithm | Program |
|-----------|---------|
| Language-independent logical solution | Implementation of algorithm in a specific programming language (e.g., Python) |
| Theoretical construct | Executable code |
| Hardware and software independent | Dependent on hardware and software environment |
| Uses natural language, pseudocode | Uses syntax of a programming language |
| Focus on logic and efficiency | Focus on syntax and implementation details |
| Can be manually executed | Executed by a computer |

## 5. What is a Pseudocode? What are the benefits of pseudocode?

Pseudocode is a high-level description of an algorithm using natural language and simple programming constructs that is not tied to any specific programming language.

Benefits of pseudocode:
1. Language-independent: Can be translated to any programming language (including Python)
2. Easy to understand for both programmers and non-programmers
3. Focuses on logic without syntax concerns
4. Reduces development time by catching logical errors early
5. Bridges the gap between algorithm design and actual coding
6. Easier to review and validate than actual code
7. Helpful for documentation

## 6. What are flowcharts and list down their advantages?

Flowcharts are graphical representations of algorithms using standardized symbols connected by arrows to show the sequence of operations.

Advantages:
1. Visual clarity: Makes logic easier to understand
2. Communication tool: Helps communicate program flow to stakeholders
3. Debugging aid: Helps identify logical errors
4. Documentation: Serves as effective documentation
5. Analysis tool: Helps in analyzing complex problems
6. Standardized: Uses globally recognized symbols
7. Implementation guidance: Helps in translating logic to Python code
8. Maintenance: Makes program maintenance easier

## 7. Enlist the advantages of algorithm.

Advantages of algorithms:
1. Problem-solving framework: Provides a systematic approach to solving problems
2. Language-independent: Can be implemented in any language (Python, Java, etc.)
3. Efficiency analysis: Allows analysis of time and space complexity
4. Reusability: Can be adapted for similar problems
5. Scalability assessment: Helps determine how solution scales with input size
6. Verification: Makes it easier to verify correctness
7. Optimization: Allows for refinement before implementation
8. Communication: Provides a common language for discussing solutions

## 8. Write down steps involved in writing a program to solve a problem.

Steps for writing a Python program to solve a problem:
1. Understand the problem clearly
2. Analyze input and output requirements
3. Design an algorithm or logical solution
4. Create pseudocode or flowchart
5. Code the solution in Python
6. Test the program with sample inputs
7. Debug and fix errors
8. Optimize the code for better efficiency
9. Document the code with comments
10. Implement exception handling where needed

## 9. What is control flow? List and define the ways of execution of control.

Control flow is the order in which statements are executed in a program.

Ways of execution control in Python:
1. **Sequential execution**: Statements executed one after another
2. **Conditional execution** (Selection):
   - `if-elif-else` statements: Execute code based on conditions
3. **Iterative execution** (Loops):
   - `for` loops: Iterate over sequences
   - `while` loops: Execute as long as a condition is true
4. **Jump statements**:
   - `break`: Exit from a loop
   - `continue`: Skip current iteration and continue loop
   - `pass`: Null operation, does nothing
   - `return`: Exit from a function
5. **Exception handling**:
   - `try-except-else-finally`: Handle errors gracefully

## 10. Write a recursive algorithm of tower of Hanoi.

```python
def tower_of_hanoi(n, source, auxiliary, destination):
    """
    Solve Tower of Hanoi puzzle with n disks
    
    Parameters:
    n: Number of disks
    source: Source rod
    auxiliary: Helper rod
    destination: Target rod
    """
    if n == 1:
        print(f"Move disk 1 from {source} to {destination}")
        return
        
    # Move n-1 disks from source to auxiliary
    tower_of_hanoi(n-1, source, destination, auxiliary)
    
    # Move the nth disk from source to destination
    print(f"Move disk {n} from {source} to {destination}")
    
    # Move n-1 disks from auxiliary to destination
    tower_of_hanoi(n-1, auxiliary, source, destination)

# Example usage
tower_of_hanoi(3, 'A', 'B', 'C')
```

## 11. Identify the simple strategies for developing an algorithm.

Simple strategies for developing algorithms:
1. **Divide and conquer**: Break complex problems into smaller subproblems
2. **Greedy approach**: Make locally optimal choices at each step
3. **Dynamic programming**: Break down problem into overlapping subproblems
4. **Brute force**: Try all possible solutions
5. **Recursive approach**: Solve problems by breaking them down into smaller versions
6. **Iterative approach**: Solve using loops instead of recursion
7. **Top-down approach**: Start with the main problem and break it down
8. **Bottom-up approach**: Solve simplest subproblems first, then build up

These strategies guide the development of Python algorithms for various problem domains.

## 12. Write an algorithm to insert a card into a list of sorted cards.

```python
def insert_card(sorted_cards, new_card):
    """
    Insert a new card into a sorted list of cards
    """
    # Method 1: Using Python's built-in features
    sorted_cards.append(new_card)
    sorted_cards.sort()
    return sorted_cards
    
    # Method 2: Manual insertion
    # i = 0
    # while i < len(sorted_cards) and sorted_cards[i] < new_card:
    #     i += 1
    # sorted_cards.insert(i, new_card)
    # return sorted_cards
```

## 13. What is Python Programming Language? Explain in detail with their advantages and disadvantages.

Python is a high-level, interpreted programming language created by Guido van Rossum and first released in 1991. It emphasizes readability and simplicity with a design philosophy that stresses code readability through significant whitespace.

**Advantages:**
1. **Easy to learn and read**: Simple syntax that resembles English
2. **Versatile**: Used in web development, data science, AI, automation, etc.
3. **Interpreted**: No compilation step required, immediate feedback
4. **Extensive libraries**: Rich ecosystem of libraries and frameworks (NumPy, Pandas, Django, etc.)
5. **Cross-platform**: Runs on Windows, macOS, Linux, etc.
6. **Open-source**: Free to use and distribute
7. **Strong community**: Large, active community providing support and resources
8. **Dynamically typed**: No need to declare variable types
9. **Object-oriented**: Supports OOP principles
10. **Integrates well**: Can be integrated with other languages like C/C++

**Disadvantages:**
1. **Speed limitations**: Slower than compiled languages like C++ or Java
2. **Mobile development**: Not the primary choice for mobile app development
3. **Runtime errors**: Type-related errors only appear during execution
4. **Global Interpreter Lock (GIL)**: Limits true multi-threading
5. **Memory consumption**: Can be memory-intensive
6. **Design constraints**: Indentation-based syntax can be challenging
7. **Weak in mobile computing**: Limited support for mobile platforms
8. **Enterprise use**: Less established for some enterprise applications

## 14. What is recursive function? What are its advantages and disadvantages? Compare it with iterative function.

A recursive function is a function that calls itself to solve smaller instances of the same problem.

**Advantages of Recursion:**
1. Elegant and easier to understand for inherently recursive problems
2. Follows the mathematical definition of many problems (e.g., factorial)
3. Can reduce complex problems to simple cases
4. More readable for tree-like structures and divide-and-conquer algorithms

**Disadvantages of Recursion:**
1. Higher memory overhead due to call stack usage
2. Risk of stack overflow for deep recursion
3. Often slower due to function call overhead
4. Can be harder to trace and debug

**Comparison with Iteration:**

| Recursive Functions | Iterative Functions |
|---------------------|---------------------|
| Uses function calls to repeat | Uses loops to repeat |
| Base case terminates recursion | Loop condition controls termination |
| Uses stack memory | Uses less memory |
| May cause stack overflow | No stack overflow risk |
| Often cleaner for tree-like structures | Often better for linear problems |
| Slower due to function call overhead | Usually faster |
| Memory: O(n) for n recursive calls | Memory: O(1) for fixed variables |
| E.g., `factorial(n) = n * factorial(n-1)` | E.g., `for i in range(1, n+1): fact *= i` |

## 15. Draw a flowchart to find the sum of the series 1+2+3+4-----+100

In Python, this would be implemented as:

```python
def sum_series():
    sum = 0
    for i in range(1, 101):
        sum += i
    return sum

print(sum_series())  # Output: 5050
```

## 16. Draw a flowchart to check whether the given number is zero, positive or negative.

In Python, this would be implemented as:

```python
def check_number(num):
    if num > 0:
        return "Positive"
    elif num < 0:
        return "Negative"
    else:
        return "Zero"

print(check_number(5))    # Output: Positive
print(check_number(-3))   # Output: Negative
print(check_number(0))    # Output: Zero
```

## 17. What is Pseudocode? Write a Pseudocode for swapping two numbers without using temporary storage.

Pseudocode is a method of describing algorithms in a human-readable format, using structured text that resembles programming code but is not tied to any specific language.

Pseudocode for swapping two numbers without using a temporary variable:
```
BEGIN
    Input a, b
    a = a + b
    b = a - b
    a = a - b
    Output a, b
END
```

In Python:
```python
def swap_without_temp(a, b):
    print(f"Before: a = {a}, b = {b}")
    a = a + b
    b = a - b
    a = a - b
    print(f"After: a = {a}, b = {b}")
    return a, b

x, y = 10, 20
x, y = swap_without_temp(x, y)  # Output: Before: a = 10, b = 20, After: a = 20, b = 10
```

## 18. Draw the flowchart for finding the roots of a quadratic equation.

In Python, this would be implemented as:

```python
import math

def quadratic_roots(a, b, c):
    # Calculate discriminant
    d = b**2 - 4*a*c
    
    # Check if discriminant is negative
    if d < 0:
        return "No real roots"
    
    # Calculate roots
    root1 = (-b + math.sqrt(d)) / (2*a)
    root2 = (-b - math.sqrt(d)) / (2*a)
    
    if d == 0:
        return f"One real root: {root1}"
    else:
        return f"Two real roots: {root1} and {root2}"

print(quadratic_roots(1, -3, 2))  # Output: Two real roots: 2.0 and 1.0
print(quadratic_roots(1, -2, 1))  # Output: One real root: 1.0
print(quadratic_roots(1, 1, 1))   # Output: No real roots
```

## 19. What is Pseudocode? How does it differ from flowchart? Write a Pseudocode to add up all the even numbers between 0 and 100 and print the result.

Pseudocode is a high-level description of an algorithm using natural language and simple programming constructs.

**Differences between Pseudocode and Flowchart:**

| Pseudocode | Flowchart |
|------------|-----------|
| Text-based representation | Graphical representation |
| Uses words and simple notation | Uses standardized symbols and arrows |
| Linear format | Non-linear, visual format |
| Easier to modify | Harder to modify once created |
| Less intuitive for beginners | More intuitive visual understanding |
| No standardized syntax | Standardized symbols |
| Better for complex logic | Better for showing program flow |

**Pseudocode for summing even numbers between 0 and 100:**
```
BEGIN
    Set sum = 0
    FOR i = 0 TO 100 STEP 2
        sum = sum + i
    END FOR
    OUTPUT sum
END
```

In Python:
```python
def sum_even_numbers():
    sum = 0
    for i in range(0, 101, 2):
        sum += i
    return sum

print(sum_even_numbers())  # Output: 2550
```

## 20. Explain the guidelines for preparing flowcharts, benefits and limitation of flowcharts.

**Guidelines for preparing flowcharts:**
1. Use standard symbols (terminal, process, decision, etc.)
2. Flow direction is typically top-to-bottom, left-to-right
3. Use one entry and one exit point for clarity
4. Keep the flowchart on one page if possible
5. Use annotations to clarify complex steps
6. Maintain consistency in symbol usage
7. Use connectors to avoid crossing lines
8. Label decision paths clearly (Yes/No, True/False)

**Benefits of flowcharts:**
1. Visual clarity of algorithm logic
2. Easy to understand for technical and non-technical people
3. Useful for planning before coding
4. Helps identify logical errors and inefficiencies
5. Effective documentation of program logic
6. Simplifies debugging and maintenance
7. Useful for explaining program flow to others

**Limitations of flowcharts:**
1. Time-consuming to create and update
2. Can become unwieldy for complex problems
3. Difficult to modify once created
4. May not capture all programming concepts easily
5. Over-simplification of complex logic
6. May not directly translate to coding constructs
7. Requires knowledge of flowchart symbols

## 21. Draw a flowchart to find the highest mark in a set of n marks.

In Python, this would be implemented as:

```python
def find_highest_mark(marks):
    if not marks:
        return None
    
    highest = marks[0]
    for mark in marks:
        if mark > highest:
            highest = mark
    
    return highest

# Example usage
marks = [78, 92, 85, 64, 88, 91]
print(f"The highest mark is: {find_highest_mark(marks)}")  # Output: The highest mark is: 92
```

## 22. Write a Pseudocode to multiply two matrices.

Pseudocode for matrix multiplication:
```
BEGIN
    Input matrix A of size m×n
    Input matrix B of size n×p
    Create result matrix C of size m×p initialized with zeros
    
    FOR i = 0 TO m-1
        FOR j = 0 TO p-1
            FOR k = 0 TO n-1
                C[i][j] = C[i][j] + A[i][k] * B[k][j]
            END FOR
        END FOR
    END FOR
    
    Output matrix C
END
```

In Python:

```python
def matrix_multiply(A, B):
    # Check if matrices can be multiplied
    if len(A[0]) != len(B):
        return "Cannot multiply: Incompatible dimensions"
    
    # Initialize result matrix with zeros
    result = [[0 for _ in range(len(B[0]))] for _ in range(len(A))]
    
    # Perform multiplication
    for i in range(len(A)):
        for j in range(len(B[0])):
            for k in range(len(B)):
                result[i][j] += A[i][k] * B[k][j]
    
    return result

# Example usage
A = [[1, 2], [3, 4]]
B = [[5, 6], [7, 8]]
result = matrix_multiply(A, B)
for row in result:
    print(row)
# Output: 
# [19, 22]
# [43, 50]
```

## 23. Draw a flowchart and write an algorithm to start a list of numbers in ascending order.

In Python, this would be implemented as:

```python
def sort_ascending(numbers):
    # Method 1: Using built-in sort function
    numbers.sort()
    return numbers
    
    # Method 2: Bubble sort implementation
    # n = len(numbers)
    # for i in range(n):
    #     for j in range(0, n-i-1):
    #         if numbers[j] > numbers[j+1]:
    #             numbers[j], numbers[j+1] = numbers[j+1], numbers[j]
    # return numbers

# Example usage
numbers = [64, 34, 25, 12, 22, 11, 90]
sorted_numbers = sort_ascending(numbers)
print(sorted_numbers)  # Output: [11, 12, 22, 25, 34, 64, 90]
```

## 24. Discuss the importance need function in python and illustrate a program to exchange the value of two variables with temporary variables?

**Importance of functions in Python:**
1. **Code reusability**: Define code once, use it multiple times
2. **Modularity**: Break down complex problems into manageable pieces
3. **Abstraction**: Hide implementation details, focus on what code does
4. **Maintainability**: Easier to update and maintain code
5. **Testing**: Isolate and test individual components
6. **Scoping**: Control variable scope and avoid naming conflicts
7. **Organization**: Structure code logically
8. **Parameter passing**: Allow flexible data handling
9. **Return values**: Process data and return results

**Program to exchange values using a temporary variable:**

```python
def swap_values(a, b):
    print(f"Before swapping: a = {a}, b = {b}")
    
    # Using a temporary variable to swap
    temp = a
    a = b
    b = temp
    
    print(f"After swapping: a = {a}, b = {b}")
    return a, b

# Example usage
x = 10
y = 20
x, y = swap_values(x, y)
```

Output:
```
Before swapping: a = 10, b = 20
After swapping: a = 20, b = 10
```

## 25. Explain the operator precedence of arithmetic operators in python?

Operator precedence in Python determines the order in which operations are performed. For arithmetic operators, the precedence (from highest to lowest) is:

1. `**` (Exponentiation)
2. `+x`, `-x` (Positive, Negative - unary operators)
3. `*`, `/`, `//`, `%` (Multiplication, Division, Floor division, Modulus)
4. `+`, `-` (Addition, Subtraction)

Example demonstrating precedence:
```python
result = 2 + 3 * 4 ** 2 - 6 / 2
# Evaluation:
# 1. 4 ** 2 = 16        (Exponentiation first)
# 2. 3 * 16 = 48        (Multiplication)
# 3. 6 / 2 = 3.0        (Division)
# 4. 2 + 48 = 50        (Addition)
# 5. 50 - 3.0 = 47.0    (Subtraction)

print(result)  # Output: 47.0
```

You can override the precedence using parentheses:
```python
result = (2 + 3) * 4 ** (2 - 6) / 2
# Evaluation:
# 1. (2 + 3) = 5        (Parentheses)
# 2. (2 - 6) = -4       (Parentheses)
# 3. 4 ** -4 = 0.00390625 (Exponentiation)
# 4. 5 * 0.00390625 = 0.01953125 (Multiplication)
# 5. 0.01953125 / 2 = 0.009765625 (Division)

print(result)  # Output: 0.009765625
```

## 26. Where does indexing starts in python?

In Python, indexing starts at 0 (zero-based indexing). This applies to all sequence types like strings, lists, tuples, and arrays.

Examples:
```python
# List indexing
my_list = ['apple', 'banana', 'cherry', 'date']
print(my_list[0])  # Output: apple (first element)
print(my_list[3])  # Output: date (fourth element)

# String indexing
text = "Python"
print(text[0])     # Output: P (first character)
print(text[5])     # Output: n (sixth character)

# Negative indexing (counts from the end)
print(my_list[-1])  # Output: date (last element)
print(text[-1])     # Output: n (last character)

# Slicing
print(my_list[1:3])  # Output: ['banana', 'cherry'] (elements at index 1 and 2)
print(text[0:3])     # Output: Pyt (characters at index 0, 1, and 2)
```

## 27. What is the use of pass statements? Illustrate with an example?

The `pass` statement in Python is a null operation or placeholder. It does nothing when executed but serves as a placeholder when a statement is required syntactically but no action is desired.

**Uses of pass statement:**
1. Create minimal classes or functions
2. Act as a placeholder for future code
3. Create empty loops
4. Implement abstract methods
5. Handle exceptions without taking action
6. Create stubs for work-in-progress code

Examples:

```python
# 1. Empty function definition
def function_to_implement_later():
    pass  # Will implement this later

# 2. Empty class definition
class EmptyClass:
    pass  # Will add methods later

# 3. In conditional statements
x = 10
if x > 5:
    pass  # No action needed for this case
else:
    print("x is 5 or less")

# 4. In loops when waiting for an external event
while not user_input:
    pass  # Wait for user input from another thread

# 5. In except blocks when exception should be ignored
try:
    # Some risky operation
    result = 10 / 0
except ZeroDivisionError:
    pass  # Ignore division by zero
```

## 28. What is call by value and call by reference and explain it with suitable examples?

**Call by Value vs Call by Reference in Python:**

In Python, the parameter passing mechanism is neither strictly call-by-value nor call-by-reference. It's actually "call by object reference" or "call by assignment." However, understanding the traditional concepts helps clarify Python's behavior:

**Call by Value:**
- A copy of the actual argument's value is passed to the function
- Changes to the parameter inside the function don't affect the original variable

**Call by Reference:**
- A reference to the actual argument is passed to the function
- Changes to the parameter inside the function affect the original variable

Python's behavior depends on the object type:
- For immutable objects (int, float, string, tuple): Behaves like call by value
- For mutable objects (list, dict, set): Behaves like call by reference

Examples:

```python
# Example with immutable objects (behaves like call by value)
def modify_immutable(x):
    print(f"Inside function, initial x = {x}")
    x += 10  # Creates a new object
    print(f"Inside function, modified x = {x}")

num = 5
print(f"Before function call: num = {num}")
modify_immutable(num)
print(f"After function call: num = {num}")  # Value remains unchanged

# Output:
# Before function call: num = 5
# Inside function, initial x = 5
# Inside function, modified x = 15
# After function call: num = 5

# Example with mutable objects (behaves like call by reference)
def modify_mutable(lst):
    print(f"Inside function, initial list = {lst}")
    lst.append(4)  # Modifies the original object
    print(f"Inside function, modified list = {lst}")

my_list = [1, 2, 3]
print(f"Before function call: my_list = {my_list}")
modify_mutable(my_list)
print(f"After function call: my_list = {my_list}")  # Value is changed

# Output:
# Before function call: my_list = [1, 2, 3]
# Inside function, initial list = [1, 2, 3]
# Inside function, modified list = [1, 2, 3, 4]
# After function call: my_list = [1, 2, 3, 4]
```

## 29. Explain with an example – While loop, break statements, and continue statement in python?

**While Loop**:
A `while` loop executes a block of code repeatedly as long as a condition is true.

```python
# Example: Print numbers 1 through 5
count = 1
while count <= 5:
    print(count)
    count += 1

# Output:
# 1
# 2
# 3
# 4
# 5
```

**Break Statement**:
The `break` statement terminates the loop containing it and transfers execution to the statement following the loop.

```python
# Example: Find the first number divisible by 7 between 1 and 100
number = 1
while number <= 100:
    if number % 7 == 0:
        print(f"First number divisible by 7: {number}")
        break  # Exit the loop once found
    number += 1

# Output: First number divisible by 7: 7
```

**Continue Statement**:
The `continue` statement skips the rest of the code inside the loop for the current iteration and jumps to the next iteration.

```python
# Example: Print only odd numbers from 1 to 10
number = 0
while number < 10:
    number += 1
    if number % 2 == 0:  # If number is even
        continue  # Skip the rest of the loop
    print(number)

# Output:
# 1
# 3
# 5
# 7
# 9
```

**Combined Example**:
```python
# Print numbers from 1 to 20, skip multiples of 3, stop at 15
num = 0
while num < 20:
    num += 1
    
    # Skip multiples of 3
    if num % 3 == 0:
        continue
        
    # Stop at 15
    if num > 15:
        break
        
    print(num)

# Output:
# 1
# 2
# 4
# 5
# 7
# 8
# 10
# 11
# 13
# 14
```

## 30. Explain the significance of Xrange() function in for loop with a help of a program?

In Python 2, `xrange()` was a memory-efficient version of `range()` for large ranges. It returned an iterator instead of a list, so it used less memory. In Python 3, `range()` behaves like the old `xrange()`, and `xrange()` is no longer available.

The significance of `xrange()` (in Python 2) or `range()` (in Python 3) is that it creates an iterable object that generates values on-demand, without storing all values in memory at once.

Comparing Python 2 behavior:

```python
# Python 2 example
# Memory inefficient - creates a list in memory
for i in range(10000000):  # Creates a list with 10 million elements
    if i % 1000000 == 0:
        print(i)

# Memory efficient - generates values on demand
for i in xrange(10000000):  # Creates an iterator that yields values as needed
    if i % 1000000 == 0:
        print(i)
```

In Python 3, the equivalent code would be:

```python
# Python 3 example
# Memory efficient - range() now behaves like xrange() in Python 2
for i in range(10000000):  # Creates an iterator
    if i % 1000000 == 0:
        print(i)

# Example to demonstrate the memory efficiency
import sys

# Create a range object - doesn't store all values
r = range(10000000)
print(f"Memory size of range object: {sys.getsizeof(r)} bytes")

# Convert to list - stores all values
list_r = list(range(1000000))
print(f"Memory size of equivalent list: {sys.getsizeof(list_r)} bytes")

# Output will show range object is much smaller than the list
```

## 31. Create program to find the factorial of given number without recursion and with recursion?

**Factorial without recursion (iterative approach):**

```python
def factorial_iterative(n):
    """Calculate factorial using iteration"""
    if n < 0:
        return "Factorial not defined for negative numbers"
    if n == 0 or n == 1:
        return 1
        
    result = 1
    for i in range(2, n + 1):
        result *= i
    return result

# Test the function
for num in range(6):
    print(f"{num}! = {factorial_iterative(num)}")

# Output:
# 0! = 1
# 1! = 1
# 2! = 2
# 3! = 6
# 4! = 24
# 5! = 120
```

**Factorial with recursion:**

```python
def factorial_recursive(n):
    """Calculate factorial using recursion"""
    if n < 0:
        return "Factorial not defined for negative numbers"
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial_recursive(n - 1)

# Test the function
for num in range(6):
    print(f"{num}! = {factorial_recursive(num)}")

# Output:
# 0! = 1
# 1! = 1
# 2! = 2
# 3! = 6
# 4! = 24
# 5! = 120
```

## 32. What are the advantages of tuple over the list? (continued)

7. **Heterogeneous data**: Better suited for storing related but different types of data (like database records)
8. **Thread safety**: No need for locks when sharing between threads
9. **Hashable**: Can be used in sets and as dictionary keys
10. **Clearer intentions**: Signals to other developers that the data shouldn't change

Example demonstrating tuple advantages:
```python
# Dictionary keys: Tuples can be used as dictionary keys (lists cannot)
coordinates = {}
point_tuple = (3, 4)  # Tuple as key - works fine
coordinates[point_tuple] = "Point A"

try:
    point_list = [3, 4]  # List as key - will cause error
    coordinates[point_list] = "Point B"
except TypeError as e:
    print(f"Error: {e}")  # Output: Error: unhashable type: 'list'

# Multiple return values
def get_dimensions():
    return (1920, 1080)  # Returning multiple values as tuple

width, height = get_dimensions()  # Unpacking the tuple
print(f"Resolution: {width}x{height}")  # Output: Resolution: 1920x1080
```

## 33. Perform the bubble sort on the elements 23,78,45,8,32,56.

```python
def bubble_sort(arr):
    n = len(arr)
    # Track iterations for demonstration
    iterations = []
    
    # Traverse through all array elements
    for i in range(n):
        # Flag to optimize if no swaps occur
        swapped = False
        
        # Last i elements are already in place
        for j in range(0, n-i-1):
            # Swap if the element found is greater than the next element
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        
        # Save the current state after each pass
        iterations.append(arr.copy())
        
        # If no swapping occurred in this pass, array is sorted
        if not swapped:
            break
    
    return arr, iterations

# Given array
arr = [23, 78, 45, 8, 32, 56]
print(f"Original array: {arr}")

# Sort the array
sorted_arr, steps = bubble_sort(arr)

# Print each iteration
for i, step in enumerate(steps):
    print(f"After pass {i+1}: {step}")

print(f"Final sorted array: {sorted_arr}")
```

Output:
```
Original array: [23, 78, 45, 8, 32, 56]
After pass 1: [23, 45, 8, 32, 56, 78]
After pass 2: [23, 8, 32, 45, 56, 78]
After pass 3: [8, 23, 32, 45, 56, 78]
After pass 4: [8, 23, 32, 45, 56, 78]
Final sorted array: [8, 23, 32, 45, 56, 78]
```

## 34. Describe the following (i) creating list (ii) accessing values in the list (iii) updating the list (iv) deleting the list elements with example.

### (i) Creating Lists

```python
# Method 1: Using square brackets
fruits = ["apple", "banana", "cherry"]

# Method 2: Using the list() constructor
colors = list(("red", "green", "blue"))

# Method 3: Empty list
empty_list = []

# Method 4: List comprehension
squares = [x**2 for x in range(1, 6)]  # [1, 4, 9, 16, 25]

# Method 5: Using the * operator for repetition
zeros = [0] * 5  # [0, 0, 0, 0, 0]

print(f"Fruits: {fruits}")
print(f"Colors: {colors}")
print(f"Empty list: {empty_list}")
print(f"Squares: {squares}")
print(f"Zeros: {zeros}")
```

### (ii) Accessing Values in Lists

```python
numbers = [10, 20, 30, 40, 50, 60, 70]

# Access by index (zero-based)
print(f"First element: {numbers[0]}")  # 10
print(f"Third element: {numbers[2]}")  # 30

# Negative indexing (count from end)
print(f"Last element: {numbers[-1]}")  # 70
print(f"Second-to-last element: {numbers[-2]}")  # 60

# Slicing [start:end] (end is exclusive)
print(f"First three elements: {numbers[0:3]}")  # [10, 20, 30]
print(f"Elements from index 2 to 5: {numbers[2:5]}")  # [30, 40, 50]

# Slicing with step [start:end:step]
print(f"Every second element: {numbers[::2]}")  # [10, 30, 50, 70]
print(f"Reversed list: {numbers[::-1]}")  # [70, 60, 50, 40, 30, 20, 10]

# Check if element exists
if 30 in numbers:
    print("30 is in the list")
```

### (iii) Updating Lists

```python
fruits = ["apple", "banana", "cherry", "orange", "kiwi"]
print(f"Original list: {fruits}")

# Update a single element
fruits[1] = "blueberry"
print(f"After updating index 1: {fruits}")

# Update multiple elements with slicing
fruits[2:4] = ["strawberry", "mango"]
print(f"After updating slice: {fruits}")

# Append element to end of list
fruits.append("grape")
print(f"After append: {fruits}")

# Insert element at specific position
fruits.insert(2, "pineapple")
print(f"After insert: {fruits}")

# Extend list with another list
fruits.extend(["papaya", "watermelon"])
print(f"After extend: {fruits}")

# Sort list
fruits.sort()
print(f"After sorting: {fruits}")

# Reverse list
fruits.reverse()
print(f"After reversing: {fruits}")
```

### (iv) Deleting List Elements

```python
numbers = [10, 20, 30, 40, 50, 60, 70, 80, 90]
print(f"Original list: {numbers}")

# Remove by value
numbers.remove(30)
print(f"After remove(30): {numbers}")

# Remove by index using pop() - returns the removed element
removed_element = numbers.pop(2)  # Removes and returns element at index 2
print(f"Removed element: {removed_element}")
print(f"After pop(2): {numbers}")

# Remove last element
last_element = numbers.pop()
print(f"Last element removed: {last_element}")
print(f"After pop(): {numbers}")

# Remove using del statement with index
del numbers[1]
print(f"After del numbers[1]: {numbers}")

# Remove elements using del with slicing
del numbers[1:3]
print(f"After del numbers[1:3]: {numbers}")

# Clear all elements
numbers.clear()
print(f"After clear(): {numbers}")

# Delete the entire list
del numbers
try:
    print(numbers)
except NameError:
    print("List has been completely deleted and no longer exists")
```

## 35. Write a python program to multiply two matrices?

```python
def matrix_multiply(A, B):
    """
    Multiply two matrices A and B
    
    Returns the result matrix or an error message if dimensions are incompatible
    """
    # Check if matrices can be multiplied
    if len(A[0]) != len(B):
        return "Cannot multiply: Incompatible dimensions"
    
    # Initialize result matrix with zeros
    rows_A = len(A)
    cols_B = len(B[0])
    result = [[0 for _ in range(cols_B)] for _ in range(rows_A)]
    
    # Perform matrix multiplication
    for i in range(rows_A):
        for j in range(cols_B):
            for k in range(len(B)):
                result[i][j] += A[i][k] * B[k][j]
    
    return result

def print_matrix(matrix, name):
    """Print a matrix with a label"""
    print(f"{name}:")
    for row in matrix:
        print(row)
    print()

# Example matrices
A = [
    [1, 2, 3],
    [4, 5, 6]
]

B = [
    [7, 8],
    [9, 10],
    [11, 12]
]

# Print the input matrices
print_matrix(A, "Matrix A (2x3)")
print_matrix(B, "Matrix B (3x2)")

# Multiply matrices
result = matrix_multiply(A, B)

# Print the result
if isinstance(result, str):
    print(result)
else:
    print_matrix(result, "Result Matrix (2x2)")
```

Output:
```
Matrix A (2x3):
[1, 2, 3]
[4, 5, 6]

Matrix B (3x2):
[7, 8]
[9, 10]
[11, 12]

Result Matrix (2x2):
[58, 64]
[139, 154]
```

## 36. Illustrate the ways creating the tuple and the tuple assignment with suitable programs?

### Ways to Create Tuples

```python
# 1. Using parentheses with elements
coordinates = (10, 20)
print(f"Coordinates: {coordinates}")

# 2. Without parentheses (comma makes it a tuple)
person = "John", 25, "New York"
print(f"Person: {person}")

# 3. Single element tuple (needs trailing comma)
singleton = (42,)  # Without comma, it would be an int
print(f"Singleton: {singleton}, type: {type(singleton)}")

# 4. Empty tuple
empty_tuple = ()
print(f"Empty tuple: {empty_tuple}")

# 5. Using tuple() constructor
colors = tuple(["red", "green", "blue"])
print(f"Colors: {colors}")

# 6. Nested tuples
nested = (1, 2, (3, 4), 5)
print(f"Nested tuple: {nested}")

# 7. Tuple repetition
repeated = ("abc",) * 3
print(f"Repeated: {repeated}")

# 8. Tuple from range
numbers = tuple(range(5))
print(f"Numbers: {numbers}")
```

### Tuple Assignment

```python
# 1. Basic tuple assignment
point = (3, 4)
x, y = point
print(f"x = {x}, y = {y}")

# 2. Swapping values
a, b = 10, 20
print(f"Before swap: a = {a}, b = {b}")
a, b = b, a  # Tuple assignment for swapping
print(f"After swap: a = {a}, b = {b}")

# 3. Multiple assignment
first, second, third = "abc"
print(f"first = {first}, second = {second}, third = {third}")

# 4. Assign with wildcards (Python 3.x)
data = (1, 2, 3, 4, 5)
head, *middle, tail = data
print(f"head = {head}, middle = {middle}, tail = {tail}")

# 5. Nested tuple unpacking
nested_data = (1, 2, (3, 4))
a, b, (c, d) = nested_data
print(f"a = {a}, b = {b}, c = {c}, d = {d}")

# 6. Function returning tuple
def get_person_details():
    return ("Alice", 30, "Engineer")

name, age, profession = get_person_details()
print(f"Name: {name}, Age: {age}, Profession: {profession}")

# 7. Partial unpacking
points = (1, 2, 3, 4)
x, y, *rest = points
print(f"x = {x}, y = {y}, rest = {rest}")

# 8. Ignoring values with underscore
data = (10, 20, 30, 40)
first, _, third, _ = data  # Ignoring 2nd and 4th values
print(f"first = {first}, third = {third}")
```

## 37. Distinguish between files and modules?

| Files | Modules |
|-------|---------|
| Physical entities that exist on the disk | Logical entities containing Python definitions and statements |
| Can be of any type (text, binary, python, etc.) | Specifically Python files imported into other Python programs |
| Opened with `open()` function | Imported with `import` statement |
| Used for storing and retrieving data | Used for organizing code and sharing functionality |
| Primary operations: read, write, append | Primary operations: import, access functions/classes/variables |
| Examples: `data.txt`, `image.png`, `script.py` | Examples: `math`, `os`, `sys`, `random` |
| Closed explicitly with `close()` | No need to close |
| Focus on data persistence | Focus on code organization |

```python
# File handling example
file_path = "example.txt"

# Writing to a file
with open(file_path, "w") as file:
    file.write("This is an example file.\n")
    file.write("It contains multiple lines of text.\n")

# Reading from a file
with open(file_path, "r") as file:
    content = file.read()
    print("File content:")
    print(content)

# Module example
import math  # Importing a standard module

# Using functions from the module
radius = 5
area = math.pi * radius ** 2
circumference = 2 * math.pi * radius

print(f"Circle with radius {radius}:")
print(f"Area: {area:.2f}")
print(f"Circumference: {circumference:.2f}")

# Creating a custom module (saved as mymodule.py)
"""
# Content of mymodule.py
def greet(name):
    return f"Hello, {name}!"

def add(a, b):
    return a + b
"""

# Using the custom module
# import mymodule
# 
# print(mymodule.greet("Alice"))
# print(f"Sum: {mymodule.add(5, 3)}")
```

## 38. Point out different modes of file opening?

Python offers various modes for opening files:

| Mode | Description | Creates new file? | Example |
|------|-------------|-------------------|---------|
| `'r'` | Read (default) - open for reading | No | `f = open('file.txt', 'r')` |
| `'w'` | Write - open for writing, truncate file first | Yes | `f = open('file.txt', 'w')` |
| `'x'` | Exclusive creation - fail if file exists | Yes | `f = open('file.txt', 'x')` |
| `'a'` | Append - open for writing, append to end | Yes | `f = open('file.txt', 'a')` |
| `'b'` | Binary mode | - | `f = open('image.png', 'rb')` |
| `'t'` | Text mode (default) | - | `f = open('file.txt', 'rt')` |
| `'+'` | Update (reading and writing) | No | `f = open('file.txt', 'r+')` |

```python
# Examples of different file opening modes

# 1. Read mode ('r') - default
try:
    with open('example.txt', 'r') as file:
        content = file.read()
        print("Read mode content:", content)
except FileNotFoundError:
    print("File not found!")

# 2. Write mode ('w') - creates new file or truncates existing
with open('example.txt', 'w') as file:
    file.write("This file was created in write mode.\n")
    file.write("Any previous content is gone!")

# 3. Append mode ('a') - creates new file or appends to existing
with open('example.txt', 'a') as file:
    file.write("\nThis line is appended to the file.")
    file.write("\nThe original content is preserved.")

# 4. Read and Write mode ('r+') - for both reading and writing
with open('example.txt', 'r+') as file:
    content = file.read()
    print("Before modification:", content)
    file.seek(0)  # Move pointer to beginning
    file.write("Modified content!\n")  # Overwrites beginning of file

# 5. Binary mode ('b') - for non-text files
with open('binary_example', 'wb') as file:
    file.write(b'\x00\x01\x02\x03')  # Writing binary data

with open('binary_example', 'rb') as file:
    binary_data = file.read()
    print("Binary data:", binary_data)

# 6. Exclusive creation ('x') - fails if file exists
try:
    with open('new_file.txt', 'x') as file:
        file.write("This is a brand new file!")
except FileExistsError:
    print("The file already exists!")

# 7. Write and Binary mode combined ('wb')
with open('binary_data.bin', 'wb') as file:
    # Write binary data
    for i in range(10):
        file.write(bytes([i]))

# Read all modes example
print("\nFinal content of example.txt:")
with open('example.txt', 'r') as file:
    print(file.read())
```

## 39. Write a program to catch a divide by zero exception. Add a finally block too?

```python
def divide_numbers():
    try:
        # Get user input
        numerator = float(input("Enter numerator: "))
        denominator = float(input("Enter denominator: "))
        
        # Attempt the division
        result = numerator / denominator
        
        # Display the result if successful
        print(f"Result of {numerator} / {denominator} = {result}")
        
    except ZeroDivisionError:
        # Catch and handle division by zero
        print("Error: Cannot divide by zero!")
        
    except ValueError:
        # Catch and handle invalid input (e.g., if user enters text)
        print("Error: Please enter valid numbers!")
        
    finally:
        # This block always executes, regardless of whether an exception occurred
        print("Division operation attempted. Cleanup complete.")
        print("Program execution continues...")

# Run the function
print("Divide Two Numbers Program")
print("-" * 25)
divide_numbers()
```

Sample Output 1 (No Exception):
```
Divide Two Numbers Program
-------------------------
Enter numerator: 10
Enter denominator: 2
Result of 10.0 / 2.0 = 5.0
Division operation attempted. Cleanup complete.
Program execution continues...
```

Sample Output 2 (Zero Division):
```
Divide Two Numbers Program
-------------------------
Enter numerator: 10
Enter denominator: 0
Error: Cannot divide by zero!
Division operation attempted. Cleanup complete.
Program execution continues...
```

Sample Output 3 (Invalid Input):
```
Divide Two Numbers Program
-------------------------
Enter numerator: ten
Error: Please enter valid numbers!
Division operation attempted. Cleanup complete.
Program execution continues...
```

## 40. Describe in details exception handling with sample program?

```python
def comprehensive_exception_demo():
    """
    A program demonstrating various aspects of Python exception handling
    """
    print("PYTHON EXCEPTION HANDLING DEMONSTRATION")
    print("=" * 40)
    
    # 1. Basic try-except
    print("\n1. BASIC TRY-EXCEPT BLOCK")
    try:
        x = 10 / 0  # Deliberately causing an error
    except ZeroDivisionError:
        print("Caught a division by zero error")
    
    # 2. Multiple exception types
    print("\n2. CATCHING MULTIPLE EXCEPTION TYPES")
    try:
        # Choose which error to generate
        error_choice = input("Enter error type to demonstrate (1=index, 2=type, 3=value): ")
        
        if error_choice == '1':
            lst = [1, 2, 3]
            print(lst[10])  # IndexError
        elif error_choice == '2':
            x = "abc" + 123  # TypeError
        elif error_choice == '3':
            int("abc")  # ValueError
        else:
            print("No error generated")
            
    except IndexError as e:
        print(f"Caught IndexError: {e}")
    except TypeError as e:
        print(f"Caught TypeError: {e}")
    except ValueError as e:
        print(f"Caught ValueError: {e}")
    
    # 3. try-except-else-finally
    print("\n3. TRY-EXCEPT-ELSE-FINALLY STRUCTURE")
    try:
        num = float(input("Enter a number to divide 100 by: "))
        result = 100 / num
    except ZeroDivisionError:
        print("You cannot divide by zero")
    except ValueError:
        print("You must enter a valid number")
    else:
        print(f"The result is: {result}")  # Executes if no exception
    finally:
        print("This always executes, regardless of whether an exception occurred")
    
    # 4. Raising exceptions
    print("\n4. RAISING EXCEPTIONS")
    try:
        age = int(input("Enter your age: "))
        if age < 0:
            raise ValueError("Age cannot be negative")
        elif age > 120:
            raise ValueError("Age is unrealistically high")
        else:
            print(f"Your age is {age}")
    except ValueError as e:
        print(f"Invalid age: {e}")
    
    # 5. Custom exceptions
    print("\n5. CUSTOM EXCEPTIONS")
    class InsufficientFundsError(Exception):
        """Exception raised when a withdrawal exceeds available balance"""
        def __init__(self, balance, withdrawal_amount):
            self.balance = balance
            self.withdrawal_amount = withdrawal_amount
            self.message = f"Insufficient funds: balance is ${balance}, tried to withdraw ${withdrawal_amount}"
            super().__init__(self.message)
    
    def withdraw(balance, amount):
        if amount > balance:
            raise InsufficientFundsError(balance, amount)
        return balance - amount
    
    try:
        current_balance = 100
        withdrawal = float(input(f"Your balance is ${current_balance}. How much do you want to withdraw? $"))
        new_balance = withdraw(current_balance, withdrawal)
        print(f"Withdrawal successful. New balance: ${new_balance}")
    except InsufficientFundsError as e:
        print(f"Transaction failed: {e}")
    except ValueError:
        print("Please enter a valid amount")
    
    print("\n" + "=" * 40)
    print("EXCEPTION HANDLING DEMONSTRATION COMPLETE")

# Run the demonstration
if __name__ == "__main__":
    comprehensive_exception_demo()
```

Key aspects of exception handling in Python:

1. **Basic Structure**: The fundamental try-except block
2. **Exception Types**: Python has many built-in exceptions (ZeroDivisionError, TypeError, etc.)
3. **Exception Hierarchy**: Exceptions form a hierarchy with more specific exceptions inheriting from more general ones
4. **Multiple Exceptions**: Can catch different types of exceptions with multiple except blocks
5. **Exception Information**: Using `as e` captures the exception object with details
6. **try-except-else-finally**: A complete structure for handling different scenarios
7. **Raising Exceptions**: Using `raise` to trigger exceptions when conditions aren't met
8. **Custom Exceptions**: Defining application-specific exceptions
9. **Clean-up Actions**: Using `finally` for code that must execute regardless of exceptions
10. **Context Managers**: Using `with` statements for automatic resource management

## 41. Write a program to find the number of instances of different digits in a given number?

```python
def count_digits(number):
    """
    Count occurrences of each digit in a given number
    
    Args:
        number: The number to analyze
    
    Returns:
        A dictionary with digits as keys and their counts as values
    """
    # Convert the number to a string to iterate through its digits
    num_str = str(abs(number))  # Using abs() to handle negative numbers
    
    # Initialize a dictionary to store the count of each digit
    digit_counts = {str(i): 0 for i in range(10)}
    
    # Count occurrences of each digit
    for digit in num_str:
        digit_counts[digit] += 1
    
    # Remove digits with zero occurrences
    result = {digit: count for digit, count in digit_counts.items() if count > 0}
    
    return result

def display_results(number, counts):
    """Display the digit counting results in a formatted way"""
    print(f"\nAnalysis of number: {number}")
    print("-" * 30)
    print("Digit | Count")
    print("-" * 30)
    
    for digit, count in sorted(counts.items()):
        print(f"  {digit}   |   {count}")
    
    print("-" * 30)
    total_digits = sum(counts.values())
    print(f"Total: {total_digits} digits")

# Test the function with user input
try:
    user_number = int(input("Enter a number to analyze: "))
    
    # Get the digit counts
    digit_counts = count_digits(user_number)
    
    # Display the results
    display_results(user_number, digit_counts)
    
except ValueError:
    print("Please enter a valid integer number.")
```

Example output:
```
Enter a number to analyze: 1223334444

Analysis of number: 1223334444
------------------------------
Digit | Count
------------------------------
  1   |   1
  2   |   2
  3   |   3
  4   |   4
------------------------------
Total: 10 digits
```

## 42. Format conversion is an important requirement in many software applications. Hence develop an algorithm to perform the following date format conversion: Input date format: 07/21/1983 Output date format: July 21, 1983. Finally write a python script to implement the above algorithm.

```python
def convert_date_format(input_date):
    """
    Convert date from MM/DD/YYYY format to Month DD, YYYY format
    
    Args:
        input_date (str): Date in MM/DD/YYYY format (e.g., "07/21/1983")
        
    Returns:
        str: Date in Month DD, YYYY format (e.g., "July 21, 1983")
    """
    # Dictionary mapping month numbers to month names
    month_names = {
        "01": "January",
        "02": "February",
        "03": "March",
        "04": "April",
        "05": "May",
        "06": "June",
        "07": "July",
        "08": "August",
        "09": "September",
        "10": "October",
        "11": "November",
        "12": "December"
    }
    
    # Check if the input is in the expected format
    if not (len(input_date) == 10 and input_date[2] == '/' and input_date[5] == '/'):
        return "Error: Invalid date format. Please use MM/DD/YYYY format."
    
    try:
        # Split the date into components
        month, day, year = input_date.split('/')
        
        # Remove leading zeros from the day (e.g., "01" -> "1")
        day = day.lstrip('0')
        
        # Convert month number to month name
        if month in month_names:
            month_name = month_names[month]
        else:
            return "Error: Invalid month number."
        
        # Format the output date
        output_date = f"{month_name} {day}, {year}"
        
        return output_date
        
    except Exception as e:
        return f"Error: {e}"

# Main program with error handling
def main():
    print("Date Format Converter: MM/DD/YYYY to Month DD, YYYY")
    print("-" * 50)
    
    while True:
        # Get user input
        input_date = input("\nEnter date in MM/DD/YYYY format (e.g., 07/21/1983): ")
        
        # Exit condition
        if input_date.lower() == 'exit':
            print("Exiting program...")
            break
        
        # Convert the date
        result = convert_date_format(input_date)
        
        # Display the result
        print(f"Converted date: {result}")
        print("\nEnter 'exit' to quit.")

# Run the program
if __name__ == "__main__":
    main()
```

Example output:
```
Date Format Converter: MM/DD/YYYY to Month DD, YYYY
--------------------------------------------------

Enter date in MM/DD/YYYY format (e.g., 07/21/1983): 07/21/1983
Converted date: July 21, 1983

Enter 'exit' to quit.

Enter date in MM/DD/YYYY format (e.g., 07/21/1983): 12/05/2024
Converted date: December 5, 2024

Enter 'exit' to quit.

Enter date in MM/DD/YYYY format (e.g., 07/21/1983): 13/01/2000
Converted date: Error: Invalid month number.

Enter 'exit' to quit.

Enter date in MM/DD/YYYY format (e.g., 07/21/1983): exit
Exiting program...
```

## 43. Write a python program named weather that is passed a dictionary of daily temperatures and returns the average temperature over the weekend for the weekly temperatures given?

def weather(temperatures):
    """
    Calculate the average temperature over the weekend (Saturday and Sunday)
    from a dictionary of daily temperatures.
    
    Parameters:
    temperatures (dict): A dictionary with days of the week as keys and
                         temperatures as values.
    
    Returns:
    float: The average temperature over the weekend, or None if weekend
           data is not available.
    """
    weekend_days = ["Saturday", "Sunday"]
    weekend_temps = []
    
    for day in weekend_days:
        if day in temperatures:
            weekend_temps.append(temperatures[day])
    
    # If we have any weekend temperatures, calculate the average
    if weekend_temps:
        return sum(weekend_temps) / len(weekend_temps)
    else:
        return None

# Example usage
if __name__ == "__main__":
    # Sample weekly temperatures
    weekly_temps = {
        "Monday": 72,
        "Tuesday": 75,
        "Wednesday": 78,
        "Thursday": 80,
        "Friday": 81,
        "Saturday": 83,
        "Sunday": 79
    }
    
    avg_weekend_temp = weather(weekly_temps)
    
    if avg_weekend_temp is not None:
        print(f"The average weekend temperature is: {avg_weekend_temp}°F")
    else:
        print("Weekend temperature data is not available.")
