as we're using **maximum likelihood**  we want to maximize the 
![](attachment/c4d0ea5ef790ef5b1fcfd52be50468b9.png)

take log (any monotonic function doesn't change the data behavior) so maximize the log is the same 
using bayes rule
![](attachment/115d08809641bed9df63dc104446b422.png)

Multiply top and bottom by q(z l x)
![](attachment/ae4c2c1ed1ba567a97a68a7d775b3ef5.png)

get the expectation
![](attachment/7f6fa81c6c5be6165d8c4a77e196ff79.png)
as LHS doesn't depend on z
![](attachment/7b545f7828c903cb97a7183a1735886e.png)

recall from [[Distribution formulas]]
![](attachment/1390d24f56502037b8b18f8078f98ff5.png)

1st term is Data reconstruction operation
	takes x and outputs the z (decoder ???)

2nd term is KL divergence between prior, and samples from the encoder network 

3rd term is KL divergence between encoder and posterior of decoder
	hard to compute
-> solution: KL is >= 0, so dropping this term gives a lower bound on the data likelihood:

![](attachment/c71bc8dc94e28603ed873c2f91f471e0.png)


we don't know how to maximize the LHS but we can with the RHS



