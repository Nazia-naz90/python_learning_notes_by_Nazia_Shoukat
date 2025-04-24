# 🐍 Python Learning Notes (From Basics to Advanced) 📚

## 🚀 1. Python Basics

### 🖨️ 1.1 Printing & Memory Check
**Explanation:**  
The `print()` function outputs text to the console. `id()` returns the unique memory address identifier for an object, useful for debugging object references.

### 💬 1.2 Comments
**Explanation:**  
Comments are non-executable text that document code. Single-line comments use `#`, while multi-line comments use triple quotes `"""`. Comments help explain complex logic and improve code maintainability.

### 🔢 1.3 Data Types & Variables
**Explanation:**  
Variables store data of specific types:
- **Primitive Types:** `int` (whole numbers), `float` (decimals), `str` (text), `bool` (True/False)
- **Collection Types:** `list` (mutable sequence), `tuple` (immutable sequence), `set` (unique unordered), `dict` (key-value pairs)

### ➕➖ 1.4 Operators
**Explanation:**  
Operators perform operations on variables:
- **Arithmetic:** `+`, `-`, `*`, `/`, `**` (exponent), `//` (floor division), `%` (modulus)
- **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=` (return True/False)
- **Logical:** `and`, `or`, `not` (combine conditions)
- **Membership:** `in`, `not in` (check if value exists in collection)
- **Identity:** `is`, `is not` (compare object memory addresses)

### ⌨️ 1.5 Input from User
**Explanation:**  
`input()` reads user input as a string. Always convert to the desired type (e.g., `int(input())` for numbers). Example:
```python
age = int(input("Enter your age: "))
📜 2. Strings & String Methods
Explanation:
Strings are immutable sequences of Unicode characters. Essential methods:

Case Conversion: .upper(), .lower(), .title()

Searching: .find(), .index(), .count()

Manipulation: .replace(), .split(), .join()

Validation: .isalpha(), .isdigit(), .isalnum()

📋 3. Lists (Dynamic Arrays)
Explanation:
Ordered, mutable collections that can hold mixed data types. Key operations:

python
colors = ["red", "green"]
colors.append("blue")  # Add to end
colors.insert(1, "yellow")  # Insert at index
colors.pop()  # Remove last item
colors[0] = "orange"  # Modify by index
🔁 4. Loops
🔄 4.1 For Loop
Explanation:
Iterates over sequences (lists, strings, ranges). The range() function generates number sequences:

python
for i in range(3):  # 0, 1, 2
    print(i)
⏳ 4.2 While Loop
Explanation:
Executes code block while condition is True. Requires manual counter increment:

python
count = 0
while count < 3:
    print(count)
    count += 1  # Don't forget this!
📦 5. Tuples
Explanation:
Immutable sequences used for fixed data. Faster than lists and can be dictionary keys:

python
coordinates = (10.5, 20.3)
single_item = ("hello",)  # Note trailing comma
🧩 6. Sets
Explanation:
Unordered collections of unique elements. Ideal for membership tests and math operations:

python
primes = {2, 3, 5, 7}
primes.add(11)  # Add element
primes.discard(2)  # Remove safely
📖 7. Dictionaries
Explanation:
Key-value pairs with O(1) lookup time. Keys must be immutable (strings, numbers, tuples):

python
person = {
    "name": "Alice",
    "age": 30,
    "skills": ["Python", "SQL"]
}
print(person.get("age", 0))  # Safe access
🎯 8. Comprehensions
Explanation:
Concise syntax for creating collections:

python
# List comprehension
squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]

# Dict comprehension
square_dict = {x: x**2 for x in range(3)}  # {0:0, 1:1, 2:4}

# Set comprehension
unique_lengths = {len(x) for x in ["a", "bb", "ccc"]}  # {1, 2, 3}
λ 9. Lambda & Functional Tools
Explanation:

Lambda: Anonymous one-line functions:

python
square = lambda x: x**2
Map: Apply function to all items:

python
list(map(str.upper, ["a", "b"]))  # ['A', 'B']
Filter: Select items meeting condition:

python
list(filter(lambda x: x>0, [-1, 0, 1]))  # [1]
📌 10. Functions
Explanation:
Reusable code blocks with parameters and return values. Use type hints for better documentation:

python
def calculate_tax(income: float, rate: float = 0.15) -> float:
    """Calculate tax based on income and rate (default 15%)"""
    return income * rate
📂 11. Modules & Imports
Explanation:
Organize code into reusable files:

python
# my_module.py
def greet(name):
    return f"Hello, {name}!"

# main.py
from my_module import greet
print(greet("World"))
❌ 12. Error Handling
Explanation:
Gracefully handle exceptions with try/except/finally:

python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("Cleanup code here")
🏗️ 13. OOP Concepts
🧱 13.1 Classes & Objects
Explanation:
Classes define object blueprints. __init__ initializes object state:

python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
🔄 13.2 Inheritance
Explanation:
Child classes inherit and extend parent class functionality:

python
class Square(Rectangle):
    def __init__(self, side):
        super().__init__(side, side)
🔒 13.3 Encapsulation
Explanation:
Control access using private attributes (__var) and properties:

python
class Account:
    def __init__(self):
        self.__balance = 0
    
    @property
    def balance(self):
        return self.__balance
📁 14. File Handling
Explanation:
Read/write files safely using context managers:

python
# Writing
with open("data.txt", "w") as f:
    f.write("Hello\nWorld")

# Reading
with open("data.txt") as f:
    lines = f.readlines()  # ['Hello\n', 'World']
🚀 15. Advanced Topics
✨ 15.1 Decorators
Explanation:
Modify function behavior without changing its code:

python
def log_time(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        print(f"Time: {time.time()-start}s")
        return result
    return wrapper

@log_time
def slow_function():
    time.sleep(1)
⚡ 15.2 Generators
Explanation:
Memory-efficient iterators using yield:

python
def fibonacci(limit):
    a, b = 0, 1
    while a < limit:
        yield a
        a, b = b, a+b

list(fibonacci(100))  # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
⏳ 16. Async/Await
Explanation:
Write concurrent code for I/O-bound tasks:

python
import asyncio

async def fetch_data():
    await asyncio.sleep(1)  # Simulate API call
    return "Data"

async def main():
    result = await fetch_data()
    print(result)

asyncio.run(main())
🎁 17. Unpacking
Explanation:
Assign multiple variables from collections:

python
# Tuple unpacking
x, y = (10, 20)

# Dictionary unpacking
params = {"a": 1, "b": 2}
print("{a} {b}".format(**params))  # "1 2"

# Extended unpacking
first, *rest = [1, 2, 3, 4]  # first=1, rest=[2,3,4]
🎉 Happy Coding! 🎉
