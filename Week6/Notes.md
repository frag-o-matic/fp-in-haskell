# Week 6 Topics

## Types with Class
* Type-classes are a way to achieve polymorphism and restrict types for polymorphic functions
* Eg: `(+) :: a -> a -> a` (`a` can be any type, not very useful/meaningful) vs `(+) :: Num a => a -> a -> a` (`a` must be a number)
* Type-calsses are essentially constraints

### Defining type classes

* `type class` : set of types for which some operations are defined
* `class` <type-class-name> <type-variable> Eg: `class Color a where`
* instance declaration says that a type is a member of a type class. Eg: `instance Color Bright where`

### Predefined type Classes

* `Num` and `Show`

## Lambda Calculus

### Variables

* `bound` (`∖x->x+1`) vs `free` (`y*3`) :  a variable is bound if there is some enclosing lambda expression that binds it

### Conversion rules

* replace an expression by another (“equal”) one
* simplify an expression these are called reductions
* three rules:

    * Alpha conversion : change the name of a function parameter consistently, can't change free variables
    * Beta conversion : “workhorse” of lambda calculus: it defines how functions work
    * Eta conversion : function is equivalent to a lambda expression that takes an argument and applies the function to the argument

## Monads

* allow sequencing of function calls to be enforced by the type system
* allows computations to be "chained" together
* Eg: `IO` monad and `Maybe` monad (and `do` constructs using them)

### Building blocks of a monad

* A monad consists of three objects, which must satisfy the "monad laws"

### The `Monad` type class

* `return` function takes a value and returns a value wrapped in the monad type constructor
* `>>=` operator (“bind”) binds a value returned from a computation to another computation
* `>>` operator (“then”) is like `>>=`, but it just ignores the value returned by the computation
* `fail` function is used by the system to help produce error messages when there is a pattern that fails to match
* To be an actual monadic type, the implementations of `bind` and `return` must conform to the three monad laws

### The monad laws

* right unit law: `m >>= return = m`
* left unit law: `return x >>= f  = f x`
* The associativity law: `(m >>= f) >>= g = m >>= (\x -> f x >>= g)`

### `do` notation

* convenient syntactic sugar for monadic computations
