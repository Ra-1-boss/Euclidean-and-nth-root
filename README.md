nth-root
def nth_root(x, n, precision=1e-10):
    """
    Calculate the nth root of a number x using the Newton-Raphson method.
    
    Args:
        x (float): The number to find the root of.
        n (int): The degree of the root (e.g., 2 for square root).
        precision (float): Desired accuracy of the result.
    
    Returns:
        float: The nth root of x.
    """
    if x < 0 and n % 2 == 0:
        raise ValueError("Cannot compute even root of a negative number.")
    if n == 0:
        raise ValueError("Undefined for n = 0.")
    
    guess = x  # Initial guess
    while True:
        next_guess = ((n - 1) * guess + x / (guess ** (n - 1))) / n
        if abs(next_guess - guess) < precision:
            return next_guess
        guess = next_guess

# Example usage:
print(nth_root(27, 3))  # Cube root of 27 (~3.0)
print(nth_root(16, 4))  # 4th root of 16 (~2.0)
