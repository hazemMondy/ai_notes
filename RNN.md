
|   |   |
|---|---|
|**Advantages**|**Drawbacks**|
|• Possibility of processing input of any length  <br>• Model size not increasing with size of input  <br>• Computation takes into account historical information  <br>• Weights are shared across time|• Computation being slow  <br>• Difficulty of accessing information from a long time ago  <br>• Cannot consider any future input for the current state|

+ Vanishing/exploding gradient The vanishing and exploding gradient phenomena are often encountered in the context of RNNs. The reason why they happen is that it is difficult to capture long term dependencies because of multiplicative gradient that can be exponentially decreasing/increasing with respect to the number of layers.
+ Gradient clipping is a technique used to cope with the exploding gradient problem sometimes encountered when performing backpropagation. By capping the maximum value for the gradient, this phenomenon is controlled in practice.
![](attachment/488dab2e28e016ea0f0ab6686b95be16.png)

- **How does a RNN solve the curse of dimensionality problem incurred by n-gram language models?**
    
    It is solved since the weight matrices are applied at every step of the network. Hence the model parameters don't grow proportionally to the input sequence size. The number of parameters is independent of the sequence length.
    

- **What is the loss function of a RNN?**
    
    Cross-entropy summed over a corpus of size T and a vocabulary of size V.

- **What are advantages of RNN?**
    - They can process input sequences of any length
    - The model size does not increase for longer input sequence lengths
    - The same weights are applied at every time step of the input, so there is symmetry in how inputs are processed

- **Give an example of the vanishing gradient problem in RNN and explain it.**
    
    > S1: 'Jane walked into the room. John walked in too. Jane said hi to _?_'.
    > 
    > S2: 'Jane walked into the room. John walked in too. It was late in the day, and everyone was walking home after a long day at work. Jane said hi to _?_'.
    
    In both cases, the RNN should predict John as an answer. However, in practice, it turns out the RNN is more likely to predict John in sentence 1 than in sentence 2. Indeed, during backpropagation, the contribution of gradient values **gradually vanishes as they propagate to earlier timesteps**. Thus for long sentences, the RNN is less likely to recall information introduced in the earliest part of a sentence.
    

- **How to solve vanishing gradient problem?**
    
    **Technique 1**: Instead of initializing W randomly, start off from an identity matrix initialization.
    
    **Technique 2**: Use ReLU as an activation function since the derivative of the gradient is either 0 or 1. This way, gradients would flow through the neurons whose derivatives is 1 without getting attenuated while propagating back through time-steps.
    

- **What are exploding gradients and give a technique on how to solve them?**
    
    The explosion occurs through exponential growth by repeatedly multiplying gradients through the network layers that have values larger than 1.0.
    
    A technique to solve exploding gradients is gradient clipping. Gradient clipping is a simple heuristic invented by Thomas Mikolov to counter the effect of exploding gradient. That is, whenever the gradient reach a certain threshold, they are set back to a small number.
[[cheatsheet]]

no. of inputs and outputs determines the application 
![](attachment/d9d7238d0a3834cc6897f5ebf3cb2d49.png)

one to one : e.g. Image classification Image ‐> Label
one to many: e.g. Image Captioning: Image ‐> sequence of words,,, Music generation
many to one: e.g. Video classification: Sequence of images ‐> label
many to many: e.g. Machine Translation: Sequence of words ‐> Sequence of words
but it computed as one network (i.e. not encoder decoder arch.)

![](attachment/974b9394febfd7ccee55e1429b3e4d61.png)
Key idea: RNNs have an “internal state” that is updated as a sequence is processed
old state has the history from the beginning till the last state
![](attachment/d0381f93409e61d31c19598c688987c5.png)


Initial hidden state Either set to all 0, Or learn it

Re‐use the same weight matrix at every time‐step
![](attachment/f80206e67ef5f52a62b3f107db9bc695.png)
L is the loss
![](attachment/fb9b4c6ac3232107b9b95f4fdcb4ce90.png)
![](attachment/aed2c5d54ec31a10a22feb2663cb9729.png)



### the second method SEQ to SEQ
![](attachment/dac27cacb8ee230717ff1fa0c784a120.png)
like encoder decoder arch

* disadvantages:


![](attachment/9f1f4f709d1c4f1d4a540a553768a8c6.png)
![](attachment/b1de409d22846b7ef2a540934f57d9b3.png)


### backpropagation
![](attachment/280eaff4b64e2484b560448fc5ac1e7d.png)
-> solution
Run forward and backward through chunks of the sequence instead of whole sequence
![](attachment/c8d8a057ea02e2d88de97e742d2586ed.png)



### multi-model
![](attachment/6ad72ab0d18f65eaab17eb156181ec50.png)
Transfer learning: Take CNN trained on ImageNet, chop off last layer
![](attachment/68ce5f0b35d44580c9071638c44ca441.png)
![](attachment/6eb418c4047ba73ca79d9ba4f0d6f2cc.png)
Sample word and copy to input till the end of sequence


### normal prediction - backpropagation flow
![](attachment/20a624f4aa5844ad63aeb9898397a319.png)
![](attachment/3404ad660555b9edeed10e4e3aa88b99.png)

Vanishing gradients-> Change RNN architecture!