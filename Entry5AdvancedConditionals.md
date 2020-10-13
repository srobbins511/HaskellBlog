# Advanced Conditionals

## Code

```haskell
{
    equalF :: Frac -> Frac -> Bool
equalF (n,p) (m,t) = 
    if(n == m && p == t)
        then True
    else equalSimp (simplifyF (n,p)) (simplifyF (m,t))

--Checks the equality of two simplified fractions
equalSimp :: Frac -> Frac -> Bool
equalSimp (n,p) (m,t) = 
    if(n == m && p == t)
        then True
    else False
-- simplify fractions
-- divide numerator and denominator by the gcd of both
simplifyF :: Frac -> Frac
simplifyF (O,p) = (O,p)
simplifyF (n, I)= (n,I)
simplifyF (n,p) = 
    ( divP (n) (n2p ( gcdN n (p2n p) ) ) , n2p (divP (p2n p) (n2p (gcdN n (p2n p) ) ) ) )
}
```
