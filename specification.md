# nextFloor

Write a function nextFloor with the following signature:

```
nextFloor(currentFloor, currentDirection, buttonsPressed)
```

```
nextFloor :: int, direction, buttons -> int
direction :: <<define at will (boolean, string, enum,...)>>
buttons :: list[button]  // where list is just the name of an abstraction; use whatever makes sense in your language
button :: <<define at will; should be capable of representing button pressings as described below>>
```

The input parameters represent the floor the elevator is currently at, the direction in which it is moving and the buttons that have been pressed (and not yet been responded to)

The function should model the behavior of a real life elevator, e.g:
 - if elevator is going up and a button to go down is pressed the elevator won't change direction until all requests going in the original direction are served
 - if a 'down' button is pressed while the elevator is going 'up' the elevator won't stop until it has served all requests going in the 'up' direction
 - etc

The available buttons are:
 - within elevator: 1..N (where N is the number of floors in the building)
 - outside of elevator: UP, DOWN (one pair per floor)

## Examples

to simplify things, let's assume that buttons and directions are represented by strings:

 - '7U' -> 7th floor up button
 - '5D' -> 5th floor down button
 - '1I' -> 1st floor button (inside elevator)
 
 - 'U' -> going up
 - 'D' -> going down

 1. nextFloor(1, 'U', ['5D']) -> 5
 2. nextFloor(1, 'U', ['5D', '3U']) -> 3


## Evaluation criteria (from most to least important)

 1. Code that runs and does what is expected to do
 2. Code that is easy to read and understand
 3. Code that is easy to test

(notice that there's nothing in the list about design patterns, architecture, extensibility, etc)


Please include a README with instructions on how to run/test with your solution.
