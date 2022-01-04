1. Dynamic Time Warping is an algorithm for the measurement of similarity between two temporal sequences, which may vary in speed.
2. The algorithm calculates an optimal match between two given sequences in the form of a distance that is the sum of localized cost functions.
3. The process can be thought of conceptually as arranging the two sequences on the sides of a grid.
4. Each cell within the grid will be filled in with a distance measure comparing the corresponding elements of the two sequences.
5. This measure can be just subtraction of one sequence from another, but more often each cell is computed by more symmetric measures like the square of the difference.
6. In order to find the best path through the grid, we search for a path that minimizes the total distance between them.
7. The procedure for finding an overall distance measure is to find all the possible routes through the grid and calculate the total distance for each.
8. Note that because we are looking for a minimum length path, each routes total distance is the minimum of the sum of distances between individual elements on the path divided by the sum of the warping function.
9. Most instances of the DTW algorithm share common optimizations. The most obvious is known as the monotonic condition, which simply stated is the rule that the path will not turn back on itself and therefore the indexes of the matrix must either remain the same or increase during each subsequent iteration.
10. Further, examining the literal definition of a path, the elements selected must to some degree border each other, and so the indexes may only increase by 1 from each element of the path to the next.
11. Another commonality in DTW algorithms is the boundary condition, which requires that the path must begin at the intersection of each sequence’s respective first elements and end on the intersection of each sequence’s respective last elements.
12. Since this technique has been at the forefront of comparing temporal audio and video signals since the 1980s, the list of variations on the classic algorithm is extensive.
13. Dynamic Time Warping works as an accurate comparison between features so long as they are structured in time (even if the information they convey is in frequency).
14. In addition, because the features considered for a DTW algorithm are set in time, if one were to choose to track multiple features concurrently, (no longer necessary in the context of DTW) it would likely be simple to correlate detected matches between different features by a simple timing threshold.
15. Another benefit of DTW is that if the system were to require multiple ‘database’ performances, then section specific DTW-distance thresholds would become a more accurate measure of similarity between unique pairs of induvial performance instances.

![](2020-08-12-05-20-48.png)
![](2020-08-12-05-21-11.png)
![](2020-08-12-05-21-29.png)
