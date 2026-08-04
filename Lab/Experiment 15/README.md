# Experiment 15: Implementation of Decision Tree Algorithm

## Aim

To implement the Decision Tree Algorithm in Python for classification.

## Objective

- To understand the working of the Decision Tree Algorithm.
- To implement a Decision Tree classifier using Python.
- To train the model using a dataset.
- To predict the class labels for test data.

## Algorithm

1. Start the program.
2. Import the required libraries.
3. Load the dataset.
4. Split the dataset into training and testing sets.
5. Create the Decision Tree classifier.
6. Train the classifier using the training data.
7. Predict the class labels for the test data.
8. Evaluate the model accuracy.
9. Display the predictions and accuracy.
10. Stop the program.

## Flowchart

```text
                  START
                    │
                    ▼
        Import Required Libraries
                    │
                    ▼
             Load Dataset
                    │
                    ▼
      Split Data into Train & Test
                    │
                    ▼
      Create Decision Tree Model
                    │
                    ▼
            Train the Model
                    │
                    ▼
          Predict Test Output
                    │
                    ▼
          Calculate Accuracy
                    │
                    ▼
          Display the Result
                    │
                    ▼
                   STOP
```

## Python Code

```from sklearn.tree import DecisionTreeClassifier

X = [[0], [1], [2], [3]]
Y = [0, 0, 1, 1]

model = DecisionTreeClassifier()

model.fit(X, Y)

print(model.predict([[1.5]]))
```

## Output

```
[0]
```
<img width="1600" height="848" alt="image" src="https://github.com/user-attachments/assets/e975ccb6-4ce3-4d39-ab5c-0d9d4c212703" />


## Result

The Decision Tree Algorithm was successfully implemented in Python, and the classifier accurately predicted the class labels for the test dataset.

## Conclusion

The Decision Tree Algorithm successfully classified the given dataset by learning decision rules from the training data. It is simple to understand, easy to implement, and widely used for classification and prediction tasks in machine learning.
