# Observations and Analysis

## 1. General Observations

- The centroid fan always created N triangles for an N-vertex polygon.
- The centroid fan was outside-free for the tested convex shapes.
- Constrained Delaunay used 98 triangles for the 100-point circle and gear, while the centroid fan used 100.
- The adaptive method selected the centroid fan for convex polygons and constrained Delaunay for concave polygons.
- The adaptive method was substantially faster for convex polygons.

## 2. Results Analysis

- Convex shape speedup increased from 6.07x for the rectangle to 44.36x for the 100-point circle.
- The tested concave shapes used 37.67-39.93 us for the adaptive method and 20.25-23.76 us for the always-Delaunay baseline.
- Centroid-fan invalidity was concentrated in concave shapes: 3 invalid triangles for C-shape, 1 for L-shape, and 2 for T-shape.
- Arrow and lightning-bolt centroid fans had no sample triangles outside the polygon, despite being concave, so polygon concavity alone does not ensure a visible fan failure at that mesh sample.
- On the 100-point gear, the adaptive method was 388.08 us versus 347.15 us for always-Delaunay, a 0.895x speedup.

## 3. Unexpected Behaviours

- The centroid-fan validation for arrow and lightning-bolt shapes reported zero outside triangles even though they are classified as concave.
- A concave shape can therefore retain a valid centroid fan for the specific polygon and edge geometry, while it is not guaranteed to remain valid in general.
- The smart dispatcher was slower on concave shapes in this implementation, showing that dispatch and convexity detection have measurable overhead.

## 4. Hypothesis Evaluation

- **Partially confirmed**

The evidence confirms that centroid fan is fast for convex polygons and that constrained Delaunay is more reliable for concave polygons. It does not confirm that centroid fan is always invalid for every concave polygon: the arrow and lightning-bolt samples were outside-free. The adaptive strategy provided valid concave results, but did not improve concave timing in the measured implementation.

## 5. Limitations

- MATLAB Online execution timing depends on shared infrastructure and runtime load.
- The sample uses only 2D validation and does not execute the algorithm in Splinter3D or against real 3D mesh cuts.
- Centroid-fan validity was sampled at one triangle centroid per fan triangle rather than by a complete geometric intersection test.
- The main comparison uses only 1000 averaged runs per shape and the scaling tests use fewer runs for larger vertex counts.
- The timing code includes dispatch, polygon classification, and triangulation setup; low microsecond values are sensitive to environment noise.

## 6. Conclusion

For plane-cut cap generation, the centroid fan is the fastest option for convex polygons and uses the minimum N triangles for the tested convex shape. Constrained Delaunay is reliable for concave polygons and the adaptive method should select it when the polygon is concave. The adaptive dispatcher is clearly advantageous on convex polygons, but its concave implementation needs optimization or a lower-overhead convexity check before it can outperform always-Delaunay.

## 7. Next Steps

- Integrate the adaptive method into Splinter3D and test it on real cut sections.
- Replace triangle-centroid sampling with complete containment and overlap validation for centroid-fan triangles.
- Benchmark over a larger set of concave polygons and 3D cutting operations.
- Profile convexity classification and Delaunay setup separately.
- Measure memory usage and compare full result quality with more robust geometric criteria.
