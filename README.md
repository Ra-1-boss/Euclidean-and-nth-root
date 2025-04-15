Euclidean
import math

def euclidean_distance(p1, p2):
    """
    Compute the Euclidean distance between two points in n-dimensional space.
    
    Args:
        p1 (list): First point coordinates (e.g., [x1, y1, z1]).
        p2 (list): Second point coordinates (e.g., [x2, y2, z2]).
    
    Returns:
        float: The Euclidean distance between p1 and p2.
    
    Raises:
        ValueError: If points have different dimensions.
    """
    if len(p1) != len(p2):
        raise ValueError("Points must have the same dimensions.")
    
    squared_diff = sum((a - b) ** 2 for a, b in zip(p1, p2))
    return math.sqrt(squared_diff)

# Example usage:
point1 = [1, 2, 3]
point2 = [4, 5, 6]
print(euclidean_distance(point1, point2))  # Output: ~5.196 (√27)
    
   
