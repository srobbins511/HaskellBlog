# Functions of Multiple Data Types

## Less

    ```haskell
    {
    -- less
    less :: NN -> NN -> Bool
    less O (S n) = True
    less (S n) O = False
    less O O = False
    less (S n) (S m) = less n m
    }
    ```

### Summary

This fucntion evaluates if the first given number of type NN is less than the second given number of type NN and returns a boolean value as a result. It evaluates true if and only if the first given value is less than the second given value. The algorithm works by removing the successors of each NN number in unison and then recursing on the new numbers. It does this until one or both the numbers reaches zero. Whichever number reches zero first had to have been the number witht he least value and thus was less than the other. It returns true if this was the first value given and false if it wasn't or if both numbers hit zero at the same time and were thus equal.

### Breakdown

1. `less :: NN -> NN -> Bool`

    This line defines a function named less that takes two NN number inputs and outputs a boolean value

2. `less O (S n) = True`

    **First Base Cases**, This case defines that if the first input is zero and the second has a successor, the first input was less and returns true

3. `less (S n) O = False`

    **Second Base Case**, If the first input has a successor and the second is zero, return false as the original first input could not be less than the second.

4. `less O O = False`

    **Third Base case**, If both inputs are zero then return false, as if the original numbers are equal and thus one cannot be less than the other.

5. `less (S n) (S m) = less n m`

    **Recursive Call**, If both numbers have a successor, remove the successor and recurse using the two new numbers as inputs. This will keep recursing until one of the numbers becomes zero

## Less Positive

    ```haskell
    {
        lessP :: PN -> PN -> Bool
        lessP I (T n) = True
        lessP (T n) I = False
        lessP I I = False
        lessP (T n) (T m) = lessP n m 
    }
    ```

### Summary

This function is functionally identical to less, but using the data type PN which behaves like a positive number. It works the same by recursively removing successors of the two inputs until a base case is reached

## Multiply Fractions

    ```haskell
    {
        mult :: NN -> NN -> NN
        mult O n = O
        mult (S O) n = n
        mult (S n) m = add m (mult n m)

        multP :: PN -> PN -> PN
        multP I n = n
        multP (T n) m = addP (multP n m) m

        multF :: Frac -> Frac -> Frac
        multF (n,p) (m,t) = (mult n m,multP p t)
    }
    ```

### Summary

The code above defines three functions all defining the functionality needed two multiply two inputs of their respetive data types (*NN, PN, Frac*) 
