# Week 3 Topics

## Recursive Functions on Lists
- Every list is either `[]` or `(x : xs)` (`:` is the `cons` function)
- `filter` give a predicate and a list, returns a list of the elements that satisfy the predicate
    - Eg: `filter (<5) [3,9,2,12,6,4] -- > [3,2,4]`
    
#### Computations over lists
- Many `for`/`while` loops in imperative languages are naturally expressed as list computations in Haskell
    - Perform a computation on each element of a list: `map`
    - Iterate over a list, from left to right: `foldl` and from right to left: `foldr`

#### Function composition
- express a large computation by "chaining together" a sequence of functions
- `.` is the function composition operator. Eg:`(f . g) x = f (g x)`

#### Folding a list (reduction)
- iteration over a list to produce a singleton value is called a fold
    - `foldl (+) z [x0,x1,x2]  -- > ((z + x0) + x1) + x2` where `+` is an arbitrary operation and `z` is the accumulator value
    - `foldr (+) z [x0,x1,x2]  -- > x0 + (x1 + (x2 + z))` where `+` is an arbitrary operation and `z` is the accumulator value
    - `map` is a special case of `fold`
    
#### Loops vs Maps & Folds
    https://github.com/wimvanderbauwhede/HaskellMOOC/tree/master/MapsFoldsLoopsTutorial

## User Defined Data-types
- Keyword `data` indicates a new type definition
- Algebraic data types
    - `sum` datatype -> Alternative values (separted by `|`)
    - `record` or `product` datatype -> Stores a bunch of values
- Type class `Show` and `deriving Show` to print values of custom data types

## Type Classes
- Generalized family of similar types (provide implementation for common functions such as `+`). Eg:
    - `Ord` -> Relational ordering
    - `Show` -> Can print values as strings
    - ...
- `ghci` can show types with `:t`
    ```
    Prelude> :t (==)
    (==) :: Eq a => a -> a -> Bool
    ```
- `deriving` clause associates a type with various type classes
- Type classes essentially define an interface and constrain members to implement that interface. Type-classes provide a mechanism for operator overloading in Haskell
