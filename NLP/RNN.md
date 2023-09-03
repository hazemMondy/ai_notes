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


[[NLP cheat sheet]]
