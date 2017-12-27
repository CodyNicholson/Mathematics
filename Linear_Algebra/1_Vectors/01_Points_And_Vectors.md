# Points And Vectors

A **point** is a location in space written as: (x, y, z, ...). A **point** can have many dimensions denoted by the amount of coordinates you define your point with.

A **vector** is an object representing a change in position. In Euclidean space, a vector can be thought of as an arrow connecting two points. The **magnitude** of a vector is the length of the arrow with direction. A **vector** can be written as:

```
[ x ]
[ y ]
[ z ]
[ ... ] 
```

If a **vector** goes from point (0,0) to (1,3) then we can represent our vector as:

```
[ 3 ]
[ 1 ]
```

Since the **vector** goes 3 units to the right (x) and 1 unit up (y).

Two **vectors** are equal if they represent the same amount of change in each direction. So a vector going from (0,0) to (1,2) is equal to a vector going from (5,8) to (6,10) since both vectors go over 1 unit and up 2 units.

Two points are only equal if they are located in the same place

In linear algebra we sometimes conflate the notion of a point in a vector by assuming that the vector starts at the origin and goes to the point. So I could say I have a vector and represent it as a point (2,5), and by assuming the vector starts at (0,0) and goes to that point you would be able to tell that the vector goes over 2 units and up 5 units.
