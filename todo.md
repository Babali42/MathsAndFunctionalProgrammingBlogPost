# TODO: Finish "Maths and functional programming"

## 1. Fill the empty sections
- [ ] **Distributivity**: write the formula `a * (b + c) = a*b + a*c` and a code example (e.g. `list.map(f)` over a concatenation: `(xs ++ ys).map(f) == xs.map(f) ++ ys.map(f)`)
- [ ] **Composition**: finish the dangling "Composition" sentence and explain the three Scala versions (`compose`, `andThen`, plain call)
- [ ] **Composability**: write a short explanation with a pipeline of small functions
- [ ] **Purity**: define it and give one pure and one impure example
- [ ] **Inverse**: explain with `x + (-x) = 0` and `reverse(reverse(xs)) == xs`
- [ ] **Cancellation**: explain with `a + b = a + c ⇒ b = c` and say where it fails (e.g. multiplication by 0)
- [ ] Complete the "To build program" intro line (and the other one-line section intros)

## 2. Close the loop on the monoid
- [ ] Re-quote the monoid definition near the end
- [ ] Show `Int` with `+` and `0` as a monoid (Scala)
- [ ] Show `String` with `++` and `""` as a monoid (Scala)
- [ ] Explicitly map: associativity → grouping freedom, identity → safe default / empty value
- [ ] Optionally define a `Monoid[A]` trait with `combine` and `empty`

## 3. Add counter-examples
- [ ] Commutativity fails: string concatenation `"a" + "b" != "b" + "a"`
- [ ] Associativity fails: subtraction `(5 - 3) - 1 != 5 - (3 - 1)`
- [ ] Identity: show an operation with no identity in the set
- [ ] Idempotence fails: `x + 1`

## 4. Improve the examples
- [ ] Replace the colour-mixing analogy for associativity with string concatenation or list append
- [ ] Replace `0 * 1 = 0` for the absorbing element with `x && false` or `None`/`Option` short-circuiting
- [ ] Connect idempotence to a practical case (safe retries, `distinct`, `toSet`)
- [ ] Pick one running example (e.g. `combine`) and reuse it across sections

## 5. Fix technical details
- [ ] Haskell snippet: `myLast [a] -> a` → `myLast :: [a] -> a`
- [ ] Make sure every Scala snippet compiles
- [ ] Move Composition and Composability out of the algebraic laws or add a sentence explaining why they are a different kind of idea
- [ ] Check the table matches the final content (add counter-examples or links if useful)

## 6. Proofreading
- [ ] "what I what reading" → "what I was reading"
- [ ] "This rules potentially works" → "These rules potentially work"
- [ ] "there is special values" → "there are special values"
- [ ] "everytime" → "every time"
- [ ] Run a spell check on the whole post

## 7. Polish and publish
- [ ] Add a short conclusion and a "what to learn next" (Semigroup, Monoid, Functor)
- [ ] Add more useful links (Scala docs, a monoid article)
- [ ] Re-read as a beginner: does each law have a formula, an example and a counter-example?
- [ ] Set `draft: false` only once everything above is checked
