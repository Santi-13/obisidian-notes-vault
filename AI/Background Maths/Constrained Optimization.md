#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning Week 5
---
***Constrained optimization*** refers to finding the *minima* or *maxima* of a function along a constrained *path*. A **contour map** is a graphical representation of a three-dimensional surface on a two-dimensional plane. It uses **contour lines** to connect points of equal value, such as elevation or temperature. 

![[Pasted image 20250128105325.png]]

A french mathematician named **Lagrange** noticed that when the **contours** just *touch* the *path*, then you'll have found the *maximum* or *minimum* point. He also noticed that when the contour touches the *path*, the vector perpendicular to the **contour** is in the same direction as the vector of the *path* itself. So we want to find the grad that is perpendicular to both the *path* and the *function*.

So we want to maximize the function $f(x,y) = x^2y$  