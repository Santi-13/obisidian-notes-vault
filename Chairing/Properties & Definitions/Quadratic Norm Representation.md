#Chairing #Definition
For a given ***Euclidean norm*** of a vector $\mathrm{x}$:
$$
V(\mathrm{x}) = \frac{1}{2} \lvert \lvert \mathrm{x} \rvert  \rvert_{P}^2  
$$
Here, $\lvert \lvert \mathrm{x} \rvert \rvert^2_{P}$ representes the **quadratic** form associated with the matrix $P$. We can rewrite this expression in the following ways:

#### Matrix Notation:
$$
V(\mathrm{x}) = \frac{1}{2} \mathrm{x}^T P \mathrm{x}
$$
#### Component Form:
$$
V(\mathrm{x}) = \frac{1}{2} \sum^n_{i=1} \sum^n_{j=1} P_{ij} \mathrm{x}_{i} \mathrm{x}_{j}
$$
#### Diagonal Form:
If $P$ is diagonal with elements $p_i$ on the diagonal, the **quadratic** norm simplifies to:
$$
V(\mathrm{x}) = \frac{1}{2} \sum^n_{i=1} p_{i} x_{i}^2
$$
