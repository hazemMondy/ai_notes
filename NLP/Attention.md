* attention for each word in output come from what in the input
* remove overhead on decoder 
* is where to look for late words to get the corresponding relevant inputs

#web 
This model allows an RNN to pay attention to specific parts of the input that is considered as being important, which improves the performance of the resulting model in practice. By noting $\alpha^{< t, t'>}$ the amount of attention that the output $y^{< t >}$ should pay to the activation $a^{< t' >}$ and $c^{< t >}$ the context at time $t$, we have:

${c^{< t >}=\sum_{t'}\alpha^{< t, t' >}a^{< t' >}}\quad\textrm{with}\quad\sum_{t'}\alpha^{< t,t' >}=1$ 

Remark: the attention scores are commonly used in image captioning and machine translation.
Attention weight -- The amount of attention that the output $y^{< t >}$ should pay to the activation $a^{< t' >}$ is given by $\alpha^{< t,t' >}$ computed as follows:

$\alpha^{< t,t' >}=\frac{\exp(e^{< t,t' >})}{\displaystyle\sum_{t''=1}^{T_x}\exp(e^{< t,t'' >})}$

Remark: computation complexity is quadratic with respect to $T_x$.

![](attachment/c82fffb924753643a2f2d9e9f460c300.png)
MLP: multi layer perceptron (NN)
![](attachment/294e6caaa730f27daf82e667432d0e39.png)
$c_t$ helps with long sequences

![](attachment/3732d439a0a57679ce96b847769b6349.png)


![](attachment/c72405e9c2e9cec3a07af791e8e69923.png)


### advantages
Interpretability 
![](attachment/5c0a9186c82aac5f2519c7cd5ff60964.png)

### examples

![](attachment/0622384cf8424a612ceb52189c1c5505.png)
Each timestep of decoder uses a different context vector that looks at different parts of the input image

![](attachment/0a4a2290633872332f944ca2ca8f4e13.png)





