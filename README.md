# faster-rcnn-win-tf2
Tensorflow Faster R-CNN for Windows and Linux by using Python 3

This is the branch to compile Faster R-CNN on Windows and Linux. It is heavily inspired by the great work done [here](https://github.com/dBeker/Faster-RCNN-TensorFlow-Python3). I have not implemented anything new but I fixed the implementations for tensorflow2.

Currently, this repository supports Python 3.5, 3.6 and 3.7.

If you find a solution to an existing issue in the code, please send a PR for it.

# How to use this Branch
1.Install tensorflow, preferably GPU version. Follow [instructions]( https://www.tensorflow.org/install/install_windows). If you do not install GPU version, you can uncomment line 5,6 in the train.py and it will execute only in CPU.

2.Checkout this branch

3.Install python packages (cython, python-opencv,easydict) by running
`pip install -r requirements.txt`
(if you are using an environment manager system such as `conda` you should follow its instruction)

4.Go to ./data/coco/PythonAPI
Run `python setup.py build_ext --inplace`
Run `python setup.py build_ext install`
Go to ./lib/utils and run `python setup.py build_ext --inplace`

5.Follow [these instructions](https://github.com/rbgirshick/py-faster-rcnn#beyond-the-demo-installation-for-training-and-testing-models) to download PyCoco database. The final structure has to look like
`\data\VOCdevkit2007\VOC2007`

6.Download pre-trained VGG16 from [here](http://download.tensorflow.org/models/vgg_16_2016_08_28.tar.gz) and place it as `data\imagenet_weights\vgg16.ckpt`.  
For rest of the models, please check [here](https://github.com/tensorflow/models/tree/master/research/slim#pre-trained-models)

7.Run train.py

Notify me if there is any issue found.