# Understanding Quantization with `cdist` and `argmin`

In digital signal processing, we need to convert continuous signal values into discrete levels. Let's break down how this works with a clear example using NumPy's `cdist` and `argmin` functions.

## Our Example Data

**Original signal samples**: `[1.7, 3.2, 5.5, 8.1, 9.3]` volts

**Quantization levels** (3-bit, 0-10V range): `[0.0, 1.429, 2.857, 4.286, 5.714, 7.143, 8.571, 10.0]` volts

## Step 1: Calculate Distances with `cdist`

The `cdist` function calculates the distance between each pair of points in two collections:

```python
from scipy.spatial.distance import cdist
import numpy as np

# Reshape arrays to required 2D format
samples_2d = np.array([1.7, 3.2, 5.5, 8.1, 9.3]).reshape(-1, 1)
levels_2d = np.array([0.0, 1.429, 2.857, 4.286, 5.714, 7.143, 8.571, 10.0]).reshape(-1, 1)

# Calculate distances
distances = cdist(samples_2d, levels_2d)
```

The resulting `distances` matrix shows how far each sample is from each quantization level:

```
distances = 
[
  [1.700, 0.271, 1.157, 2.586, 4.014, 5.443, 6.871, 8.300],  # distances for sample 1.7V
  [3.200, 1.771, 0.343, 1.086, 2.514, 3.943, 5.371, 6.800],  # distances for sample 3.2V
  [5.500, 4.071, 2.643, 1.214, 0.214, 1.643, 3.071, 4.500],  # distances for sample 5.5V
  [8.100, 6.671, 5.243, 3.814, 2.386, 0.957, 0.471, 1.900],  # distances for sample 8.1V
  [9.300, 7.871, 6.443, 5.014, 3.586, 2.157, 0.729, 0.700]   # distances for sample 9.3V
]
```

Let's examine the first row: `[1.700, 0.271, 1.157, 2.586, 4.014, 5.443, 6.871, 8.300]`
- This shows the distance from our first sample (1.7V) to each quantization level
- The smallest distance is 0.271, at index 1, which corresponds to level 1.429V

## Step 2: Find Closest Levels with `argmin`

The `argmin` function identifies which column has the minimum value in each row:

```python
closest_indices = np.argmin(distances, axis=1)
```

This gives us:
```
closest_indices = [1, 2, 4, 6, 7]
```

For each sample, this tells us which quantization level is closest:
- Sample 1.7V → Index 1 (smallest distance is 0.271)
- Sample 3.2V → Index 2 (smallest distance is 0.343)
- Sample 5.5V → Index 4 (smallest distance is 0.214)
- Sample 8.1V → Index 6 (smallest distance is 0.471)
- Sample 9.3V → Index 7 (smallest distance is 0.700)

## Step 3: Get Quantized Values

Finally, we use these indices to look up the corresponding quantization levels:

```python
quantized_signal = vector_levels[closest_indices]
```

Result:
```
quantized_signal = [1.429, 2.857, 5.714, 8.571, 10.0]
```

## Visual Representation

Here's what's happening visually:

| Original sample | Distance to each level | Closest level | Quantized value |
|----------------:|------------------------|---------------|-----------------|
| 1.7V | 1.700, **0.271**, 1.157, 2.586, 4.014, 5.443, 6.871, 8.300 | 1.429V | 1.429V |
| 3.2V | 3.200, 1.771, **0.343**, 1.086, 2.514, 3.943, 5.371, 6.800 | 2.857V | 2.857V |
| 5.5V | 5.500, 4.071, 2.643, 1.214, **0.214**, 1.643, 3.071, 4.500 | 5.714V | 5.714V |
| 8.1V | 8.100, 6.671, 5.243, 3.814, 2.386, 0.957, **0.471**, 1.900 | 8.571V | 8.571V |
| 9.3V | 9.300, 7.871, 6.443, 5.014, 3.586, 2.157, 0.729, **0.700** | 10.000V | 10.000V |

This completes the quantization process, mapping each continuous signal value to the nearest available discrete level.
