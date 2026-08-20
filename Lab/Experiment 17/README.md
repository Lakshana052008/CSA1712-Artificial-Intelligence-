# Experiment 17: Program to Sum the Integers from 1 to n

## Aim

To write and implement a Python program to calculate the sum of all integers from 1 to N using an iterative approach.

## Objective

- To understand the use of iteration in Python.
- To calculate the sum of a sequence of integers.
- To implement a program using loops and conditional statements.
- To analyze the input and generate the required output.

## Algorithm

1. Start the program.
2. Read the value of N from the user.
3. Check whether N is a positive integer.
4. If N is less than 1, display an appropriate message.
5. Otherwise, initialize `sum = 0`.
6. Set the counter `i = 1`.
7. Add the value of `i` to `sum`.
8. Increment `i` by 1.
9. Repeat Steps 7 and 8 until `i` becomes greater than N.
10. Display the sum of integers from 1 to N.
11. Stop the program.

## Flowchart

```text
                         START
                           │
                           ▼
                      Enter N
                           │
                           ▼
                       N < 1 ?
                     ┌─────┴─────┐
                    Yes          No
                     │            │
                     ▼            ▼
              Display Invalid   sum = 0
                  Input          i = 1
                     │            │
                     ▼            ▼
                    STOP        i <= N ?
                              ┌────┴────┐
                             Yes       No
                              │         │
                              ▼         ▼
                        sum = sum + i  Display Sum
                              │         │
                              ▼         ▼
                          i = i + 1     STOP
                              │
                              └──────► Repeat
```

## Pseudocode

```text
START

READ N

IF N < 1 THEN
    DISPLAY "Enter a positive integer"
ELSE
    sum ← 0
    i ← 1

    WHILE i ≤ N DO
        sum ← sum + i
        i ← i + 1
    END WHILE

    DISPLAY "Sum =", sum
END IF

STOP
```

## Python Code

```python
n = int(input("Enter a positive integer N: "))

if n < 1:
    print("Please enter a positive integer.")
else:
    total = 0

    for i in range(1, n + 1):
        total += i

    print("Integers from 1 to", n, "are summed.")
    print("Sum of integers from 1 to", n, "is:", total)
```

## Output

```text
Enter a positive integer N: 10
Integers from 1 to 10 are summed.
Sum of integers from 1 to 10 is: 55
```
<img width="1397" height="383" alt="image" src="https://github.com/user-attachments/assets/4c4fefab-57cb-47ec-b1bf-c80f7d9cf314" />


## Result

The Python program was successfully implemented to calculate the sum of all integers from 1 to N using an iterative approach.

## Conclusion

The program successfully demonstrates the use of loops, counters, conditional statements, and accumulation to calculate the sum of consecutive integers. The program also handles invalid input by checking whether N is a positive integer.
