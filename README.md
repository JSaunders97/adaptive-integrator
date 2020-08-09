# Adaptive Integrator

An adaptive integrator which uses the *divide and conquer* paradigm and trapizoids to approximate an integral. The algorithm is inspired by the method described [here](https://en.wikipedia.org/wiki/Adaptive_quadrature).

## Algorithm: Adaptive Integrator
Inputs: Lower Bound, Upper Bound, Previous Estimate, Error Threshold, Function

Output: approximate_integral

* Compute midpoint of integral

* Approximate left and right divisions of integral with trapizoids
    
* new_estimate = left_estimate + right_estimate
    
if | new_estimate - previous_estimate | < threshold:

    return new_estimate

else:

    return adaptive_integrator(lower_bound, mid_point, left_estimate, threshold, function) + adaptive_integrator(mid_point, upper_bound, right_estimate, threshold, function)
    
  ## Example
  
  To demonstrate the effectivness of the adaptive integrator, we approximate the following integral: 
  
  ![integral](https://latex.codecogs.com/gif.latex?%5Cint_0%5E%5Cinfty%20%5Cfrac%7B1%7D%7B%28x&plus;2%29x%5E%7B%5Cfrac%7B1%7D%7B3%7D%7D%7D%20%3D%20%5Cfrac%7B2%5E%7B%5Cfrac%7B2%7D%7B3%7D%7D%5Cpi%7D%7B%5Csqrt%7B3%7D%7D%20%5Capprox%202.87922701884465)
  
 Integrating this function between 5.0 x 10^-324 and 1.0 x 10^308 with an error threshold of 1.0 x 10^-15 and an inital estimate of 3 yields: 2.8792270189503437, which is correct to 10 significant figures.

