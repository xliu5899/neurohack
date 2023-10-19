# neurohack

From the hackathon at NeuroHackademy 2023

### cnn_preproc
contains the preprocessing steps for creating the input to a convolutional neural network (CNN). The input are 2D image files of 5s intervals of BOLD activation during movie-watching sorted randomly into train/test directories. The CNN will classify based on whether the 5s interval contained a social or non-social scene
1. takes as input CIFTI files from the Human Connectome Project (HCP) 7T release representing fMRI data during movie watching
2. creates flattened images for each TR (1000ms) of BOLD activation across the cortex by hemisphere and centered at (1) frontal and (2) occipital poles.
3. combines the 4 viewpoints of cortical BOLD activation into a single image for each TR, then averages across every 5 second interval
4. **IV**: imports categorical movie data created elsewhere which labels each 5s interval in the movie clip as social (containing more than 1 face) or non-social (containing 0 or 1 human face)
5. allocates image files randomly into 70/30 train/test split - ready for CNN

### cnn_model
contains the code for the CNN and its accuracy
