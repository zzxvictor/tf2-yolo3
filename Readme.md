# tf2-yolo3

## Quick Start

This code depends on tensorflow-2.x, please install it first.

The easiest way is to use conda, 

**conda install tensorflow-gpu==2.0.0**

This code also requires opencv-python, install it by pip or conda as the following

**pip install opencv-python**

**pip install absl-py**

**pip install numpy**

## Training

To train on m2nist dataset, just run 

**python train.py**

To train on your own dataset, just run 

**python train.py --batch_size 32  --dataset train.txt --val_dataset val.txt --epochs 100  --size 320,320 --learning_rate 1e-3**  

--size is the input of size in the format (height, width)

--dataset is your own dataset in yolo format, a text file of lines in the following format,

Row format: `image_file_path box1 box2 ... boxN`;
Box format: `x_min,y_min,x_max,y_max,class_id` (no space).

Here is an example

```
path/to/img1.jpg 50,100,150,200,0 30,50,200,120,3
path/to/img2.jpg 120,300,250,600,2
...
```

## Use your model

To detect on single image,just run

**python detect.py   --image path_to_your_image.png  --output path_to_your_output.png  --size 320,320**  

Here is two example on m2nist dataset

![output0](https://github.com/akkaze/tf2-yolo3/blob/master/assets/output0.jpg)![output1](https://github.com/akkaze/tf2-yolo3/blob/master/assets/output1.jpg)

If you have any question, please contact me directly,my email is zhengankun@163.com
