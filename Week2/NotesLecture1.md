
Recap:
  Why image classification is Hard ?

  The idea of data driven approach with test data and training with segments of data.

  Linear Classifier for cat recognition.

  Loss function and now we will discuss how to minimize the loss

Multi-class SVM loss:

  Sums along the incorrect classes. It compares the different the score of correct class identified with score incorrect class received.

  Not only we say, we want the correct class score to be higher than incorrect one but we make sure it is higher with a safety manager which is 1.

  These scores are scale free. Using 1 is arbitrary choice.

  Loss =0 means what ?
  Each wrong label score is at least greater than 1.

  What if we just sum over all classes instead of just to wrong ones ?
    If we do calculate the loss over correct ones too then it will 0 and we will end up with the sum just inflated by our offset. in this case it is just 1.

Initially, at the start of the training weights will be small and hence the individual class wise loss scores be almost class number -1 . and average would be almost 2. So this value can be used as our checkpoint to be sure that we are still using the correct way for calculating weights.

Weight regularization :

it measures the niceness of weights, in the end test results improve.

L2 regularization: we take squares of the loss scores.
Why regularization: if we have x =[1,1,1,1] and
w1=[1,0,0,0]
w2=[0.25,0.25,0.25,0.25]

Which weight vector is better? Although we have same dot product ?

w2 : as it takes more number of pixels into considerations. instead of just focusing on one factor. So we prefer diffused weights.

Softmax Loss(Multi-nominal Logistic Regression):

  We calculate the log likelihood of the class scores. So we want to maximize the correct class score and we want to minimize the likelihood score of incorrect class

  for checkpointing during our iteration , we can verify that it is is calculating correct values or not, by taking into consideration the fact that, initially all w's are small and hence the scores would be almost zeros. and hence the exponent is 1 and normalization to it would give 1 over number of classes and hence -ve log of number of classes.


Now how to determine the weights?

  1) Randomization and checking for loss:
        -Poor accuracy
  2) Following the slope:
     Finding gradient at given weight
     It is approximate
     it is slow: as we have to take for each dimension and for each parameter so in neural network there can be millions of params.

  3) Analytic gradient:
     With calculus we get an expression so it is easy to calculate
     So idea can be visualized as it is a a particle moving towards the center.


Gradient Decent:
    1)we evaluate decent with loss fun and data and weights
    2)Then weight is updated with step size and weight gradient obtained in step 1.

    In practice :
    we don't calculate loss for all the data.
    we take few data points from the data set for compute the gradient.

    Use batch sizes such that it will suit to your memory.


Effect of Step Size/ Learning Rate on loss function:

    we need to find a correct learning rate as we can bounce back over back and back to local minima instead to settle down to the global minima.

    so we in practice we take high learning rate and then we decay the learning rate.

Effect of Update formulas:

    there are different types of formulas for updating the weights and each one performs differently on different problems. Some would perform better than other and some won't.


Computer Vision Before 2012 and After 2016:
    We defined the features and computed scores.
    But in Deep leaning : we don't define features instead we calculate weights and loss function and we try to minimize loss and get ultimately class scores. Here we are considering data of all the pixels. Which turns out to be more robust.
