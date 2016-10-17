# Week 4 Topics

## Keep Your Programs Tidy 

- `let` expression and scope
- Whitespace is significant in `let` expressions
- `where` clause
    * provides definition for variables used in an equation
    * indent mode than start of equation
    * `where` is similar to `let` but is not an expression


## Guards

- definiting functions based on predicate values. Eg:
    ```
    absolute x
        | x<0 = -x
        | otherwise = x
    ```
- `otherwise` like `default` in C-style `switch`

## Case expressions

- similar to `guards` but does pattern matching (select clause based on value). Eg:
    ```
    hello :: Pet -> String
    hello x = 
      case x of
        Cat -> "meeow"
        Dog -> "woof"
        Fish -> "bubble"
    ```
- `_` (underscore) acts as the `don't care`/`match all` character for `case` expressions
- `if` is syntactic sugar for `case` expressions

## Dealing with Uncertainty

- `Maybe` values to denote optional/possibly missing values
- `Nothing` similar to `NULL` in C
- derives from `Eq` (equality) and `Ord` (comparison)
- Propagating `Maybe` values
    * `case` statements or `Monads`
- `fmap` applies functions to the value inside `Maybe`

## Parsing Text Using Higher-Order Functions

### Function generators

- generate parameterised functions, eg:
    ```
    gen_add_n = \n ->
    \x -> x+n

    add_3 = gen_add_n 3
    add_7 = gen_add_n 7
    ```
- can be used with any operation, eg:
    ```
    gen_op_n = \op n ->
    \x -> x `op` n
    ```

## Parsers

- Parsec library

## QuickCheck Tool

- automatically generating test cases for your Haskell programs
