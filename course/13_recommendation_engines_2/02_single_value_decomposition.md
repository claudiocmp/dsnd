# Singular Value Decomposition

SVD is a methodology widely implemented for recommendations.

**Latent Factors**

Latent factors are values that are not directly observable in our data, but that may be recognised when looking at relationships and trend that exists between the data values we observed.

Let's create a series of factors which appears in movies and are liked or not by users. For instance, `{dog, actor_named_Brian, AI, Mary_Strip, sad_movie}` 

![](img\00_latent_factors.PNG)

From here, we can create a matrix which relates $n$ users and $m$ items (movies) through a value $r_nm$ (rating).

$$
\begin{bmatrix}
r_{11}&r_{12}&\cdots &r_{1n} \\
r_{21}&r_{22}&\cdots &r_{2n} \\
\vdots & \vdots & \ddots & \vdots\\
r_{n1}&r_{n2}&\cdots &r_{nn}
\end{bmatrix}
= U \Sigma V
$$

Where:
* $U$ **Users-laten_factors** represents how each user feels about each latent factor. It has dimension **(n,k)**, where **k** is the number of latent factors.<br/>
* $V$ **Item-laten_factors** represents how each item includes each latent factor. It has dimension **(m,k)**, and it's transposed.<br/>
* $\Sigma$ is a **(k,k) diagonal matrix** with sorted values largest to smallest. This is because the **latent factors are like Principal Components** and the $\Sigma$ matrix tells us how much each factor is important.

![](img\01_latent_factors_decomp.PNG)


Therefore, given $k$ latent factors, we have to find $k*(m + n +1)$ values related to them.

Three main takeaways from SVD:
  * The latent factors retrieved from SVD aren't actually labeled.
  * We can get an idea of how many latent factors we might want to keep by using the Sigma matrix.
  * SVD in NumPy will not work when our matrix has missing values. This makes this technique less than useful for our current user-movie matrix.

