# Branching and Iteration
Please start solving the following excercises in the `main.py` file.
In some questions, there is code provided, you need to copy that part to the `main.py` file.

## Q1: 
What is wrong with the example below?
```
import random
p1 = random.randint(0,10)
p2 = random.randint(0,10)

if p1 > p2:
  print("p1 is greater than p2")
else:
  print("p2 is greater or equal than p1")  
  
```

This is ok but less readable: 
```
if p1 > p2: print("p1 is greater than p2")
``` 

## Q2: `if` statement
Player with greater score wins. Who won?
Write a conditional statement for every possible case comparing two scores. Try to use both `elif` and `else`.

There is a short statement for `if...else` as well but again, less readable:

```
print("p1 is greater") if p1 > p2 else print("p2 is greater or equal")
```

## Q3: `and`, `or`

A new player enters:
```
p3 = random.randint(0,10)

```
Use logical `and, or` statements to compare score of `p3` to other two player scores `p1` and `p2`. We are especially interested in these two cases:
* if p3 is greater than both p1 and p2 or
* if p3 is greater than at least one of them.


## Q4: Nested `if`
We have all the tools to implement a Rock, Paper Scissors game. Use nested `if...else` statements to find every possible case for moves of the two players. **Hint: ** There are 9 cases in total.


```
p1 = input("Select Rock(R), Paper(P) or Scissors(S) for player 1")
p2 = input("Select Rock(R), Paper(P) or Scissors(S) for player 2")

# Enter your code here 
```

## Q5: Input Check
Make sure that the user entered the correct input, i.e. either R, P or S. Use while to keep asking the user again for input until they enter the input in the correct format.

```
p1 = input("Select Rock(R), Paper(P) or Scissors(S) for player 1")
p2 = input("Select Rock(R), Paper(P) or Scissors(S) for player 2")

# Enter your code here
```

## Q6: Empty `if`
Can an `if` statement be empty? In other words, will the code below give an error if you leave it like that?

```
if a > b:
```

## Q7: For loop
Write a program that calculates the sum of squares of first n natural numbers and displays only the odd squares along the way

```
n = int(input("Enter n: "))

```