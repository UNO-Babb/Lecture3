# Lecture 3 - CYBR 2980

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
>>> x = 16
>>> x >= 0 and math.sqrt(x) < 5
True
>>> x = -20
>>> x >= 0 and math.sqrt(x) < 5
False
>>> math.sqrt(x)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: math domain error
```
The same is true with **or** statements. This time, a True statement in the first position will result in a True result. As a result, the second expression is not evaluated if the first expression is True.

There are many reasons we may want to short circuit an operation, especially if the it is a difficult or costly operation.
```
>>>
```
NEED TO FINISH THIS SECTION.
## Ranges

## Control Statements

### if-else statements

### for loops

### while loops

## Coding Bat

## Quiz
