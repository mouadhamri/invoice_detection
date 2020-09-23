# invoice_detection : Image Annotation

## Dataset
To train the YOLO invoice detector on your own dataset, copy your training images to [`invoice_detection/Data/Source_Images/Training_Images`](/Data/Source_Images/Training_Images/).  

## Annotation
To make our detector learn, we first need to feed it some good training examples. We use Microsoft's Visual Object Tagging Tool (VoTT) to manually label images in our training folder [`invoice_detection/Data/Source_Images/Training_Images`](/Data/Source_Images/Training_Images/). To achieve decent results annotate at least 100 images. For good results label at least 300 images and for great results label 1000+ images. 



## Convert to YOLO Format
As a final step, convert the VoTT csv format to the YOLOv3 format. To do so, run the conversion script from within the [`invoice_detection/1_Image_Annotation`](/1_Image_Annotation/) folder:

```
python Convert_to_YOLO_format.py
```
The script generates two output files: [`data_train.txt`](/Data/Source_Images/Training_Images/vott-csv-export/data_train.txt) located in the [`invoice_detection/Data/Source_Images/Training_Images/vott-csv-export`](/Data/Source_Images/Training_Images/vott-csv-export) folder and [`data_classes.txt`](/Data/Model_Weights/data_classes.txt) located in the [`invoice_detection/Data/Model_Weights`](/Data/Model_Weights/) folder. To list available command line options run `python Convert_to_YOLO_format.py -h`.

### That's all for annotation! 
Next, go to [`invoice_detection/2_Training`](/2_Training) to train your YOLOv3 detector.