
### Fermat's factorization method on RSA
------

- If p and q are too close to √N then we can easily factorize it with fermat's factorization method
- we have to find an s such that (s^2 - n) is a perfect square 
- s^2 have to greater then n
- if p and q are close t would be relatively very small
- only work if and only if p and q are relatively too close  compared to n

Let s = ( p + q) / 2  ( Note that s is close to √n)
and t = ( p - q) / 2
we know  n = p * q 
then, n = (s + t) * (s - t)
then, n =  s^2 - t^2
then, t^2 = s^2 - n
so t = √(s^2 - n)
now we can get p and q 
p = s + t
q = s - t

