#### Please add your answers to the **_Analysis of Algorithms_** exercises here.

## Exercise I

a) This loop was really hard for me to figure out; while the _while_ loop is multiplying _n_ 3 times and the inner loop is multiplying it 2 times, the loop is still entirely based on the size of _n_. Therefore, this loop is running at a runtime complexity of `O(n)`.

b) Normally this code would be a nested loop that has a time complexity of `O(n^2)` - However, since the nested/inner loop doubles every time we run it until it hits its maximum of _n_, the running time complexity is actually `O(n log(n))`. This is because the outer loop is time `O(n)` which is multiplied by its inner loop of `O(log(n))`.

c) The _if/then_ block within this code is irrelevant as it's constant time. The meat of this function is the recursive call; once again, the number 2 is irrelevant in the face of the recursive call. This function is a running time complexity of `O(n)` due to iterating a recursive call once for every number from n to 0.

## Exercise II

A _Binary Search_ algorithm would be the most efficient one to use for our purposes, as it would have a running time complexity of `O(log(n))`. We will use it top halve the number of floors rin our data set each time we iterate. Here's the walkthrough:

1. We will select a floor in the middle to start off on, and we'll throw an egg out the window to see if it breaks
2. If the egg breaks, we know that the minimum floor where the egg will break is likely below us. We will resolve our dataset to only include the floors below us
3. If the egg doesn't break, we know that the minimum floor where the egg will break is likely above us. We will update our dataset to only include those floors
4. We will take our new "halved" dataset and choose a floor in the middle again; I will repeat the steps mentioned in points #2 and #3 above until my dataset contains two floors
5. At this point, we'll either be on a floor where the egg has just broken or one where it hasn't (inside the remaining two floors)
6. If n length is 2, I will return _f_ dynamically depending on if the egg has just broken or not (using a simple _if/else_ statement)

Using this algorithm (based on _Binary Search_), we can reduce the number of steps needed to find _f_ while also minimizing the number of eggs broken to `Log(n)`.
