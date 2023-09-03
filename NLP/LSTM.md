change the vanilla arch to have multi paths for gradient to  overcome the vanishing gradient
![](attachment/58f684c4258bc2a421b76a0586c9daf7.png)
->
![](attachment/9b6de11e0df93029244e4a2067a211ba.png)

key differences:
add two sources of history ( Cell history c, history h)

the new "cell state" channel -> made The LSTM have the ability to remove or add information to the cell state using gates

![](attachment/96f2b804641ec025760752227c7c4b96.png)


![](attachment/54573f403612f094235c9144e2dea8cc.png)



![](attachment/e98db0071c969834986132928543b344.png)
$i_t$ is the output of sigmoid it decides what parts of the current history to take from $\tilde{C}_t$
$f_t$ decides the previous cell history 
then update
 
![](attachment/23a7d5b3e66a8a2dcc4545ac039d0070.png)
*_Decide what to output based on the memory._


[[LSTM types]]

### summary
![](attachment/7f689eda0406df19f0fa361ee6702bc0.png)

### training gradient flow
![](attachment/0d97f1d904a98ffacb1a7ad168f69714.png)

![](attachment/a5dbf0ab7ba7e3c0b9bd76366243a1fe.png)


