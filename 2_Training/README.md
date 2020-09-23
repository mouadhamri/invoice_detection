# invoice_detection: Training

## Training
Using the training images located in [`invoice_detection/Data/Source_Images/Training_Images`](/Data/Source_Images/Training_Images) and the annotation file [`data_train.txt`](/Data/Source_Images/Training_Images/vott-csv-export) which we have created in the [previous step](/1_Image_Annotation/) we are now ready to train our YOLOv3 invoice detector. 

## Download and Convert Pre-Trained Weights
Before getting started download the pre-trained YOLOv3 weights and convert them to the keras format. To run both steps run the download and conversion script from within the [`invoice_detection/2_Training`](/2_Training/) directory:

```
python Download_and_Convert_YOLO_weights.py
```

The weights are pre-trained on the [ImageNet 1000 dataset](http://image-net.org/challenges/LSVRC/2015/index) and thus work well for object detection tasks that are very similar to the types of images and objects in the ImageNet 1000 dataset.

## Train YOLOv3 Detector
To start the training, run the training script from within the [`invoice_detection/2_Training`](/2_Training/) directory:
```
python Train_YOLO.py 
```
Depending on your set-up, this process can take a few minutes to a few hours. The final weights are saved in [`invoice_detection/Data/Model_weights`](/Data/Model_weights). To list available command line options run `python Train_YOLO.py -h`.


### That's all for training! 
Next, go to [`invoice_detection/3_Inference`](/3_Inference) to test your YOLO detector on new images!
