Image Classification:

Why it is difficult ?
  1) Images are in pixels. Each pixel with RGB so they are 3D arrays and each value is between [0,255].
  2) The camera can be rotated around a cat, zoomed, what happens about the brightness?
  3) Deformations of the object.
  4) Occlusion : sometimes we can just see part of it.
  5) Background Clutter: Things can blend into environment.
  6) Intraclass variation: cats and their different types/ breeds.


Past attempts:
  1) we came up with rules for edges and so on.


Now Data Driven:
    Collect data, apply ML, evaluate classifier.

Simple classifier : Nearest Neighbor classifier
  Remember training and images. Then predict label of the most similar training image.

  Distance Matrix: Manhattan Distance
  Just subtract the data of the pixel values we get final Sum of Distances indicating and we get how far is one image from the other.

How it performs?
  As training data increases it would be linearly increasing.

  But for CNN it will be constant time once it is trained.

What will be the accuracy for NN when we use Euclidean Distances?
    > As each time training data would be mapped to one category and it will always return a result and hence the accuracy is 100 %.
    same can not be said for the K NN classifier, as there can be mapping for two categories.


What are hyper Parameters: These are the factors which we consider as a computing tool which will set apart the each category.Eg. Manhattan Distances, Euclidean Distances

Best Practices for choosing the Hyper Parameters:
  In order to get the most accurate results: As we don't know what Parameters would be best to use, we should try out few. But how?

  1) Our aim is to generalize for the unseen data. How to do that?

     > "Forget we have test data"

     using data in folds. like 80% from the training data and check it its performance on the remaining 20% of the training for validation. it is Validation Data.

     Cross Validation: By taking into consideration of combination of folds and testing on to remaining one fold for validation. Cycle through it.

     we get performance in terms of accuracy and at certain point we can get best results so choose those values and finally go for test data. Now this will be used for all the reporting later on.

Why K-Nearest on images is BAD?
    Distance metrics would vary a lot due to different values of brightness. etc.
    SO bad time performance for the test data.


Linear Classification:  (Cool Stuff Now which will lead to the CNN):

  NN are like lego blocks and they can talk to each other.

Parametric Approach:
  1) construct a function  such that takes an images and defines a class scores in terms of numbers say classes are 10.

  Data of 32*32*3 so [0-3071] into numbers [0-10]. So cat score should be highest for the cat pic.

  So we take the image data of 3072 matrix and it is arranged in one column. Now weight/parameters is ideally such a way that it will give correct score for cat image.
  So W will be of (3072 * 10) Matrix

And we have Bias Factor : It is for the fact that if the data is skewed then it will be more likely to predict for cats only even in case of if it is a dog.

So we get finally Dot product as score for classes.

f(x,W,b)=Wx +b

In a simple way to put it:

Every single score is weighted sum of each pixels. So it is calculating color at each pixel at each spatial position.

So once we train, we get an image for each class in a way such that we have color blob. So positive weight will be more where blue is more for airplane example. And negative weight implies not relevant to that pixel for given class.

So depending data we provide it will generalize to it. Ex. Horse is facing two ways so generalized image will have two heads.

The heuristic of average of color would perform?
  > it won't perform as efficient as linear

Gray scale images would perform would better right?
  >If in the data more red cars are present then template would have more red. what about yellow cars?
    So in a way linear classifier won't capture all the features, But now imagining the training data everything in gray scale would cause all the generalization about color so it would depend on just texture and just edges sort of and would perform very poorly.

Loss function :

  In order to define what is good Weight ?
  we start with random W and find W that minimized the loss. Then we can tweak the functional form

f(x,W)=W x

So our aim would be how to minimize the losses and get the best weights ? We tweak the function and get neural network and get Convolution finally. Stay Tuned !
