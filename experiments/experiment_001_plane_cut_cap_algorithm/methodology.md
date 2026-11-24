# Experimental Methodology

## 1. Objective

### Research Question

Which algorithm is suitable for creating a valid cap when a 3D model is cut by a plane?

We compare centroid-fan triangulation, constrained [Delaunay triangulation](https://en.wikipedia.org/wiki/Delaunay_triangulation), and an adaptive method that selects between them.

### Motivation
This experiment is important because all the cut that we will do in splinter3D will require a cap, so finding the most efficient algorithm in each scenario and more importantly always having a valid cap is required.

### Hypothesis

The centroid fan is expected to be faster than constrained Delaunay and to produce exactly N triangles for an N-edge polygon. However, it is expected to be invalid for some concave polygons. The adaptive method should provide a valid triangulation while using the centroid fan for convex polygons and constrained Delaunay for concave polygons.

## 2. Experimental Setup

The experiment was made in [MATLAB Online](https://matlab.mathworks.com/). It uses 2D polygons to evaluate the triangulation strategies.

A valid solution is defined as follow:
- All the triangle in the solution need to be inside of the shape
- The shape need to be fully filled with triangles and there should not be any empty space

The best solution is defined as follow:
- The number of triangle created need to be the smallest
- The solution need to be the quickest

### Input Data

The input data consists of predefined convex and concave polygons plus generated circle and gear polygons:

| Shape | Vertices | Type |
|---|---:|---|
| Circle | 13 | Convex |
| Rectangle | 4 | Convex |
| Arrow | 8 | Concave |
| C-shape | 8 | Concave |
| L-shape | 6 | Concave |
| T-shape | 8 | Concave |
| Lightning bolt | 8 | Concave |
| Circle | 100 | Convex |
| Gear | 100 | Concave |

### Software
- MATLAB Online
- MATLAB constrained `delaunayTriangulation`
- MATLAB `isInterior` for constrained-Delaunay triangle validation

## 3. Experimental Parameters

The main comparison used 1,000 executions per shape. The generated scaling tests used 50-500 executions depending on polygon size. No 3D mesh or live Splinter3D implementation was used.

## 4. Procedure

1. Open `src/PlotDelaunayTriangulation2Example.ipynb` in MATLAB Online.
2. Define convex, concave, circle, and gear polygons.
3. Generate centroid-fan triangles and validate a sample triangle from each fan triangle against `inpolygon`.
4. Create a constrained Delaunay triangulation with polygon boundary constraints and count triangles marked interior by `isInterior`.
5. Run the centroid fan, constrained Delaunay, and adaptive dispatcher 1,000 times for the main shape set.
6. Run the scaling tests over circle sizes from 4 to 1,000 vertices and gear sizes from 4 to 1,000 vertices.
7. Record the average execution time and speedup ratio.

## 5. Measurements

We are collectiing all the following metrics

- Execution time in microseconds (`us`): average time over the configured runs.
- Number of triangles: compare the centroid fan and constrained Delaunay output.
- Invalid centroid-fan triangles: number of triangles whose sample centroid is outside the polygon.
- Speedup: always-Delaunay time divided by adaptive-method time.
- Smart-method selection: centroid fan for convex shapes and constrained Delaunay for concave shapes.

## 6. Reproducibility

Open `src/PlotDelaunayTriangulation2Example.ipynb` in MATLAB Online and run all sections in order. The shape definitions, run count, timing loops, and adaptive dispatch are contained in the notebook. Processed summary measurements are in `result.csv`; visualizations are stored in `figures/`.
