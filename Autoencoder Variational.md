intro : [[Autoencoder Regular]]


> Z is not vector of scaler values 
	now its a probability p(x | z)

![](attachment/7759311f541172d19b407f14cfc99021.png)
![](attachment/dd649bfa8d3b02b90ff9deaa87f8ccfa.png)

If we could observe the z for each x, then could train a conditional generative model p(x | z)
![](attachment/b564cd9382fc2aafbcff01b160ae5a15.png)
p(x | z), can compute this with decoder network
p(z), we assumed Gaussian prior for z

Problem: Impossible to integrate over all z!
-> Solution: try bayes rule p(x , z) = p(x | z) p(z) = p(z | x) p(x)
![](attachment/2fb4f63689b6ca8685c19538a9690c0e.png)
-> Solution: Train another network (encoder) that learns **q**(z | x) ~= **p**(z | x) 
![](attachment/4ea35da20201be85a212837f7eefcf04.png)
![](attachment/2403851cef6275b0006a052ce3a46a0a.png)

VAE provide solutions to these two difficulties of latent variable models:

1. How to define the latent variables z
2. How to deal with integral over z

![](attachment/a576b00a12d7d2d3f1757a1588f3d102.png)
the loss function is just the reconstruction loos ($||\hat{x} - x||^2$) 
regularization is for measuring how much the inferred data distribution differ from our prior hypothesis (guess about how the data latent variable space may look like) (little gaussian circles from [[latent variable models]])  $D_{kl} (q_{\phi} || P(z))$ to constrain them (the encoder) to stay or follow that prior distribution p(z)

Encoder = compress data into loy.ver-dimensional representation (latent space)
![](attachment/3ee3906b1e5a939763bd5ce148dbdb8c.png)
[[intuition and regularization and prior in the latent space]]




#### training 
[[VAE training]]

### example 
![](attachment/f3eca64b5187b20d719bbab048ab16ff.png)

it must have ReLu (any activation) in between
Covariance matrix should be 20x20, but we approximated it to take the diagonal only **assumption** 

[[VAE Understand the Z features]]
[[VAE code]]

[[GANs]]
[[GAN code]]

