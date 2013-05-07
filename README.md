durand-kerner
=============
Finds all the roots of a polynomial by [Weierstrass' method](http://en.wikipedia.org/wiki/Durand%E2%80%93Kerner_method) (or known in Abramowitz&Stegun as the Durand-Kerner method).  This is basically a generalization of Newton's method that works for multiple roots.

Use
===
Install using npm:

    npm install durand-kerner
    
```javascript
var findRoots = require("durand-kerner")

var roots = findRoots([1, 1, -1])  // Finds roots for 1 + 1*x - 1*x^2

// Now:
//      roots[0] = real part of roots
//      roots[1] = imaginary part of roots

for(var i=0; i<roots.length; ++i) {
  console.log(roots[0][i] + "+" + roots[1][i] + "i")
}

// Prints:
//  1.618033988749895+0i
//  -0.6180339887498949+0i


## `require("durand-kerner")(r_coeff[, i_coeff, n_iters, tolerance, initial])`
Finds the roots of a polynomial whose real coefficients are given by `r_coeff` and imaginary coefficients by `i_coeff`.

* `r_coeff` - the real part of the polynomial's coefficients, stored in an array
* `i_coeff` - the imaginary part of the polynomial's coefficients (default all 0)
* `n_iters` - Maximum number of iterations to run before bailout. Default is `r_coeff.length^3`
* `tolerance` - Stopping threshold.  Default is `1e-6`
* `initial` - Initial guess for solution vector.  This also gets the solution (optional)

Note if initial `< r_coeff.length-1`, then

**Returns** An array of roots.  

# Credits
(c) 2013 Mikola Lysenko. MIT License