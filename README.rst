========
geometry
========
Python geometry library
by Gareth Rees <http://garethrees.org/>


Introduction
------------
**geometry** is a library containing a pure-Python implementation of vectors.


Requirements
------------
1. It must be possible to create and manipulate vectors of any dimension via the interface: there must be no segregation of 2- or 3-dimensional vectors into their own classes. (This makes it straightforward to write code that's agnostic about the number of dimensions: for example a line/circle intersection algorithm that is re-usable for line/sphere intersection.)

2. Vectors must be agnostic as to the representation of scalars (where possible), so that users can carry out many kinds of computation on vectors of integers, fractions, decimals, and other numeric types, and get back vectors with elements of the same type. (Obviously this isn't possible for methods that needs to compute the magnitude of the vector, or to use trigonometry, but it must work for simple arithmetic operations.)

3. There must be no arbitrary distinctions between points and vectors. It's up to the user to decide what kind of thing a vector represents.

4. There must be no dependencies on Numpy or other third-party libraries: the implementation must be in pure Python.

4. The code must be portable between Python 2.7 and Python 3.2+.

5. Vector objects must be immutable, so that they can be stored in sets and used as keys in dictionaries.

6. Vector objects must be capable of being combined with other kinds of sequence, without the iterable needing to be converted. It must be possible to write code like ``v + (1, 0, 0)`` instead of the fussy ``v + Vector(1, 0, 0)``.

7. Programming mistakes like the addition of two vectors with different dimensions must be detected and raised as exceptions where possible.


Other design notes
------------------
1. The term *magnitude* is used for the Euclidean norm; the term *length* is avoided because in Python that's too easily confused with the ``len()`` of the vector, that is, its *dimension*.


License
-------
This program is free software; you can redistribute it and/or modify
it under the terms of the `GNU General Public License`_ as published by
the `Free Software Foundation`_; either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the `GNU
General Public License`_ for more details.

.. _GNU General Public License: http://www.gnu.org/copyleft/gpl.html
.. _Free Software Foundation: http://www.fsf.org/

