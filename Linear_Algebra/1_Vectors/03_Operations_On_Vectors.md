# Operations On Vectors

### Addition

One way to visualize the sum of two vectors is to lay them end-to-end. The arrow formed by starting at the beginning of the first arrow and ending at the end of the second array gives the overall amount of change by the two vectors. For example: Vector1 = (2,3) and Vector2 = (3,-4). We will now add Vector1 and Vector2. Since Vector1 starts at (0,0), our SumVector will start at (0,0). Then we start Vector2 at the end of Vector1: (2,3). Vector2 goes right by 3 and down by 4, so we end up with (5,-1). Our SumVector is equal to (5,-1) - assuming that we start from the origin.

We can add vectors more easily using the numeric representation:

```
Vector1:  Vector2:  SumVector:
 [ 2 ]  +  [ 3 ]   =  [ 5 ]
 [ 3 ]  +  [ -4 ]  =  [ -1 ]
```

### Subtraction

Assume we have two vectors: (2,5) and (1,2). To subtract them graphically, we look at the distance from the end of our second vector (2,5) to the end of our first vector (1,2). In our case, this would be (-1,-3).

Numerically we can represent this as:

```
Vector1:  Vector2:  DiffVector:
 [ 2 ]  -  [ 1 ]   =  [ -1 ]
 [ 5 ]  -  [ 2 ]   =  [ -3 ]
```

### Scalar Multiplication

In this case, a vector is multiplied by a number that we call a **scalar**. Multiplying a vector by 2 doubles its length. Multiplying a vector by 1 keeps it at the same length. Multiplying a vector by 1/2 cuts its length in half.

We can also multiply our vector by a negative number. This reverses the direction the arrow points in addition to possibly growing or shrinking the vector.

Numerically, scalar multiplication is computed by multiplying each coordinate of the vector by the scalar like so:

```
Vector1:
 [ 3 ]
 [ 9 ]
                          ProductVector:
2 * Vector1 = 2 * [ 3 ] =    [ 6 ]
              2 * [ 9 ] =    [ 18 ]
```

***

## Python Implementation Of Operations

```
class Vector(object):
    def __init__(self, coordinates):
        try:
            if not coordinates:
                raise ValueError
            self.coordinates = tuple(coordinates)
            self.dimension = len(coordinates)

        except ValueError:
            raise ValueError('The coordinates must be nonempty')

        except TypeError:
            raise TypeError('The coordinates must be an iterable')

    def plus(self, v):
        new_coords = [x+y for x,y in zip(self.coordinates, v.coordinates)]
        return Vector(new_coords)

    def minus(self, v):
        new_coords = [x-y for x,y in zip(self.coordinates, v.coordinates)]
        return Vector(new_coords)

    def times_scalar(self, c):
        new_coords = [c*x for x in self.coordinates]
        return Vector(new_coords)

    def __str__(self):
        return 'Vector: {}'.format(self.coordinates)

    def __eq__(self, v):
        return self.coordinates == v.coordinates
```
