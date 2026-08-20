# Experiment 20: Prolog Program for Planets Database

## Aim

To write and implement a Prolog program to create a database containing information about planets and retrieve the required details using Prolog.

## Objective

- To understand database representation in Prolog.
- To store planet information as facts.
- To retrieve planet details using predicates.
- To understand facts, rules, and logical queries in Prolog.

## Algorithm

1. Start the program.
2. Define facts containing the names of planets and their properties.
3. Store information such as planet type and number of moons.
4. Define a predicate to display the planet information.
5. Search the database using the defined predicate.
6. Display the matching records.
7. Stop the program.

## Flowchart

```text
                    START
                      │
                      ▼
             Create Planet Database
                      │
                      ▼
              Store Planet Facts
                      │
                      ▼
             Define Planet Predicate
                      │
                      ▼
              Search the Database
                      │
                      ▼
             Display Planet Details
                      │
                      ▼
                     STOP
```

## Pseudocode

```text
START

Define planet facts
Define planet type
Define number of moons

Search the planet database

FOR each planet
    Display planet details
END FOR

STOP
```

## Prolog Code

```prolog
planet(mercury, terrestrial, 0).
planet(venus, terrestrial, 0).
planet(earth, terrestrial, 1).
planet(mars, terrestrial, 2).
planet(jupiter, gas_giant, 95).
planet(saturn, gas_giant, 146).
planet(uranus, ice_giant, 28).
planet(neptune, ice_giant, 16).

main :-
    write('PLANETS DATABASE'), nl,
    write('-----------------'), nl,
    planet(Name, Type, Moons),
    write('Planet: '), write(Name),
    write(', Type: '), write(Type),
    write(', Moons: '), write(Moons), nl,
    fail.

main.

:- initialization(main).
```

## Output

```text
PLANETS DATABASE
-----------------
Planet: mercury, Type: terrestrial, Moons: 0
Planet: venus, Type: terrestrial, Moons: 0
Planet: earth, Type: terrestrial, Moons: 1
Planet: mars, Type: terrestrial, Moons: 2
Planet: jupiter, Type: gas_giant, Moons: 95
Planet: saturn, Type: gas_giant, Moons: 146
Planet: uranus, Type: ice_giant, Moons: 28
Planet: neptune, Type: ice_giant, Moons: 16
```
<img width="1681" height="583" alt="image" src="https://github.com/user-attachments/assets/18c08e50-293e-48e6-a955-b488e7197d75" />


## Result

The Prolog program was successfully implemented to create a planets database and display the stored information.

## Conclusion

The experiment successfully demonstrated how Prolog facts and predicates can be used to represent and retrieve information from a planets database.
