# Face Recognition With ArcFace

This repository contains the implementation of a face recognition system using the ArcFace method. The project includes training and evaluation scripts, datasets, and utility functions.

## Table of Contents

- [Introduction](#introduction)
- [Datasets](#datasets)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Evaluation](#evaluation)
- [Results](#results)
- [References](#references)

## Introduction

This project implements a face recognition system using ArcFace, a popular method for facial recognition. The implementation is based on the course materials from "BTK Akademi: Bilgisayarlı Görü Uygulama Alanları".

## Datasets

The project utilizes the following datasets:
- MS1M
- LFW (Labeled Faces in the Wild)

## Installation

To install the required dependencies, run the following command:
```bash
pip install -r requirements.txt
```

Ensure you have OpenCV installed. If not, you can install it using:

```bash
pip install opencv-python
```

## Usage

1. Clone the repository:

```bash
git clone https://github.com/FEgebilge/Face-Recognition-With-ArcFace.git
cd Face-Recognition-With-ArcFace
```

2. Prepare the datasets:
   - Place the MS1M dataset in the path specified in the configuration.
   - Place the LFW dataset in the path specified in the configuration.

3. Run the training script:

```bash
python train.py
```

4. Evaluate the model:

```bash
python eval.py
```

## Project Structure

```
Face-Recognition-With-ArcFace/
├── data/
│   ├── lfw.py
│   ├── ms1m.py
│   ├── eval_lfw.py
├── dataset/
│   ├── lfw_aligned_112
│   ├── lfw_pair.txt
│   ├── MS1M
├── models/
│   ├── arcfacenet.py
│   ├── ArcMarginProduct.py
├── utils/
│   ├── utils.py
├── train.ipynb
├── requirements.txt
├── config.py
└── README.md
```

## Configuration
Example configuration:
```python
config.train_root = '/path/to/MS1M'
config.lfw_root = '/path/to/lfw_aligned_112'
config.lfw_file_list = '/path/to/lfw_pair.txt'

config.mode = 'se_ir'
config.depth = 50
config.margin_type = 'ArcFace'
config.feature_dim = 512
config.batch_size = 128
config.lr = 0.01
config.milestones = [5, 8, 10]
config.total_epoch = 12

config.save_path = './saved'
```


## Evaluation
To evaluate the trained model on the LFW dataset, use the `eval_lfw.py` script. 


## Results
The results of the training and evaluation will be saved in the `./saved` directory. This includes model checkpoints, best model, and configuration files.

## References

- ArcFace: Additive Angular Margin Loss for Deep Face Recognition
- [BTK Akademi: Bilgisayarlı Görü Uygulama Alanları](https://www.btkakademi.gov.tr/portal/course/bilgisayarli-goru-uygulama-alanlari-12421)
- [MS1M Dataset](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/08/MSCeleb-1M-a.pdf)
- [LFW Dataset](https://www.kaggle.com/datasets/jessicali9530/lfw-dataset)