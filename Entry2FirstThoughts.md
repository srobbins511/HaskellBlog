# First Thoughts

## Early Difficulties

The main thing I noticed instantly when I started using Haskell was that I would have a hard time wrapping my head around how it behaved as a language. For the way Haskell syntax works, more like defining rules of behaviorthan scripting, at least from what I had used at the time, was completely foreign to me. For instance, the = operator being one of equality and not assignment took some getting used to. How programs in Haskell are created almost by defining cases nd not writing scripts was a novel concept to me, to say the least.

## Early Programs

It was not until writing a simple program for addition (*seen below*) that it really clicked for me how things worked.

```haskell
{
-- addition
`add :: NN -> NN -> NN`
`add O n = n`
`add (S n) m = S (add n m)`
}
```
