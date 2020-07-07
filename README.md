## Elevator nextFloor() Function

The function `nextFloor()` computes the next floor the elevator will stop on, given
the current floor, current direction, and the current set of pressed buttons.

Example usage:

```python
nextFloor(42, UP, ['43U', '55D', '2I'])

# will return: 43
```

### Parameters
 - `currentFloor`: What floor we are passing at the moment?
 - `currentDirection`: Are we going UP or DOWN at the moment?
 - `buttonsPressed`: Which buttons have been pressed?

If there are no buttons pressed, `nextFloor` will return current floor.

The `buttonsPressed` is a list of elements, which are 
encoded in the format: `<floor number> + <command>`, 
where `<command>` is one of `U` (up), `D` (down), or `I` ("inside", for buttons inside the elevator). 

If there is no floor in the direction of the current movement of the elevator,
a `RuntimeError` is raised.
 
Please see the unit tests in `test/test_elevator.py` for more usage examples.

### Helper Functions

#### parseButtonCommand(command, currentFloor, currentDirection)
 Given an elevator button, along with current floor and direction,
 return tuple `(floor, direction)`.

 For example:
    
  - '5U' -> (5, `UP`)
  - '9I' -> (9, `<direction>`)

 In the last example, the <direction> is determined based on current
 floor and direction of the elevator — if we are moving towards the 9th floor,
 the answer will be `currentDirection`, otherwise the opposite direction.

#### isApproaching(targetFloor, currentFloor, currentDirection)
Are we approaching the target floor, given our present location and direction?
