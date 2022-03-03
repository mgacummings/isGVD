# isGVD
Code to check whether ideals are geometrically vertex decomposable.

This Sage notebook contains several functions, most notable is the `isGVD` function.
Taking any polynomial ideal, stored as a string, as input, this function returns whether or not the ideal is geometrically vertex decomposable.

## Example

The following ideal is geometrically vertex decomposable [[1]](#KleinRajchgot21).
We use `show_output=False` to hide intermediate output.

```{python}
> isGVD('ideal(y*(z*s-x^2), y*w*r, w*r*(z^2 + z*x + w*r + s^2))', show_output=False)
True
```

By default, `show_output` is set to `True`.
In this case, every intermediate geometric vertex decomposition and the C_{y,I} and N_{y,I} ideals are shown, as well as any warnings.

```{python}
> isGVD('ideal(y*(z*s-x^2), y*w*r, w*r*(z^2 + z*x + w*r + s^2))')
```
Has the following output.

```
------
I = ideal(y*(z*s-x^2), y*w*r, w*r*(z^2+z*x+w*r+s^2))
decomposing with respect to r
[WARNING] Groebner basis not squarefree in r
decomposing with respect to s
[WARNING] Groebner basis not squarefree in s
decomposing with respect to w
[WARNING] Groebner basis not squarefree in w
decomposing with respect to x
[WARNING] Groebner basis not squarefree in x
decomposing with respect to y
C = ideal(x^2-s*z,r*w)
N = ideal(r*s^2*w+r^2*w^2+r*w*x*z+r*w*z^2)
C and N form a valid geometric vertex decomposition
------
I = ideal(x^2-s*z,r*w)
decomposing with respect to r
C = ideal(w,x^2-s*z)
N = ideal(x^2-s*z)
C and N form a valid geometric vertex decomposition
------
I = ideal(w,x^2-s*z)
decomposing with respect to s
C = ideal(z,w)
N = ideal(w)
C and N form a valid geometric vertex decomposition
------
I = ideal(z,w)
generated by indeterminates
------
I = ideal(w)
generated by indeterminates
------
I = ideal(x^2-s*z)
decomposing with respect to s
C = ideal z
N = ideal()
C and N form a valid geometric vertex decomposition
------
I = ideal z
generated by a single indeterminate
------
I = ideal()
zero ideal
------
I = ideal(r*s^2*w+r^2*w^2+r*w*x*z+r*w*z^2)
decomposing with respect to r
[WARNING] Groebner basis not squarefree in r
decomposing with respect to s
[WARNING] Groebner basis not squarefree in s
decomposing with respect to w
[WARNING] Groebner basis not squarefree in w
decomposing with respect to x
C = ideal(r*w*z)
N = ideal()
C and N form a valid geometric vertex decomposition
------
I = ideal(r*w*z)
decomposing with respect to r
C = ideal(w*z)
N = ideal()
C and N form a valid geometric vertex decomposition
------
I = ideal(w*z)
decomposing with respect to w
C = ideal z
N = ideal()
C and N form a valid geometric vertex decomposition
------
I = ideal z
generated by a single indeterminate
------
I = ideal()
zero ideal
------
I = ideal()
zero ideal
------
I = ideal()
zero ideal

True
```

## References

<a id="KleinRajchgot21">[1]</a>
P. Klein and J. Rajchgot. 
Geometric vertex decomposition and liaison. 
_Forum of Math, Sigma_, 9(70), 2021.
