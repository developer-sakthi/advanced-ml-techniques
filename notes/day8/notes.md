# DBSCAN

- unsupervised
- groups together points that are closely packed (high density) and marks points in low-density regions as outliers.
- Clusters are formed where many points are close together.

## Advantages

- Can find arbitrary shaped clusters
- Handles noise and outliers
- No need to specify number of clusters beforehand

## Types of points

### Core points

- Points that are part of a dense region.
- Have a neighborhood of at least minPts points.
- A point is a core point if it has at least MinPts points within ε distance.

eg :
MinPts = 5
If a point has 5 or more neighbors within ε → Core Point

### Border points

- Points that are on the periphery of a dense region.
- Have a neighborhood of less than minPts points, but are not core points.

A point that:

- Is within ε of a core point
- But has less than MinPts neighbors

### Noise points

- Points that are not core points and are not border points.
- Is not within ε of any core point
- Has too few neighbors than minPts

## Parameters

### 1. Epsilon (ε)

Maximum distance to consider neighbors.

If ε is too small

```
Too many noise points
Clusters break apart
```

If ε is too large

```
Clusters merge together
Poor clustering
```

<div style="border:1px solid #ccc; padding:10px; border-radius:6px;">
<strong>Finding ε value :</strong> plot the k-distance graph with k=minPts-1 and elbow point gives indication of optimal k value .
</div>

### 2. MinPts (Minimum Points)

Minimum number of points required to form a core point.

Typical values:

```
MinPts = 4
MinPts = 2 * number_of_features
```

Example:

| Dataset Dimension | Suggested MinPts |
| ----------------- | ---------------- |
| 2D                | 4                |
| 3D                | 6                |
| Higher            | Larger           |
