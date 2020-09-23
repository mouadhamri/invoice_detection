# Invoice AI detection: Building a Custom Object Detector for invoices

This repo is a fork of the repo https://github.com/AntonMu/TrainYourOwnYOLO.git which makes use of ilmonteux/logohunter which itself is inspired by qqwweee/keras-yolo3 (a Darknet implementation  of YOLO3).
We use TensorFlow 2.3 and Keras 2.4.

### Pipeline Overview

To build and test a YOLO invoice object detection algorithm follow the below steps:

 1. [Image Annotation](/1_Image_Annotation/)
	 - Install Microsoft's Visual Object Tagging Tool (VoTT)
	 - Annotate the invoices.
 2. [Training](/2_Training/)
 	- Train your custom YOLO model on annotated invoices. 
 3. [Inference](/3_Inference/)
 	- Detect objects in new invoice images.

## Repo structure
+ [`1_Image_Annotation`](/1_Image_Annotation/): Scripts and instructions on annotating invoices.
+ [`2_Training`](/2_Training/): Scripts and instructions on training your YOLOv3 model
+ [`3_Inference`](/3_Inference/): Scripts and instructions on testing your trained YOLO model on new invoice images.
+ [`Data`](/Data/): Input Data, Output Data, Model Weights and Results
+ [`Utils`](/Utils/): Utility scripts used by main scripts

## Getting Started

### Requisites
The only hard requirement is a running version of python 3.6 or 3.7. To install python 3.7 go to 
- [python.org/downloads](https://www.python.org/downloads/release/python-376/) 

and follow the installation instructions. Note that this repo has only been tested with python 3.6 and python 3.7 thus it is recommened to use either `python3.6` or `python3.7`.



### Installation

#### Setting up Virtual Environment [Linux or Mac]

Clone this repo with:
```
git clone https://github.com/mouadhamri/invoice_detection.git
cd invoice_detection/
```
Create Virtual **(Linux/Mac)** Environment:
```
python3 -m venv env
source env/bin/activate
```
Make sure that, from now on, you **run all commands from within your virtual environment**.

Install required packages (from within your virtual environment) via:

```
pip install -r requirements.txt
```
If this fails, you may have to upgrade your pip version first with `pip install pip --upgrade`.

## Full Start (Training and Inference)

To train your own custom YOLO invoice object detector please follow the instructions detailed in the three numbered subfolders of this repo:
- [`1_Image_Annotation`](/1_Image_Annotation/),
- [`2_Training`](/2_Training/) and
- [`3_Inference`](/3_Inference/).
 
**To make everything run smoothly it is highly recommended to keep the original folder structure of this repo!**

Each `*.py` script has various command line options that help tweak performance and change things such as input and output directories. All scripts are initialized with good default values that help accomplish all tasks as long as the original folder structure is preserved. To learn more about available command line options of a python script `<script_name.py>` run:

```
python <script_name.py> -h
```

