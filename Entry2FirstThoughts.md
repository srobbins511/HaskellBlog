# First Thoughts

## Early Difficulties

The main thing I noticed instantly when I started using Haskell was that I would have a hard time wrapping my head around how it behaved as a language. For the way Haskell syntax works, more like defining rules of behaviorthan scripting, at least from what I had used at the time, was completely foreign to me. For instance, the = operator being one of equality and not assignment took some getting used to. How programs in Haskell are created almost by defining cases nd not writing scripts was a novel concept to me, to say the least.

## Early Programs

It was not until writing a simple program for addition (*seen below*) that it really clicked for me how things worked.

```haskell
{
-- addition
add :: NN -> NN -> NN
add O n = n`
add (S n) m = S (add n m)
}
```

### To Breakdown

1. `add :: NN -> NN -> NN`
    This line names a function called add and specifies that it takes two data inputs of NN and returns an output of type NN. Type NN is a custom type of data that behaves as Natural numbers, but is built using successor notation using the characters O for the number 0 and S for successor.
    **For Example**
    S (S O) is the successor of the successor of 0. So 2.

2. `add O n = n`
    This line specifies the first case of the function add. The part on the left of the `=` determine the inputs of the function. In this case a `O` and a variable `c`. The output on the right is the varaible `n`.

    Thus in essence it is saying given the input of zero and a number, return the number, or when adding anything to 0 the answer is anything.

3. `add (S n) m = S (add n m)`
    This line defines the recursive part of the function. The inputs on the left are `(S n)` and `m`. The `(S n)` input defines a variable natural number that contains a successor. And `m` defines any natural number. So this case of the function is called when given two inputs with the first being a non-zero natural number and the second being any natural number. The right side of the equation is the recursive call for the function.

    In essence it is saying when given a natural number variable with a successor and any other natural number variable, the result is the successor of the addition of the two variables, which will call itself again and again until the base case of adding something to zero is reached.

It was the simplicity of the function as well as its similarity to content i learned in Discrete Math that really allowed me to get a grasp of how Haskell worked as a language and the versitility of it as a language.
