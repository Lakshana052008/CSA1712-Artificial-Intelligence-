# Experiment 19: Prolog Program for Student-Teacher-Subject-Code Database

## Aim

To write and implement a Prolog program to create a database containing student, teacher, subject, and subject code information and retrieve the required details using queries.

## Objective

- To understand database representation using Prolog.
- To store student, teacher, subject, and subject code as facts.
- To retrieve related information using Prolog rules.
- To understand facts, predicates, and logical relationships.

## Algorithm

1. Start the program.
2. Define facts for students, teachers, subjects, and subject codes.
3. Define a predicate to relate the student, teacher, subject, and code.
4. Search the database using the defined relationship.
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
       Store Student, Teacher & Subject
                      │
                      ▼
              Store Subject Code
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

Define student, teacher, subject and code facts

Define relationship between them

Search the database

IF matching record exists THEN
    Display the record
ELSE
    Display "No Record Found"
END IF

STOP
```

## Prolog Code

```prolog
student(lakshana).
student(rahul).
student(priya).

teacher(raj).
teacher(kumar).
teacher(anitha).

subject(ai).
subject(dbms).
subject(networks).

subject_code(ai, 'CSA11712').
subject_code(dbms, 'CSA11713').
subject_code(networks, 'CSA11714').

teaches(raj, ai).
teaches(kumar, dbms).
teaches(anitha, networks).

studies(lakshana, ai).
studies(rahul, dbms).
studies(priya, networks).

student_details(Student, Teacher, Subject, Code) :-
    student(Student),
    studies(Student, Subject),
    teaches(Teacher, Subject),
    subject_code(Subject, Code).

main :-
    write('Student - Teacher - Subject - Code Database'), nl,
    write('--------------------------------------------'), nl,
    student_details(Student, Teacher, Subject, Code),
    write('Student: '), write(Student),
    write(', Teacher: '), write(Teacher),
    write(', Subject: '), write(Subject),
    write(', Code: '), write(Code), nl,
    fail.

main.

:- initialization(main).
```

## Output

```text
Student - Teacher - Subject - Code Database
--------------------------------------------
Student: lakshana, Teacher: raj, Subject: ai, Code: CSA11712
Student: rahul, Teacher: kumar, Subject: dbms, Code: CSA11713
Student: priya, Teacher: anitha, Subject: networks, Code: CSA11714
```
<img width="1887" height="891" alt="image" src="https://github.com/user-attachments/assets/7b793e9b-fce6-41d7-8d9d-0a302d0c7fc4" />


## Result

The Prolog program was successfully implemented to create and retrieve student, teacher, subject, and subject code information.

## Conclusion

The experiment successfully demonstrated the use of Prolog facts, rules, predicates, and relationships to represent and retrieve information from a simple database.
