
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

  Initially, at the start of the training weights will be small and hence the individual class wise loss score would be almost 0.   
