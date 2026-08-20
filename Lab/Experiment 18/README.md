# Experiment 18: Prolog Program for a Database with Name and DOB

## Aim

To write and implement a Prolog program to create a database containing the name and date of birth of persons and retrieve the required information using queries.

## Objective

- To understand database representation in Prolog.
- To define facts using name and date of birth.
- To retrieve information using Prolog queries.
- To understand facts, predicates, and logical queries.

## Algorithm

1. Start the program.
2. Define a predicate `person(Name, DOB)`.
3. Store the name and date of birth of different persons as facts.
4. Use queries to retrieve the required information.
5. Display the matching records.
6. Stop the program.

## Flowchart

```text
                    START
                      │
                      ▼
             Create Prolog Database
                      │
                      ▼
             Store Name and DOB
                      │
                      ▼
                 Enter Query
                      │
                      ▼
             Search Database
                      │
                      ▼
              Matching Record?
                ┌─────┴─────┐
               Yes          No
                │            │
                ▼            ▼
          Display Record   No Record
                │            │
                └─────┬──────┘
                      │
                      ▼
                     STOP
```

## Pseudocode

```text
START

Define person(Name, DOB)

Store person records

READ Query

Search the database

IF matching record exists THEN
    Display Name and DOB
ELSE
    Display "No Record Found"
END IF

STOP
```

## Prolog Code

```prolog
person(lakshana, '15-05-2006').
person(rahul, '20-08-2005').
person(priya, '10-12-2006').
person(ajay, '25-03-2005').
person(anitha, '18-07-2006').

```

## Queries

### Query 1: Find the DOB of a Person

```prolog
?- person(lakshana, DOB).
```

### Output

```text
DOB = '15-05-2006'.
```

### Query 2: Find the Person with a Given DOB

```prolog
?- person(Name, '20-08-2005').
```

### Output

```text
Name = rahul.
```

### Query 3: Display All Records

```prolog
?- person(Name, DOB).
```

### Output

```text
Name = lakshana,
DOB = '15-05-2006' ;

Name = rahul,
DOB = '20-08-2005' ;

Name = priya,
DOB = '10-12-2006' ;

Name = ajay,
DOB = '25-03-2005' ;

Name = anitha,
DOB = '18-07-2006'.
```
<img width="1887" height="617" alt="image" src="https://github.com/user-attachments/assets/7494159e-f2b0-411d-b81c-c3f3f6f1734b" />


## Result

The Prolog database containing the name and date of birth of persons was successfully created, and the required information was retrieved using Prolog queries.

## Conclusion

The experiment successfully demonstrated how Prolog can be used to represent and retrieve database information using facts, predicates, and logical queries.
