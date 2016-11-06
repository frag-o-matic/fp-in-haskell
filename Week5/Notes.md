# Week 5 Topics

## Lazy is Good

- Haskell is a "lazy" lang -> evaluation of expression delayed till it is needed (vs. eager evaluation as in C/Java)
- "call-by-value" (C/Java) vs "call-by-need" (Haskell)
- "bottom" (`bot`) -> non terminating value
- "strict in argument" -> function fails to terminate when `bot` is supplied as the argument

### Infinite Data Structures

* Definition `let ones = 1 : ones` -> infinite list of `1`s
* `take` (pick specified number of elements from a data structure) and `drop` (remove specified number of elements and return rest of the list)
* `^C` to terminate infinite loops
* `repeat a` -> infinite list of identical values

### Currying

* Restrict all functions to have just one argument, makes use of higher order functions
* `f :: Int -> Int -> Int` is actually `f :: Int -> (Int -> Int)`
* `a->b` gives the type of a function with argument type `a` and result type `b`
* arrows group to the right, and application groups to the left

### Polymorphism

* `Parametric`: can be instantiated to any type, represented by a type variable. Eg: `length::[a] -> Int` (`a` is any type)
* `Ad-hoc`: instantiated to any type chosen from a set. Eg: `(+)::Num a => a -> a -> a` (add values of any type `a`, provided that `a` is an element of the type class `Num`)

### Type inference

* analysis of code in order to infer its type => based on `type inference rules`:
    * Context
    * Type of constant
    * Type of application
    * Type of lambda expression

### Partial application

* don’t need to provide all arguments to a function

    ```Haskell
    sq x y = x*x+y*y
    sq4 = sq 4 -- = \y -> 16+y*y
    sq4 3 -- = (sq 4) 3 = sq 4 3 = 25
    ```
