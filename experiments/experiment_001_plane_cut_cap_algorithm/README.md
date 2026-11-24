# EXP-001 - [Plane cut cap algorithm comparison]

**Date:** 2026-11-17
**Status:** Completed

## Objective
Compare centroid-fan, constrained Delaunay triangulation, and an adaptive dispatcher for creating valid caps on polygonal plane-cut sections.

## Research Question
Which triangulation method provides the smallest, fastest, and most reliable result for convex and concave 2D polygons?

## Hypothesis
The centroid fan is faster and uses exactly one triangle per polygon edge, but may place triangles outside concave shapes. Constrained Delaunay is slower but produces a valid triangulation. The adaptive method should use the centroid fan for convex shapes and constrained Delaunay for concave shapes.

## Methodology
Nine predefined and generated polygons were tested in MATLAB Online. Execution time was averaged over 1,000 runs for each shape. Triangle count, invalid centroid-fan triangles, smart-method selection, and smart-versus-always-Delaunay timing were measured.

## Main Results
- Centroid fan is valid for convex shapes and uses N triangles for an N-vertex polygon.
- Centroid fan produced outside triangles for concave C, L, and T shapes.
- Constrained Delaunay reduced the triangle count to N-2 interior triangles on the 100-point examples.
- The adaptive method was 6.07x to 44.36x faster than always-Delaunay on the tested convex shapes.
- On concave shapes, the adaptive method selected constrained Delaunay and was comparable to or slower than the always-Delaunay baseline due to classification and dispatch overhead.

## Files
- [methodology.md](methodology.md)
- [result.csv](result.csv)
- [observations.md](observations.md)
- [MatLabTriangle.pdf](MatLabTriangle.pdf)
- [src/](src/)
- [figures/](figures/)

## Related Research
None