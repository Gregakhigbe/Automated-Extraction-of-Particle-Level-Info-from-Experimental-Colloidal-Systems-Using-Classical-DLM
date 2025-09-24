# Automated-Extraction-of-Particle-Level-Info-from-Experimental-Colloidal-Systems-Using-Classical-DLM
This research aims to develop an automated image analysis pipeline capable of extracting position, orientation, size, and shape parameters of core–shell ellipsoidal colloidal particles at liquid interfaces, and to rigorously compare its performance with established methods in the literature. By directly benchmarking deep learning and classical image processing approaches, the study will assess differences in accuracy, robustness, and computational efficiency. The research will follow these steps:

Data Collection
A core resource for this project is a microscopy image dataset of core–shell ellipsoidal particles adsorbed at liquid interfaces, generously provided by my supervisor, Dr. Jack Eatson (Eatson et al., 2025). This dataset, acquired under controlled experimental conditions, offers high-resolution images capturing particle configurations and orientations essential for training and validating automated analysis algorithms. If dataset size proves insufficient for robust deep learning model training, a synthetic microscopy image generation pipeline will also be developed following the principles outlined by Chatterjee and Byun (2023). This synthetic data will augment the training set by simulating variations in particle number density, orientation distributions, and imaging noise, improving the model’s capacity to generalize across diverse conditions.

Data Preprocessing
Images will undergo standard preprocessing steps to enhance quality and consistency. Preprocessing will include normalization to correct illumination and contrast variations, noise reduction using morphological and median filtering, and background subtraction to isolate particle regions.
These steps are necessary to ensure reliable segmentation and feature extraction, particularly given the variability in experimental image quality


Feature Selection
The core pipeline will implement a deep convolutional neural network (CNN) architecture inspired by the approach of Bals and Epple (2023), tailored for segmentation and morphological analysis of ellipsoidal colloidal particles. The network will:
•	Segment individual particles from the background
•	Extract positional coordinates (centroids) of particles
•	Quantify size by measuring major and minor axes
•	Determine particle orientation in the plane of the interface relative to the image frame.
The model will be trained on a labelled subset of the Eatson dataset, which includes particle positions, in-plane orientations, and sizes obtained using the ML algorithm described in Eatson et al. (2025). It is acknowledged that using these labels may bias the results toward the original model. If feasible, a small subset of images will be manually verified or relabelled to assess this effect. Supervised learning with data augmentation (random rotations, scaling, noise injection) will be employed to enhance robustness. Performance will be validated on a reserved test set to prevent overfitting.
