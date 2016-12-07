Computational Graph:

input data and parameters are passed through Computational Graph and at the end we get one number as loss function.

In Computational Network we will have input images  then we have a very data intensive and Computational intensive nodes.

on a similar notes we can derive the analogy for the neural Turing Machine, the tape would be a thousands of nodes, so we can think of those in terms of data structures.

how we can come up with gradients which will lead to the a final loss function


So gradient in terms can be interpreted as the rate at which it affects the output
At each node we want to calculate how each input is having effect on the output of the node.

Chain Rule usage?

for the intermediate nodes we won't be knowing the direct effect of the input of the current node onto the final loss value. So we can calculate that with the help of chain rule.


 Demo run down for a circuit:
  Each node has input and final output is given, so we start to do back propagation, and use of chain rule if we donw have all the values.
  This is to understand in better way about the gradient decents in the net so that it will be easy for us to debug some issues in the weights if any.
  As we start from the last node, we have local gradient in terms of functions say (1/x or ax) and we get a value which indicates its direct effect on the output. No we use these values and plug those in for the rest of the nodes.


in Caffe= top diff is equal to the gradient and in Torch it is gradient (Just about the naming convention)

Forward computes the loss, backward computes the  gradient and update uses the gradient change the weights little bit and this process goes on.
