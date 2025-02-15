# Classification_Three_Ways

*  Three types of classification models, SVMs, K-Nearest Neighbours, and Random Forests.
*  Introduce confusion matricies, which are a good way to visualise performance.
*  Look at how we select hyper-parameters, and ways to help automate this process

# Classification_HOG

HOG will take an image and divide it into a grid. Within each grid cell, it will look at the gradients of the pixels. The gradient of each pixel is characterised by a magnitude, and a direction. The magnitude tells us how strong the gradient is, the direction simply tells us in which direction the gradient is moving. Strong gradients correspond to edges, and with the direction we can determine if the edge is a vertical, horizontal, or something else. All up, this gradient information tells us about the local texture in the patch. When we aggregate patches across the image, we get an idea of the gradient/texture across the image, and we can use this as the feature to represent the image. Compared to raw pixels, we get:

*  A more compact feature representation (unless we have tiny images)
*  Something that is invariant to small translations and shifts
*  Something that has at least some invariance to other external factors (lighting, etc).

# Classification_BoW

Bag of Words is a feature transform that allows us to go from a variable length sample to a fixed length representation. To do this, we transform our data into a histogram, that measure how many instances of each word we have. There are a few steps involved in this:

*  Clean the text. This means usually converting to lower case, removing punctuation, removing stop words, performing lemmatisation
*  Build a dictionary. This contains all possible words. We may at this point choose to exlude words that are very rare (if they're very rare, it's harder for our model to understand their meaning), very common (if they're very common, they're probably not much use for discriminating between classes), or just take the top N words to avoid having histograms that are too big.
*  Convert our text into a Bow of Words via the dictionary. This will take us from a variable length text sample to a fixed length histogram. Each word in the dictionary will have an entry in the histogram. The value in the histogram will be how many times that word occurs in the sample.
