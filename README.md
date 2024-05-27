# About

## Abstract
This model suggests an approach that can produce lifelike piano compositions autonomously through the utilization of General Adversarial Network (GAN) introduced by Ian Goodfellow in 2014. The generated piano music has a duration of 37 seconds and is created from a 14-dimensional latent vector. Training is conducted using the <a href="https://www.kaggle.com/datasets/jackvial/themaestrodatasetv2">MAESTRO V2 dataset</a>. The model is developed using `Tensorflow` and entirely coded in `Python`.

## Detailed

This repository presents a deep learning model that produces lifelike piano music autonomously from a 14-dimensional latent vector using General Adversarial Network (GAN). The `midi2img.ipynb` file converts midi files into images, where each image represents the pitch versus time distribution of the midi file in `png` format. The `midi2image.ipynb` processes 300 notes from the midi, producing the corresponding distribution; the quantity of notes can be adjusted as needed. These `png` images form the training dataset for the model. The model generates a `png` image, which is then transformed into `midi` using image2midi.


These images are utilized in training the proposed model. The generator learns and replicates the distribution, while the discriminator distinguishes between the actual (real) and generated (fake) distributions. Training concludes once the discriminator can classify each distribution with approximately 0.5 probability, typically after 3000 iterations. At this stage, the generator has effectively learned the distribution and can produce identical new distributions.

The GAN consists of two models: the generator and the discriminator. The generator comprises 3 Convolutional layers, 3 Upsampling layers, and one dense layer with leaky ReLU activation. Taking a 14-dimensional latent vector as input, the generator generates images sized at 106x300x1. The discriminator, responsible for discerning real from fake distributions, consists of 5 Convolutional layers and one dense layer with Leaky ReLU and sigmoid activation. It assesses input images of size 106x300x1 to classify them as real or fake.

# Highlights

Pitch vs time distribution of generated file

<img width="497" alt="Screenshot 2023-04-13 at 2 26 12 PM" src="https://user-images.githubusercontent.com/76246981/231954874-40aa4d35-4aba-4a16-927e-565b1975c558.png">

The generator

<img width="512" alt="Screenshot 2023-04-13 at 2 30 24 PM" src="https://user-images.githubusercontent.com/76246981/231955239-ab1404e8-d28f-4ec0-932d-05897e2cbf21.png">

The discriminator

<img width="521" alt="Screenshot 2023-04-13 at 2 30 45 PM" src="https://user-images.githubusercontent.com/76246981/231955277-f8071be6-196f-4483-959b-7193b52190a5.png">

# Prerequisites

`Python>=3.6`

# Getting started

1. Download the repository and unzip it.
2. Install necessary packages using `pip install -r requirements.txt`.
3. Run the `load_model.ipynb` to generate `png` images and after that run `img2midi.ipynb` to convert it into `midi` files.
4. If you want to convert midi to wav, run `midi2wav.ipynb` file.
5. Read the `instructions.txt` for better understanding of repository.
