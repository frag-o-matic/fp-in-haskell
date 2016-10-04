# Week 2 Topics

## Boolean Values and Expressions
- `Boolean` type : `True` & `False`
- `==` tests for equality

## Zip that List
- 'zip' -> function combines two of lists into a list of pairs
    - Eg: `zip [1,2,3] [4,5,6]` -> `[(1,4),(2,5),(3,6)]`
- `zip3` -> combines three lists into a triplet
    - Eg: `zip [1..10] ['a'...'z']` -> ``
- If lists of diff lengths, length of shorter list is used
- `zipWith` -> applies a function to the result of `zip`
    - Eg: `zipWith max [1,2,3] [0,2,4]` -> `[1,2,4]` (returns the `max` of each pair)
    - Eg: `zipWith (+) [1,2,3] [0,2,4]` -> `[1,4,7]` (returns element-wise sum of each pair)
    - Can take lambda function for the operation
    
## I/O
- Use `IOMonad` for I/O operations
- Functions dealing with I/O will have `IO()` type
- `<-` associates input values with names
- I/O operations are impure
- Order of function evaluation matters for impure functions
    - `do` notation and *sequencing* of actions -> very important for I/O

