eural Style Transfer Project
Project Components
The repository contains the following three core files:


Notebook (nst-final-project.ipynb): A hands-on implementation of the NST algorithm using Python, Keras, and TensorFlow.


Report (NST_report.pdf): A detailed technical paper covering the mathematical background, architectural workflow, and optimization algorithm comparisons.
+1

Presentation: A visual summary of the project goals, methodology, and results.

How It Works
The project utilizes the VGG19 architecture, a pre-trained convolutional neural network (CNN), to extract and manipulate image features.

1. Feature Representation
The network is used to capture different levels of information from the input images:


Content Representation: Extracted from the conv4_2 layer to maintain the primary objects and arrangement of the original scene.


Style Representation: Extracted from multiple layers (conv1_1, conv2_1, conv3_1, conv4_1, conv5_1) to capture a hierarchy of artistic textures, from colors to complex brush strokes.

2. Loss Functions
The generated image is iteratively updated by minimizing a total loss function comprised of three components:


Content Loss: Measures the L2 distance between the content image and the generated output.


Style Loss: Calculated using Gram matrices to compare the texture correlations between the style source and the output across multiple VGG layers.


Total Variation Loss: Acts as a denoising factor to ensure spatial continuity and visual coherence in the final output.

Workflow & Architecture
The workflow starts by cloning the content image and then iteratively adjusting its pixel values via gradient descent based on the calculated losses.

Optimization Algorithms
The project includes a comparative analysis of different optimization methods:


Adam: Simpler with lower computational cost per step, but requires many iterations to converge.


L-BFGS-B: A quasi-Newton method that reaches convergence in fewer iterations and yields qualitatively sharper images, though it is more computationally intensive per step.
