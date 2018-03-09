Please install `termcolor`, use
```
sudo pip install termcolor
```
on ubuntu like systems.

Example 1
=========

```
In [1]: l1 = Eq(x + y + z, 2); l2 = Eq(x + y + 2*z, 2); l3 = Eq(x + 2*y + z, 3); l4 = Eq(2*x + y + z, 4)

In [2]: solve([l1, l2, l3, l4])
Given system has more equations than unknown.
	Try to get augmented matrix Matrix([[1, 1, 1, 2], [1, 1, 2, 2], [1, 2, 1, 3], [2, 1, 1, 4]]) in row-echolen form. Currently matrix is:
	------------------------------------------------------------------------
⎡1  1  1  2⎤
⎢          ⎥
⎢1  1  2  2⎥
⎢          ⎥
⎢1  2  1  3⎥
⎢          ⎥
⎣2  1  1  4⎦


	For 1 th row.
	-------------
	Row 1 contains the pivot element.
	Divide all the elements in the current row by the pivot element = 1. ------>
⎡1  1  1  2⎤
⎢          ⎥
⎢1  1  2  2⎥
⎢          ⎥
⎢1  2  1  3⎥
⎢          ⎥
⎣2  1  1  4⎦
	Subtract 1 times row 1 from row 2. --------------->
⎡1  1  1  2⎤
⎢          ⎥
⎢0  0  1  0⎥
⎢          ⎥
⎢1  2  1  3⎥
⎢          ⎥
⎣2  1  1  4⎦


	Subtract 1 times row 1 from row 3. --------------->
⎡1  1  1  2⎤
⎢          ⎥
⎢0  0  1  0⎥
⎢          ⎥
⎢0  1  0  1⎥
⎢          ⎥
⎣2  1  1  4⎦


	Subtract 2 times row 1 from row 4. --------------->
⎡1  1   1   2⎤
⎢            ⎥
⎢0  0   1   0⎥
⎢            ⎥
⎢0  1   0   1⎥
⎢            ⎥
⎣0  -1  -1  0⎦


	For 2 th row.
	-------------
	The current column has no pivot element, so try to find one in other columns.
	Row 2 contains the pivot element.
	Divide all the elements in the current row by the pivot element = 1. ------>
⎡1  1   1   2⎤
⎢            ⎥
⎢0  1   0   0⎥
⎢            ⎥
⎢0  0   1   1⎥
⎢            ⎥
⎣0  -1  -1  0⎦
	Subtract -1 times row 2 from row 4. --------------->
⎡1  1  1   2⎤
⎢           ⎥
⎢0  1  0   0⎥
⎢           ⎥
⎢0  0  1   1⎥
⎢           ⎥
⎣0  0  -1  0⎦


	For 3 th row.
	-------------
	Row 3 contains the pivot element.
	Divide all the elements in the current row by the pivot element = 1. ------>
⎡1  1  1   2⎤
⎢           ⎥
⎢0  1  0   0⎥
⎢           ⎥
⎢0  0  1   1⎥
⎢           ⎥
⎣0  0  -1  0⎦
	Subtract -1 times row 3 from row 4. --------------->
⎡1  1  1  2⎤
⎢          ⎥
⎢0  1  0  0⎥
⎢          ⎥
⎢0  0  1  1⎥
⎢          ⎥
⎣0  0  0  1⎦


	For 4 th row.
	-------------
	Since the given system has = 4 equations and 3 unknowns.
	=>	The system of equations is overdetermined.
	Since in the right-hand side we have non-zero value.
	=>	The given system has no solution.
Out[2]: []
```



Example 2
=========

```
In [3]: l1 = Eq(x + y + z, 6)
   ...: l2 = Eq(x + 2*y - z, 2)
   ...: l3 = Eq(x + y - z, 0)
   ...: solve([l1, l2, l3])
   ...: 
	This system of equations is equivalent to solving.
	AX = b where,
	A = Matrix([[1, 1, 1], [1, 2, -1], [1, 1, -1]]), X = Matrix([[x], [y], [z]]) and b = Matrix([[6], [2], [0]]).
	Since the inverse of A exists.
	=>	The given system of equations is well behaved.
	=>	A**-1 = Matrix([[1/2, -1, 3/2], [0, 1, -1], [1/2, 0, -1/2]]).


	The solution of which is given by X = A**-1 * b
	Substitute values of A and b from above we get,
	=>	Matrix([[x], [y], [z]]) = Matrix([[1, 1, 1], [1, 2, -1], [1, 1, -1]])**-1 * Matrix([[6], [2], [0]])
					= Matrix([[1], [2], [3]])


		Hence x = 1, y = 2, z = 3, is the unique solution.
```



Example 3
=========

```
In [1]: a, b, c, d = symbols('a b c d')

In [2]: l1 = Eq(a + b + c + d, 2)

In [3]: l2 = Eq(a + 2*b + c + d, 4)

In [4]: solve([l1, l2])
	Try to get augmented matrix Matrix([[1, 1, 1, 1, 2], [1, 2, 1, 1, 4]]) in row-echolen form. Currently matrix is:
	------------------------------------------------------------------------
⎡1  1  1  1  2⎤
⎢             ⎥
⎣1  2  1  1  4⎦


	For 1 th row.
	-------------
	Row 1 contains the pivot element.
	Divide all the elements in the current row by the pivot element = 1. ------>
⎡1  1  1  1  2⎤
⎢             ⎥
⎣1  2  1  1  4⎦
	Subtract 1 times row 1 from row 2. --------------->
⎡1  1  1  1  2⎤
⎢             ⎥
⎣0  1  0  0  2⎦


	For 2 th row.
	-------------
	Row 2 contains the pivot element.
	Divide all the elements in the current row by the pivot element = 1. ------>
⎡1  1  1  1  2⎤
⎢             ⎥
⎣0  1  0  0  2⎦
	Augmented matrix is now in row-echelon form and equals:
			Matrix([[1, 1, 1, 1, 2], [0, 1, 0, 0, 2]])
	The given system of equations has infinite number of solutions.
	Use back-substituion in augmented matrix to obtain solution.
	where c, d, are any real numbers.
```


Example 4
=========
```
In [6]: solve([Eq(sinh(x) + cosh(x), 1)])
Rewritting hyperbolics in terms of 'exp' function.
--------------------------------------------------
So that the equation sinh(x) + cosh(x) - 1 becomes exp(x) - 1.
	This system of equations is equivalent to solving.
	AX = b where,
	A = Matrix([[1]]), X = Matrix([[x]]) and b = Matrix([[0]]).
	Since the inverse of A exists.
	=>	The given system of equations is well behaved.
	=>	A**-1 = Matrix([[1]]).


	The solution of which is given by X = A**-1 * b
	Substitute values of A and b from above we get,
	=>	Matrix([[x]]) = Matrix([[1]])**-1 * Matrix([[0]])
					= Matrix([[0]])


		Hence x = 0, is the unique solution.


	Try to get augmented matrix Matrix([[1, 0]]) in row-echolen form. Currently matrix is:
	------------------------------------------------------------------------
[1  0]


	For 1 th row.
	-------------
	Row 1 contains the pivot element.
	Divide all the elements in the current row by the pivot element = 1. ------>
[1  0]
	Augmented matrix is now in row-echelon form and equals:
			Matrix([[1, 0]])
	Since the augmented matrix equal number of rows(=1) and unknowns(=1).
	=>	The given system of equations has exactly one solution.
	Use back-substituion in augmented matrix to obtain solution.
```
