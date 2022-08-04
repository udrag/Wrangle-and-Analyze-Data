# WeRateDogs Wrangle Project

Real-world data rarely comes clean. Using Python and its libraries, I tried to gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. I have documented the wrangling steps in a Jupyter Notebook, plus showcased them through analyses and visualizations using Python (and its libraries).

The aforementioned dataset is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.

WeRateDogs downloaded their Twitter archive and sent it to Udacity via email exclusively for the students to use in one of the projects. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 2000+ of their tweets as they stood on August 1, 2017.

## The Data

This project, I have worked on the following three datasets.

### Enhanced Twitter Archive

The WeRateDogs Twitter archive contains basic tweet data for all 2000+ of the tweets, but not everything. One column the archive does contain though: each tweet's text, which we used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." Of the 2000+ tweets. The dataset has been prior filtered for tweets with ratings only (there are 2356).

The data has been extracted this data programmatically, but this hasn't been done very well. As you will see in the first part, the ratings aren't all correct. Same goes for the dog names and dog stages. Therefore, I have assessed and cleaned these columns in order for these to be used for analysis and visualization.

### Additional Data via the Twitter API

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data has been gathered from Twitter's API.

### Image Predictions File

The images in the WeRateDogs Twitter archive have been ran through a [neural network](https://www.youtube.com/watch?v=2-Ol7ZB0MmU) that can classify breeds of dogs. The results: a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

#### So for the last row in that table:

• tweet_id is the last part of the tweet URL after "status/" → https://twitter.com/dog_rates/status/889531135344209921

• p1 is the algorithm's #1 prediction for the image in the tweet → golden retriever

• p1_conf is how confident the algorithm is in its #1 prediction → 95%

• p1_dog is whether or not the #1 prediction is a breed of dog → TRUE

• p2 is the algorithm's second most likely prediction → Labrador retriever

• p2_conf is how confident the algorithm is in its #2 prediction → 1%

• p2_dog is whether or not the #2 prediction is a breed of dog → TRUE

• etc.
