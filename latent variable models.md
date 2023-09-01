
a latent variable is the ==hidden== representation (source) of the observed input
![](attachment/41c90ae83c353100d73d10603c7b7fa7.png)
like the scary shadows on left and the source on right 

the Q is Can we learn the true explanatory factors. e.g. latent variables. from only observed data?
![](attachment/3c21e1296b6f9257efaad3d91d396b0e.png)


![](attachment/699a9e4b94266cccdb62fa42851820a9.png)
p(x) is scatter in the feature space
it doesn't take the regular known distributions like gaussian, binomial etc.

early in machine learning they used mixture of gaussian: 
	construct those distributions into combination of gaussian distributions like **Fourier** 

p(z) is normally gaussian, not necessarily have a covariance -> covariance is unity
z is a gaussian with some variance $\sigma{}$   thus giving by the ellipse form 
we can assume it with unit variance i.e. circle

estimate or approximate the p(x) not compute it.

![](attachment/27359cf877c35583c25394a8ad54f128.png)

p(x|z) if giving a point from the data z give me it's easy gaussian distribution like the red dots data
