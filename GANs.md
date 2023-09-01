Generative Adversarial Networks

![](attachment/b14a2dc39c746e6dd759963329f3812c.png)

as we don't know the two distributions, thus we can't know if the training is done or not
so we want to compare the two distributions [[Distribution comparison formulas]] 

at best case of training the fake = real = 50% i.e. good discriminator doesn't which to decide

[[intuition of GAN tranining]]

### training
![](attachment/af7f149f1d754238a4a0adb3eb5f62d9.png)

1st term if we sampled an image from the data the D want to classify = 1 (real)
2nd term in if we sampled an image from the Z latent space the DG(z) term:
* the D want it to be = 0 (fake)
	* thus, D want to maximize this side (1-DG(z))
* the G want it to be = 1 (real)
	* thus, G want to minimize this side (1-DG(z))


### gradient
![](attachment/67067b3ccb2d35cf9cfd9cbb78e2b5ad.png)
We are not minimizing any overall loss! No training curves to look at! 😢

the second case of #vanishinggradient but in the beginning of the training 
![](attachment/575c70370488475363802c3c71a9ed6b.png)

Optimal training case
	This minimax game achieves its global minimum when pG = pdata!


optimality proof
[[optimality proof]]
![](attachment/fe74c116b280599b586eb784bd5490a2.png)

### training problems of GANs
vanishing gradients is solved
![](attachment/2fe249247b8c4e8ff08cc218b2121073.png)
3) training oscillation in the min max property![](attachment/c24c6b71df95b432aa691289fc0fd214.png)
state 1: x, y are + then v is +
max(y) will maximize y and min(x) will minimize x
state 2: x is - and y is + thus v is -
max(y) to maximize y it will make it - to make v +
… till return to the first state

4) same generated class from G to get maximum reward from D ![](attachment/7fa60d60ebca3238c6588d18ead960d0.png)
5) the Distribution divergence formula can make very big difference in the training
![](attachment/f035a03d130bb6a0e7c5e058061419a1.png)
![](attachment/52564a242f32abb166cc37a2caca4286.png)
-> solution
![](attachment/d0d227bc18bdc319d6b388d173c3af88.png)



[[pros and cons]]
### [[GAN Improvements]]
