# Cycle_GANS_CNN

Table of Contents:

- Introduction

- Requirements

- Installation

- Data Preparation

- Training

- Results

- Limitations

- Future Work

- Citation

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

- Clone the repository:

git clone https://github.com/ctloo1983/Cycle_GANS_CNN.git

cd Cycle_GANS_CNN

pip install -r requirements.txt

#### Methodology
For the computational backbone of this research,we bought a Google Colab+ 500 compute units paid subscription and used the TensorFlow framework for ease of model implementation and scalability. The primary model employed was a Cycle Generative Adversarial Network (CycleGAN),followed by using other CNN architectures such as VGG-19 and ResNet-50, which was formulated to work with unpaired image-to-image translation tasks. The main dataset was sourced from the Kaggle competition entitled "I’m Something of a Painter Myself," which provided a robust set of 7,028 paired images—original photographs juxtaposed against their Monet-stylized counterparts. Another larger dataset was sourced from the internet which contained paintings of Candido, a Brazillian Painter.

#### Model Architecture
The CycleGAN architecture is compartmentalized into two distinct generators and two discriminators. 

Objective Function
The loss function used for this experiment is a weighted sum of adversarial and cycle-consistency losses. 
λ is a hyperparameter to control the weight of the cycle-consistency term.

#### Training Process
The training regimen involves several epochs of forward and backward propagation through both the generator and discriminator networks, in an alternating fashion. Optimization was performed using the Adam optimizer with a learning rate dynamically adjusted based on the training progression.



#### Results
Our CycleGAN model exhibited some capabilities in the transformation of original photographs into Monet-inspired art forms. Qualitatively, the output images maintained a certain level of artistic fidelity, somewhat resembling the intricate brush strokes and color palettes characteristic of Monet’s paintings.

#### Limitations 

However, the model is not without its limitations:

The translated images occasionally exhibited a lack of sharpness, veering towards a somewhat blurry aesthetic.
There were instances where the color mapping was not accurate at all, leading to inconsistencies in hue and saturation.

#### Future Work
These could potentially be mitigated in future iterations through fine-tuning the model with a more extensive dataset, like the Candido paintings in one of the files above.

#### License
MIT License. 
