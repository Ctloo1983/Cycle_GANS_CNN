# Cycle_GANS_CNN

Table of Contents:
Introduction
Requirements
Installation
Data Preparation
Training
Testing
Results
Comparisons
Future Work
Citation
License

#### Introduction
This repository contains the implementation of a HSLU Computer Vision project that explores the use of Cycle GANs (Generative Adversarial Networks) along with Convolutional Neural Networks (CNNs) to perform Neural Style Transfer. The goal of this project is to investigate the capabilities of GANS and different CNN architectures , specifically VGG19 and ResNet50, in transforming the style of images to mimic the artistic styles of renowned painters like Monet and Candido.



#### Requirements
Python 3.x
PyTorch
NumPy
Matplotlib
OpenCV


#### Installation
###### Clone the repository
git clone https://github.com/ctloo1983/Cycle_GANS_CNN.git

###### Navigate to the project directory
cd Cycle_GANS_CNN

###### Install dependencies
pip install -r requirements.txt

Methodology
For the computational backbone of this research, we leveraged the TensorFlow framework for ease of model implementation and scalability. The primary model employed was a Cycle Generative Adversarial Network (CycleGAN), formulated to work with unpaired image-to-image translation tasks. The dataset was sourced from the Kaggle competition entitled "I’m Something of a Painter Myself," which provided a robust set of 7,028 paired images—original photographs juxtaposed against their Monet-stylized counterparts.

Model Architecture
The CycleGAN architecture is compartmentalized into two distinct generators and two discriminators. Specifically, 
�
�
�
G 
AB
​
  and 
�
�
�
G 
BA
​
  serve as the generators that map images from domain 
�
A to 
�
B and vice versa. Discriminators 
�
�
D 
A
​
  and 
�
�
D 
B
​
 , on the other hand, discern the authenticity of images from domains 
�
A and 
�
B, respectively.

Objective Function
The loss function used for this experiment is a weighted sum of adversarial and cycle-consistency losses. Mathematically, it can be expressed as follows:

�
(
�
�
�
,
�
�
�
,
�
�
,
�
�
)
=
�
GAN
(
�
�
�
,
�
�
)
+
�
GAN
(
�
�
�
,
�
�
)
+
�
�
cyc
(
�
�
�
,
�
�
�
)
L(G 
AB
​
 ,G 
BA
​
 ,D 
A
​
 ,D 
B
​
 )=L 
GAN
​
 (G 
AB
​
 ,D 
B
​
 )+L 
GAN
​
 (G 
BA
​
 ,D 
A
​
 )+λL 
cyc
​
 (G 
AB
​
 ,G 
BA
​
 )
Here, 
�
GAN
L 
GAN
​
  denotes the adversarial loss and 
�
cyc
L 
cyc
​
  the cycle-consistency loss. 
�
λ is a hyperparameter to control the weight of the cycle-consistency term.

Training Process
The training regimen involves several epochs of forward and backward propagation through both the generator and discriminator networks, in an alternating fashion. Optimization was performed using the Adam optimizer with a learning rate dynamically adjusted based on the training progression.

Results
Our CycleGAN model exhibited compelling capabilities in the transformation of original photographs into Monet-inspired art forms. Qualitatively, the output images maintained a high level of artistic fidelity, encapsulating the intricate brush strokes and color palettes characteristic of Monet’s oeuvre.

Limitations and Future Work
However, the model is not without its limitations:

The translated images occasionally exhibited a lack of sharpness, veering towards a somewhat blurry aesthetic.
There were instances where the color mapping was not entirely accurate, leading to inconsistencies in hue and saturation.
These could potentially be mitigated in future iterations through the introduction of perceptual loss functions or by fine-tuning the model with a more extensive dataset.
