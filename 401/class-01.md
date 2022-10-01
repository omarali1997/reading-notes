# Read 01 - Intro to Python

## 1- Big O
----------------------------
![image](https://www.freecodecamp.org/news/content/images/2021/06/0_cyqWw3UxODl-wqJi.jpg)

### The formal definition is useful when you need to perform a math proof. For example, the time complexity for selection sort can be defined by the function f(n) = n²/2-n/2 as we have discussed in the previous section.

### If we allow our function g(n) to be n², we can find a constant c = 1, and a N₀ = 0, and so long as N > N₀, N² will always be greater than N²/2-N/2. We can easily prove this by subtracting N²/2 from both functions, then we can easily see N²/2 > -N/2 to be true when N > 0. Therefore, we can come up with the conclusion that f(n) = O(n²), in the other selection sort is “big O squared”.
----------------------------------

## 2- Python Names and Values
-------------------------
### Python is simple
* #### Works like other languages
* #### ... until it doesn't
* #### Mechanisms are simple
* #### ... but the effects can be surprising
* #### Names, values, assignment, mutability

### Names refer to values
* ### Assignment: make this name refer to that value
---------------------
#### x = 23
#### print(x)
--------------------------

