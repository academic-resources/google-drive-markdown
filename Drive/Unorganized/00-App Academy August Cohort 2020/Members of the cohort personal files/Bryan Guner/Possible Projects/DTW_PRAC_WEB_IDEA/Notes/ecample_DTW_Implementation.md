![](2020-08-12-04-37-16.png)
**in the table linked above:**
● For each cell, the cost of arriving at the cell from the bottom, left, and bottom-left is calculated.
● On the point (2,2) of Figure 7 below, it costs 2 units to arrive from the bottom cell because the bottom cell’s lowest value plus the current cell value is 2.
● It costs 1 to arrive from the left because 2 + 0 = 2. It costs 1 to arrive from the bottom left because 1 + (½)\*0 = 1.
● After calculating the costs for each cell, the least cost path can be determined. To find the least cost path, one must make three assumptions.
● The first is that the path always begins at point (1,1) and end at the upper right most cell.
● Secondly, it is assumed that the least cost path should lie along the diagonal of the matrix, so diagonal movement should be favored over lateral movement.
● Can adress the aformentioned desire for diagonal transversal by implementating a reduction in the cost of diagonal movement by 50%.
● Finally, the third assumption is that because time moves forward, one should never move backwards to find the least cost path.
● Calculating the least cost path involves starting at the upper right most cell and working backwards to the starting cell.
● The path chosen should be the cell with the lowest cost of arrival.
●
//--------------------------------------
**Cost of arrivial per cell:**
![](2020-08-12-04-45-10.png)
//--------------------------------------
