## Optical Flow Hallucinations for Pitt's AD dataset
Im2Flow's implementation for flow hallucination was used to generate these predictions. Their implementation and project page can be found here: [[Github Repo]](https://github.com/rhgao/Im2Flow)    [[Project Page]](http://vision.cs.utexas.edu/projects/im2flow/)
### Optical Flow Hallucinations
The zip file located in the folder predictions contains the pixel representations of flow for the ads dataset.
### Generating Flow Visualizations
To draw 
### Observations
Due to diversity of the dataset, the performance of the model on our dataset seemed to have high variance, however their were images that appeared to provide promising results. I observed these patterns from flow hallucinations generated from a random subset of Pitt's ad dataset. These appear to be biases created from the training dataset (HMDB-51). <br/>
1. Model performed better when there was a clear, single object as the focus of the ad. Many of the videos in HMDB-51 had a single object in focus, which I believe is the likely reason for this.
2. Recognize simple motions

### Ideas for Future Work
