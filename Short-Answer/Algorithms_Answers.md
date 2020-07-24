#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) Given that the loop checks if a is less than n cubed, while adding n squared to a each iteration of the loop, it would take n times to iterate through the loop entirely, so it has a runtime of O(n).

b) In this function there are two loops, the for loop, which runs n times, and the inner loop which uses a comparison between j and n to determine when to stop. every time the inner loop runs, j doubles, so the breakpoints of when the inner loop would stop are on exponents of 2, therefore the runtime is O(n*log2(n)).

c) This is a simple recursion function that runs itself again while the variable bunnies is over 0, every time it recurses, it decrements bunnies by one, therefore it has a runtime of O(bunnies).

## Exercise II

I would use a binary search here. If the egg in the middle floor breaks, continue searching the subtrees below, and search higher if it does not break.Binary searches have a runtime of O(log2(n)), which would mean that the number of dropped eggs would not be too great if there were a large number of floors.

I would utilize a midpoint strategy. And, in the case where the midpoint would be a float, I would round up because that just makes more sense to me to be more inclusive of floors and would probably be the fastest way at finding the floor fastest.

If the egg breaks at any floor, the floor below it would be considered the new upper bound, since we don't need to test the higher floors anymore. By keeping a list of the floors where eggs break and did not break, whenever an egg does not break but broke on the floor above, we will return that floor as the maximum floor.

For example, let's use 50 stories where the eggs wouldn't break at floor 11 and below:

    1: Floors 1-50, midpoint = 26 (break)
    2: Floors 1-25, midpoint = 13 (break)
    3: Floors 1-12, midpoint = 7 (safe)
    4: Floors 7-12, midpoint = 10 (safe)
    5: Floors 10-12, midpoint = 11 (safe)
    6: Floors 11-12, midpoint = 12 (break)
    
    At this point we know the max safe floor is 11 since it is safe there and broke on floor 12.

