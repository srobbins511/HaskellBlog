# Conditionals

    In this Entry I will go over my experience with using conditional statements

## Example: GCD

### Code

    ```haskell
    {
        gcdN :: NN -> NN -> NN
        gcdN (n) (m) = 
            if(less n m) 
                then gcdN n (subtr m n) 
            else if (less m n) 
                then gcdN m (subtr n m) 
            else n
    }
    ```

### Summary

The above code is for a function to find the GCD of two numbers of type *NN*. It takes in two *NN* numbers and returns an *NN* number. In order to complete this task the use of a conditional statement is necessary as the algorithm used requires one to first fins the lesser of the two inputs then recurse using the lesser number and the greater number - lesser number. Which means for the same set of inputs, there will be two possible ways of recursion and three branches out.

Based on what i could tell, Haskell requires the conditionals to be in an in/then/else form with each clearly stated and requiring all to be present. In the case of the above code it reads as:

the result of `gcdN (n) (m)` is `gcdN n (subtr m n)` if `(less n m)` is true, otherwise it is `gcdN m (subtr n m)` if `(less m n)` is true. If both are not then the result is just `n`.
