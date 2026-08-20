# Experiment 16: Implementation of Feed Forward Neural Network

## Aim

To implement a Feed Forward Neural Network in Python using the sigmoid activation function.

## Objective

- To understand the working of a Feed Forward Neural Network.
- To perform forward propagation using inputs, weights, and bias.
- To apply the sigmoid activation function.
- To predict the output class.

## Algorithm

1. Start the program.
2. Define the sigmoid activation function.
3. Initialize the input values.
4. Initialize the weights and bias.
5. Calculate the weighted sum of inputs.
6. Apply the sigmoid activation function.
7. Compare the output with the threshold value.
8. Display the predicted class.
9. Stop the program.

## Flowchart

```text
                    START
                      │
                      ▼
          Define Sigmoid Function
                      │
                      ▼
             Initialize Inputs
                      │
                      ▼
          Initialize Weights & Bias
                      │
                      ▼
        Calculate Weighted Sum
                      │
                      ▼
        Apply Sigmoid Activation
                      │
                      ▼
             Output >= 0.5?
                ┌─────┴─────┐
               Yes          No
                │            │
                ▼            ▼
         Predicted Class  Predicted Class
               1               0
                │            │
                └──────┬─────┘
                       │
                       ▼
                  Display Output
                       │
                       ▼
                      STOP
```

## Python Code

```python
import math

def sigmoid(x):
    return 1 / (1 + math.exp(-x))

# Input values
inputs = [0.5, 0.8]

# Weights and bias
w1 = 0.4
w2 = 0.6
bias = 0.1

# Feed Forward calculation
net = inputs[0] * w1 + inputs[1] * w2 + bias
output = sigmoid(net)

print("Input:", inputs)
print("Output:", round(output, 4))

if output >= 0.5:
    print("Predicted Class: 1")
else:
    print("Predicted Class: 0")
```

## Output

```text
Input: [0.5, 0.8]
Output: 0.6964
Predicted Class: 1
```
<img width="1377" height="691" alt="image" src="https://github.com/user-attachments/assets/b1068f47-6b4d-454a-bf15-f950ba1d148e" />


## Result

The Feed Forward Neural Network was successfully implemented in Python using the sigmoid activation function, and the predicted class was obtained.

## Conclusion

The Feed Forward Neural Network successfully performed forward propagation by calculating the weighted sum and applying the sigmoid activation function. The network produced an output of 0.6964 and classified the input as Class 1.
