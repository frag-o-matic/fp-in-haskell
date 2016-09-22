# Week 1 Topics

## Basic Elements of Haskell:

  * Expressions and Variables
      * Haskell has expressions only, no statements
      * Assignment to variable: `v = (b*b-4*a*c)/2*a`
      
  * Functions
      * Syntax: `<func_name> <args> = <func_body>` as in `hello name = "Hello, "++name`
          * function args separated by spaces, no parens
      
  * Types
      * Types more powerful than in other lang
      * Type declaration and function definition are separate
      * `::` indicates type declaration follows
      * Eg:
      
          `f :: Int -> Int -> Int`
          
          `f x y =  x*y+x+y`
  * Lists
      * Similar to syntax in python. Eg: `lst = [ "A", "list", "of", "strings"]`
      
## Expressions and Equations
  * Pure FP  => no statements (i.e no assignments or jumps)
  * All computation is performed by evaluating expressions

### Expressions
  * expression evaluates to a result `e --> r`
  * function takes argument(s), performs some computation, and produces result(s). 
      * "Apply" a function => use it. write function name <space> args. Eg: `abs (-6)`
  * parens not required (useful for grouping/clear meaning)
  * function application binds tighter than anything else
  
### Equations
  * give names to values. Eg: `answer = 42`
  * same as maths equations (LHS -> name & RHS -> value)
  * are not variables & cannot be re-assigned ("pure") aka "variables are constant"
  
## More Basic Elements

### Lambdas (Anonymous functions)
  * Anonymous functions. Eg: `f = \x y -> x*y+x+y`

### Blocks

  * `let <block> in <ret_value>`
  * is an expression, so it returns a value
  * no need for a `return` statement
  
### Conditionals

  * `if <cond> then <ret_when_true> else <ret_when_false>`
  * is an expression, so it returns a value

### Higher-order Functions

  * functions take other functions as arguments
  * Eg: `map <lambda> <list>` as in `map (\x->2*x) [1..10]` which doubles each item of list

### Case
  * `case ... of ...`
  * works on types
  * ???
  
### Generics
  * ???

## Reduction, Functions and Lists

### Reduction

  * is the sole means of execution of a functional program
  * converting an expression to a simpler form
  * Church-Rosser theorem: `Every terminating reduction path gives the same result`
      * Correctness doesn’t depend on order of evaluation
      * Different expressions can be evaluated in parallel
      
### Functions

  * takes one or more arguments and computes a result 
  * given same arguments, result will always be the same (similar to maths functions)
  * `prelude` -> Haskell's standard library
  * function is defined by an equation, application is evaluated by replacing it with the body of the function

### Lists

  * key datastructure: a single value that contains several other values
  * used for functions returning multiple values
  * Lazy Evalutaion: evaluated only when they are used
  * Operations:
      * `++` (append)       : concat two lists `[1,2] ++ [3,4]` gives `[1,2,3,4]`
      * `..` (sequence)     : sequnce of items `[1..5]` gives `[1,2,3,4,5]`
      * `!!` (index)        : starting with 0 `[[5,3,8,7]] !! 2` gives `8`
      * `head` (first element of list) and `tail` (rest of the list)
  * List Comprehension: specifying computation on list(s)
  * Lists are immutable
  
## GHCI Installation

* Getting ghci `sudo apt-get install haskell-platform`
* Quitting ghci `:q`
