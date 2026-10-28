
## Introduction

When learning functional programming I often read some definitions of the basics concepts.
But instead of having a great comprehension of what I what reading I get stuck.

Let's take the example of a [monoid](https://en.wikipedia.org/wiki/Monoid)

> In abstract algebra, a monoid is a set equipped with an associative binary operation and an identity element. For example, the natural numbers with addition form a monoid, the identity element being 0.

Among all the complicated terms let's focus on the mathematical ones : **associative** and **identity element**.

## Why to learn those mathematical concepts ?

Object-Oriented Programming is based on Solid Principles and code pieces called design patterns.
It is not the same for Functional programming which tends to rely on abstract definitions.

To learn functional programming I needed to do some maths !

> 💡 Those concepts are useful for OOP developers too !

But hopefully, we can explain them using code analogies so it will be easier for you to follow me !

_**Disclaimer** : I'm absolutely not an expert about it. I will let the comment section available and PR possible to receive your precious feedbacks!_

## Core algebraic laws
Here are rules which can be true for a single operation.

### Commutativity

```
a + b = b + a
```

When an operation is commutative, the order of its arguments does not matter.

### Associativity

```
(a + b) + c === a + (b + c)
```

When an operation is associative we can group several operations as we want.
Order of sub operation does not matter.

Mixing colors is associative because red mixed with (blue mixed with yellow) gives the same result—brown—as (red mixed with blue) mixed with yellow when the same amounts are used. 🎨


## Combining operations

This rules potentially works when several operations interact

### Distributivity

```

```

## Neutral & special values

For an operation there is special values

### Identity

```
e * a = a * e === a
```

Given this formula ```x + 0 === 0 + x === x``` we can see that 0 is the identity for the addition operation.

Given this formula ```x * 1 === 1 * x === x``` we can see that 1 is the identity for the multiplication operation.

### Absorbing element

An absorbing element is a value that overwrite an operation result

```
z * a = a * z = z
```

```
0 * 1 = 1 * 0 = 0
```

For any x or y the result will always be 0.

## Structural concepts

To build program

### Composition

```haskell
myLast [a] -> a
myLast = head . reverse
```

```scala
def myLast[A]: List[A] => A =
  (_.head) compose (_.reverse)

def myLast[A](xs: List[A]): A =
  xs.reverse.head

def myLast[A]: List[A] => A =
  (_.reverse).andThen(_.head)
```

Composition 

### Composability

## Functional programming foundations

To reason about programs

### Purity

### Substitution (referential transparency)

```
y = f(x)
```
If the function f is referentially transparent then substitution is possible and everytime you see **y** you can replace it by **f(x)**

## Useful additional laws

### Idempotence

```
abs(abs(x)) === abs(x)
```

### Inverse

### Cancellation

## The big table :

| Category                                   | Concept                    | Law / Rule                        | Code intuition                             | Why it matters                                 |
| ------------------------------------------ |----------------------------| --------------------------------- | ------------------------------------------ | ---------------------------------------------- |
| **Core algebraic laws (single operation)** | Associativity              | `(a ⊕ b) ⊕ c = a ⊕ (b ⊕ c)`       | `sum(sum(a,b),c) === sum(a,sum(b,c))`      | regroup operations, enables parallel reduction |
|                                            | Commutativity              | `a ⊕ b = b ⊕ a`                   | `a + b === b + a`                          | reorder computations, caching, optimization    |
| **Combining operations**                   | Distributivity             | `a * (b + c) = a*b + a*c`         | distribute a transform over a structure    | refactoring, optimization, parallel transforms |
| **Neutral & special values**               | Identity (neutral element) | `x ⊕ e = x`                       | `acc + 0 === acc`                          | safe initialization, default values            |
|                                            | Absorbing element (zero)   | `x ⊗ 0 = 0`                       | error/null short-circuits pipeline         | failure propagation, early exit                |
| **Structural concepts**                    | Composition                | `f ∘ g`                           | `f(g(x))`                                  | build complex behavior from small functions    |
|                                            | Composability              | functions combine cleanly         | small pure functions chain easily          | modular, reusable systems                      |
| **Functional foundations**                 | Purity                     | same input → same output          | no side effects                            | predictable, testable code                     |
|                                            | Referential transparency   | replace expression with its value | `f(x)` can be substituted by result        | enables algebraic reasoning                    |
| **Useful additional laws**                 | Idempotence                | `f(f(x)) = f(x)`                  | `abs(abs(x)) === abs(x)` | safe retries, stable operations                |
|                                            | Inverse                    | `x ⊕ x⁻¹ = e`                     | `add(x, negate(x)) === 0`                  | undo operations                                |
|                                            | Cancellation               | `a ⊕ b = a ⊕ c ⇒ b = c`           | remove common prefix in pipeline           | reasoning about equality                       |

## Links

[Basic laws of algebra](https://en.wikiversity.org/wiki/Basic_Laws_of_Algebra)
