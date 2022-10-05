# Read 03 - Whiteboarding + Big O

># A beginner's guide to Big O Notation

![image](https://www.freecodecamp.org/news/content/images/2021/06/0_cyqWw3UxODl-wqJi.jpg)
```
The formal definition is useful when you need to perform a math proof. For example, the time complexity for selection sort can be defined by the function f(n) = n²/2-n/2 as we have discussed in the previous section.

If we allow our function g(n) to be n², we can find a constant c = 1, and a N₀ = 0, and so long as N > N₀, N² will always be greater than N²/2-N/2. We can easily prove this by subtracting N²/2 from both functions, then we can easily see N²/2 > -N/2 to be true when N > 0. Therefore, we can come up with the conclusion that f(n) = O(n²), in the other selection sort is “big O squared”.
```
* ### Big O notation is used in Computer Science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm.

* ### Anyone who’s read Programming Pearls or any other Computer Science books and doesn’t have a grounding in Mathematics will have hit a wall when they reached chapters that mention O(N log N) or other seemingly bizarre syntax. Hopefully this article will help you gain an understanding of the basics of Big O and Logarithms.

* ### As a programmer first and a mathematician second (or maybe third or fourth) I found the best way to understand Big O thoroughly was to produce some examples in code. So, below are some common orders of growth along with descriptions and examples where possible.

> ## O(1)

### O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

```
bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}
```

### O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. The example below also demonstrates how Big O favours the worst-case performance scenario; a matching string could be found during any iteration of the for loop and the function would return early, but Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

```
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}
```


> ## O(N²)

### O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N³), O(N⁴) etc.
```
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}
```
> ## O(2^N)
### O(2^N) denotes an algorithm whose growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential — starting off very shallow, then rising meteorically. An example of an O(2^N) function is the recursive calculation of Fibonacci numbers:
```
int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}
```


