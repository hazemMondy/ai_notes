
Q: What happens if we initialize all W=O, b=O?
A: All outputs are O, all gradients are the same! No "symmetry breaking"
i.e. no training will happen
![](attachment/154f8b8fc76eb9cf64b9ac4a98576f6a.png)
	for vanishing and exploding gradients



![](attachment/3a9bde9879656343b7a28e307a76e1ab.png)
![](attachment/33628f0641f072c3b61db5d5c5465e3b.png)


### xavier init
![](attachment/7c1af058e6545e2002d06f5e4a2fd990.png)
![](attachment/6c44475a8b50613a4d4c004de53ddf8a.png)
Xavier assumes zero centered activation function
-> ReLU correction: std = sqrt(2 / Din) (takes half of the range (+))

![](attachment/6153fcb60cf573a5ec1990813d48075c.png)