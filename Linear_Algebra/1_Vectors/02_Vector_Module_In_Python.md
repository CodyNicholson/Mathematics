# Vector Module In Python

```python
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


    def __str__(self):
        return 'Vector: {}'.format(self.coordinates)


    def __eq__(self, v):
        return self.coordinates == v.coordinates
```

In our vector module, the **initializer** (init) creates a vector based on an input list of coordinates and also sets the dimension of space that the vector lives in. We could create a vector: (1,2,3) like this:

```
my_vector = Vector([1,2,3])
```

The **str** function gives us the ability to print out the coordinates of the vector using Python's built in print function.

```
my_vector = Vector([1,2,3])
print(my_vector)
```

The above print statement would result in this output: Vector: (1, 2, 3)

The **eq** function gives us the ability to check to two vectors are equal. Recall that two vectors are equal if they have the same magnitude and direction. Here are some examples:

```
v1 = Vector([1,2,3])
v2 = Vector([1,2,3])
v3 = Vector([-1,2,3])

print(v1 == v2)
print(v1 == v3)
```

The above code will output:

```
True
False
```
