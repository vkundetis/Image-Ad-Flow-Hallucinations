## Optical Flow Hallucinations for Pitt's AD dataset
Im2Flow's implementation for flow hallucination was used to generate these predictions. Their implementation and project page can be found here: [[Github Repo]](https://github.com/rhgao/Im2Flow)    [[Project Page]](http://vision.cs.utexas.edu/projects/im2flow/)
### Optical Flow Hallucinations
The zip file located in the folder predictions contains the pixel representations of flow for the ads dataset.
### Drawing Flow Vectors
These pixel level representations of flow can be visualized by drawing flow vectors. This can be done as follows:
1. Download Pitt's image-ad dataset, which can be found here: [[Image Ads]](http://people.cs.pitt.edu/~kovashka/ads/#image).
2. Move the images you want to visualize into a folder named `/input`. Move the corresponding flow hallucinationsm for the images into a folder named `/output`.
3. Run the following code: 
```Shell
  python visualizeFlow.py --flowImgInputDir output/ --rgbImgDir input/ --arrowImgOutDir visualization
  ```
The folder `/visualization` will be created, which will contain the images with drawn on flow vectors.
 
### Observations
Due to diversity of the dataset, the performance of the model on our dataset seemed to have high variance, however their were images that appeared to provide promising results. I observed these patterns from flow hallucinations generated from a random subset of Pitt's ad dataset. These appear to be biases created from the training dataset (HMDB-51). A relatively simple dataset of primarily humans doing everyday tasks. <br/>

1. **Single/Focused Object -** Model performed better when there was a clear, single object as the focus of the ad. Many of the videos in HMDB-51 had a single object in focus, which I believe is the likely reason for this.
2. **Realistic Objects -** The results tended to be better on realistic objects, and it appeared to be thrown off by the abstraction in many ads.
3. **Typical Objects in Motion -** The model performed better on objects of humans/animals, or objects that you would typically expect to be in motion versus those that would typically be static.

### Ideas for Future Work

1. **Improve Flow Prediction -** The Im2Flow model could possibly be improved by training it on Pitt's video ad dataset. This is a more complex dataset than HMDB-51, which could improve flow hallucinations on images.
2. **Generate a performance metric -** The model did not show consistant results for images on our dataset. A robust performance metric that uses both the flow prediction and base image would be useful for determining cases when we should or should not use flow for interpreting.
