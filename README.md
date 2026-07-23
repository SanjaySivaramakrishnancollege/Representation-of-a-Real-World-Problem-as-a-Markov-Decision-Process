## Exp-1
# MDP REPRESENTATION ->
## AIM:
To design an MDP representation for a delivery drone navigating a city to deliver a parcel to a customer's address.

## PROBLEM STATEMENT:
The MDP representation of a delivery drone that must fly from a pickup hub, collect a parcel, and navigate through city airspace to reach a customer's delivery address while avoiding no-fly zones (restricted obstacle regions).

### Problem Description
To deliver a parcel from the hub (pickup point) to the customer's delivery address while avoiding no-fly zones in the city airspace.

### State Space
```
I.   The drone's current position.
II.  The location of the parcel pickup hub.
III. The customer's delivery address (goal position).
IV.  The positions of no-fly zones (obstacles) in the city.
```

### Sample State
```
1. The drone is at position 1.
2. The parcel pickup hub is at position 3.
3. The delivery address is at position 4.
4. No-fly zones (obstacles) are at positions 2.
```

### Action Space
```
0   ->>  Hover (Same State)
1   ->>  Left
2   ->>  Down
3   ->>  Right
4   ->>  Up
```

### Sample Action
0 -> 3 -> 3 -> 1

### Reward Function
```
1. +1 for successfully delivering the parcel to the delivery address.
2. 0 for hovering, hitting a no-fly zone, or being at the start/pickup state.
```

### Graphical Representation
*(Insert the state-transition diagram image here, showing positions 1–4 with the drone's path from hub to delivery address, marking the no-fly zone.)*

## PYTHON REPRESENTATION:
```python
p = {
    1: {
        0: [(1, 1, 0, False)],
        1: [(1, 1, 0, False)],
        2: [(0.7, 3, 0, True), (0.3, 2, 0, False)],
        3: [(0.3, 2, 0, False), (0.7, 3, 0, True)],
        4: [(1, 1, 0, False)]
    },
    2: {
        0: [(1, 2, 0, True)],
        1: [(1, 2, 0, True)],
        2: [(1, 2, 0, True)],
        3: [(1, 2, 0, True)],
        4: [(1, 2, 0, True)]
    },
    3: {
        0: [(1, 3, 0, False)],
        1: [(1, 3, 0, False)],
        2: [(1, 3, 0, False)],
        3: [(0.98, 4, 1, True), (0.7, 1, 0, False)],
        4: [(0.7, 1, 0, False), (0.98, 4, 1, True)]
    },
    4: {
        0: [(1, 4, 0, True)],
        1: [(1, 4, 0, True)],
        2: [(1, 4, 0, True)],
        3: [(1, 4, 0, True)],
        4: [(1, 4, 0, True)]
    }
}
```

## OUTPUT:


## RESULT:
Thus, the MDP representation of a delivery drone navigating a city to deliver a parcel to a customer's address, while avoiding no-fly zones and minimizing flight time, is successfully executed.
