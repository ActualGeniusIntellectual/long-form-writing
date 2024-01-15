# Function Decomposition

Let $f$ be a function from A to B. Function $f$ can be decomposed into two functions $g$ and $h$ such that $f = g ∘ h$ where $g$ is a function from A to C and $h$ is a function from C to B. But why stop there? We can decompose $g$ and $h$ into two functions each, and so on. This is called function decomposition. The idea is to decompose a function into more primitive operations and study the properties of the primitive operations to understand the properties of the function. Thus the function $f$ and its properties are downstream from this composition of primitive operations. This is a powerful idea that we will use to understand the properties of functions.

## Function Decomposition Example

Let look at a simple example. Assume we're working with the simple polynomial function $f(x) = 4*x^2 + 1$. We can decompose this function into the following operations:

- $f_1(x) = x^2$
- $f_2(x) = 4*x$
- $f_3(x) = x + 1$

We can then compose these functions to get the original function $f$:

- $f(x) = f_3(f_2(f_1(x)))$

Let's do away with the parentheses and write this as:

- $f(x) = f_3 ∘ f_2 ∘ f_1$

The ordering of the operations is important. If we change the order of the operations, we get a different function. However, you can list $f_3$ as being the $1$ operation. Just remember to apply them in the correct order to build up the original.

## Function Decomposition Syntax

Now lets abstract away the individual compositions. Again, as long as we can build up the original, we have a copacetic decomposition. We can write the decomposition as:

- $ \Theta_{n=1}^{3} f_i = f$

Let $\Theta$ be the equivalent to the summation operator $\Sigma$ but for function composition. The lower bound is the starting function and the upper bound is the final function. The index is the order of the function composition.

## Computing the Derivative of a Function Composition

Let's say we want to compute the derivative of the function $f(x) = f_3 ∘ f_2 ∘ f_1$. We can use the chain rule to compute the derivative of the composition of functions. The chain rule states that:

- $ \frac{d}{dx} f(g(x)) = f'(g(x)) * g'(x)$

We can apply this rule to our function composition:

- $ \frac{d}{dx} f(x) = \frac{d}{dx} f_3(f_2(f_1(x))) = f_3'(f_2(f_1(x))) * f_2'(f_1(x)) * f_1'(x)$

Yup. It's chain rule all the way down. We can apply this rule to any function composition. The chain rule is a powerful tool for computing the derivative of a function composition.

Symbolically, meaning without variables, we can write the chain rule as:

- $ \frac{d}{dx} f = \frac{d}{dx} (f_3 ∘ f_2 ∘ f_1) = f_3' ∘ f_2 ∘ f_1 * f_2' ∘ f_1 * f_1'$

Because of the nature of the chain rule and nested nature of function composition, we can write the derivative of a function composition recursively. Let's define the derivative of a function composition as:

- $ \frac{d}{dx} f = \frac{d}{dx} (f_3 ∘ f_2 ∘ f_1) = f_3' * \frac{d}{dx} (f_2 ∘ f_1)$

## Grand Unified Theory of Deriving Function Compositions

Now we can incorporate the function composition syntax to reduce the number of terms in the derivative of a function composition. Let's define the derivative of a function composition as:

- $ \frac{d}{dx} f = \frac{d}{dx} \Theta_{n=1}^{3} f_i = f_3' * \frac{d}{dx} \Theta_{n=1}^{2} f_i$

We can continue to apply this rule until we get to the derivative of the first function in the composition. We can then apply the chain rule to get the derivative of the first function in the composition. We can write this as:

Setting some general bounds and replacing the $3$ with $m$, we get the general form of the derivative of a function composition:

- $ \frac{d}{dx} f = \frac{d}{dx} \Theta_{n=1}^{m} f_i = f_m' * \frac{d}{dx} \Theta_{n=1}^{m-1} f_i$

I think this is a pretty cool result.