## Semantic Image Segmentation using Fully Conventional Neural Network.

[//]: # "Image References"

[image1]: https://github.com/mniju/CarND-Semantic-Segmentation/blob/master/Output/Sample1.png "Sample1"
[image2]: https://github.com/mniju/CarND-Semantic-Segmentation/blob/master/Output/Sample2.png "Sample2"
[image3]: https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/05d20ad124a8696f387e6c9632dec0b31251df64/3-Figure3-1.png "Architecture"
[image4]: https://qph.ec.quoracdn.net/main-qimg-2f67065ea45f75188c09e110252408c3
[image5]: ./writeup/original.png "Sample Image"
[image6]: ./writeup/CroppingandResizing.png "cropping&Resizing Image"

### Purpose:
The aim of the project is to train a network to Classify each pixel in the Image to two classes -Road/Not Road.

### Process:
An Encoder-Decoder Model is used for this classification.

We use Transfer learning to get the weights of the existing VGG-16 Model.

Convert the Classic VGG-16 to a Fully convolutional Network,and Transfer the learning from the network for our task. we then combine the information from the deep layer to that of the shallow layer that has the appearence to get the proper segmentation by using the Skip layer architecture.
![image4]
The VGG-16 Model is considered the Encoder and a a decoder is developed by upconverting the layers of decoder and also using the Skip layer architecture to produce proper results.

The complete Model is shown below.This is similiar to the one used in this [paper](https://www.semanticscholar.org/paper/PCA-aided-Fully-Convolutional-Networks-for-Semanti-Tai-Ye/05d20ad124a8696f387e6c9632dec0b31251df64).

![image3]

### Training:

Training is done with [KITTI Road Dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php)

I trained the network in [Floydhub](https://www.floydhub.com/mniju/projects/carnd-semanticsegmentation/23/code).I ran it for 20 epochs with a Batch size of 10.It took me around 29 Minutes to Train and create Test run Images.
I reached a validation loss around 0.03.

![image1]

![image2]

### Reflection:
As seen this gives some reasonable output.This may not be the best yet though.
May be some additional epochs should be run and then IOU should be calculated to determine how well the network performs.

I took inspiration from two wonderful guys [Lukaz](https://github.com/ljanyst) and [Levin](https://github.com/LevinJ)

