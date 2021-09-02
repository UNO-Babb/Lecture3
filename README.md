# Lecture 3 - CIST 1600

## Objectives:
Discuss and demonstrate:
- Conditions, boolean logic, logical operators
- Ranges
- Control statements
  - if-else
  - for loops
  - while loops
- Short-circuit evaluation


## Boolean Logic
Boolean values can only be one of two states:
- True
- False

Boolean values are used to make decisions in various control structures. The most common way to create a boolean value is through a comparison.
```
>>> 10 < 15
True
>>> 10 > 15
False
>>> age = 19
>>> age >= 21
False
```

Here are some common boolean comparison operators  

| Operator | Description |
| --- | --- |
| < | Strict less than |
| > | Strict greater than |
| <= | Less than OR equal |
| >= | Greater than OR equal |
| == | Equal |
| != | Not equal |

We also join two or more boolean expressions together with **and** and **or** operators.

| Statement 1 | Statement 2 | AND | OR |
|---|---|---|---|
|True|True|True|True|
|True|False|False|True|
|False|True|False|True|
|False|False|False|False|

### Examples
```
>>> x = 5
>>> y = 10
>>> x < 10 and y > 5
True
>>> x < 10 or y < 0
True
>>> x < 10 and y < 0
False
```
## Short-circuit evaluation
Since the result of an **and** statement is only True if both the first and second elements are True, for the sake of efficiency the second part of the statement is only evaluated if the first part is True.

```
>>> age = 19
>>> hour = 23
>>> age < 18 and hour > 22
False
```
The hour is not evaluated since the first statement is False. This is often used to avoid potential errors.
```
>>> import math
>>> x = -20

>>> math.sqrt(x)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: math domain error

>>> x >= 0 and math.sqrt(x) < 5
False

>>> x = 16
>>> x >= 0 and math.sqrt(x) < 5
True
```
The same is true with **or** statements. This time, a True statement in the first position will result in a True result. As a result, the second expression is not evaluated if the first expression is True.

There are many reasons we may want to short circuit an operation, especially if the it is a difficult or costly operation.

## if-else statements
**Note: Indentation matters**
```
if <condition>:
  statement1
  statement2
  etc...
```
The indented statements will only execute if the <condition> is true.
```
x = 5
if x > 2:
  print ("The statement x > 2 is TRUE!")

print("This line happens either way.")
```
What do you do if the if condition is not true?
```
grade = input("Enter your grade: ")
grade = int(grade) #convert from string to integer

if(grade >= 70):
  print("You passed!")
else:
  print("You need to study more.")
```
What if there are multiple options?
```
if(grade >= 90):
  print("You got an A")
elif(grade > 80):
  print("You got a B")
elif(grade > 70):
  print("You got a C")
elif(grade > 60):
  print("You got a D")
else:
  print("You got a F")
  ```

## for loops
For loops in Python will iterate across a list. The variable you create for the loop will be each of the items in the list in order.
```
>>> ages = [19, 18, 22, 20]
>>> for i in ages:
      print(i)
19
18
22
20
```
### Ranges
The range function is an easy way to create a list for our loop to iterate over.  
```
range(10) -> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

>>> for i in range(10):
      print(i)
```
You can also give the range function a start, stop, and increment amount.  
```
#range(start, end, increment)
#Example
>>> for i in range(10, 20, 2):
      print(i)
```

## while loops
A while loop works like an if statement where a boolean expression will determine if the loop continues. Every loop should have 3 important things.
- Initialize a variable
- Check the variable
- Change the variable... in a way that will eventually end.  

```
>>> x = 10 #initalize
>>> while (x > 0):  #check the variable
      print(x)
      x = x - 1     #change the variable
```
Loops do not need to be determined by the value of a number, it could be a state that we are waiting to change.
```
play = "Yes" # initialize
while (play == "Yes"): # check the variable
  <some game goes here>
  play = input("Play again? (Yes/No): ") #change the variable

print("End of the game.")
```
---
### Coding Bat
[Codingbat.com](https://codingbat.com/python) is a site where you can practice small programming challenges. The functions are tested against known answers to verify that you have correctly solved each challenge. This is know as unit testing.

## Quiz
1. Based on the following information, which statements would be True?
  ```
  x = 21
  y = 9
  z = 12
  ```
  - [ ] x < y
  - [ ] x > y
  - [ ] x == y - z
  - [ ] y - z <= 0
  - [ ] z / 4 > y / 3

1. Based on the following information, which statements would be True?
  ```
  x = 21
  y = 9
  z = 12
  ```
  - [ ] x > z and x > y
  - [ ] x < z or y < z
  - [ ] z == x + y and x = y + z
  - [ ] z + x > z + y or y < x - z

1. Based on the following information, which statements would trigger a short-circuit evaluation?

  Note: not which is true or false, just short-circuit.
  ```
  lives = 3
  playAgain = "Yes"
  ```
  - [ ] lives <= 0 or playAgain == "No"
  - [ ] lives <= 0 and playAgain == "Yes"
  - [ ] playAgain == "Yes" or lives >= 0
  - [ ] playAgain == "Yes" and lives >= 0

1. Under which conditions will the code print "Guess again."
  ```
  num = input("Guess a number: ")
  num = int(num)
  if num <= 42:
    print("You win!")
  else:
    print ("Guess again.")
  ```
  - It happens every time, no matter what number the user picks.
  - Anytime the user picks the number 42.
  - Anytime the user picks a number that is not 42.
  - Anytime the user picks a number that is greater than 42.

1. For what values of time will the program respond "Time to leave."?
  ```
  if time < 900:
    print("Get ready for class.")
  elif time <= 1015:
    print("In class and loving it.")
  elif time <= 1030:
    print("Time to leave.")
  else:
    print("Enjoy the rest of your day.")
  ```
  - Anytime before 1030
  - Anytime after 1030
  - Anytime between 900 and 1015
  - Anytime between 1016 and 1030

1. What values would be output by the following code?
  ```
  for i in range(2, 9, 3):
    print(i)
  ```
  - 2, 5, 8
  - 2, 5, 8, 11
  - 2, 3, 4
  - 2, 3, 4, 5, 6, 7, 8

1. What will cause the loop to end? (select all that apply)
  ```
  guess = -1
  secret = 42
  count = 0
  while (guess != secret and count < 5):
    guess = input("Enter your guess: ")
    guess = int(guess)
    count = count + 1

  if guess == secret:
    print("You got it!")
  else:
    print("Sorry, not correct")

  ```
  - [ ] guess = 42
  - [ ] guess is not 42
  - [ ] user has fewer than 5 attempts
  - [ ] user has attempted 5 times
