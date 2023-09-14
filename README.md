# ImageCaptioning
Textual Description Generation for Visual Content using Neural Networks

# Description:
The task here performed is generating a caption for an input image. The model uses a convolution neural network to read images and create a feature vector. It uses a recurrent neural network for learning sentences/captions for images. This is basically an Encoder-Decoder model.


## Requirements

- Keras =>  2.3.1
 - pillow => 7.1.2
 - h5py => 2.10.0
 - nltk => 3.5
 - numpy => 1.18.4
 - pandas => 1.0.3
 - sciPy => 1.4.1
 - TensorFlow => 2.2.0
 - urllib3 => 1.25.9


## Dataset

We used the **Flickr8k** dataset in this proposed model, which contains around 8000 images. We divided this into three parts
1. 6000 images - training purpose
2. 1000 images - development and verification
3. 1000 images - testing purpose

This dataset contains two folders - images and text (related captions)
In our project folder, we have two folders named Flicker8k_Data and Flickr8k_Text. Images from the dataset are to be copied into the **Flickr8k_Data** folder, and text from the dataset is to be copied into the **Flickr8k_Text** folder.

## Used Model

 - We used a pretrained VGG16 CNN model for feature extraction and image encoding.
 -  For caption generation (Sequence generator), we used LSTM (RNN).

## Execution Steps

Commands:
 ```
 python preprocess_data.py
 ```
 - It creates some preprocessed text files in the Flickr8k_Text folder
 ```
 python encode_image.py
 ```
 - it creates image_encoding.p file
 - uses VGG16 model
 ```
 python train.py var
 ```
 - where var is an integer value passed denoting the number of epochs required
- model will be saved in the Output Folder
```
python test.py image
```
- where image is any image kept in the test folder
- This image is used to test our model

## Output

The output of this model is a caption for an input image.

## Result


![dog](beach.jpg)

**generated caption**
```
brown dog running in the water
```

![water](water.jpg)

**generated caption**
```
The person is riding a surfboard in the ocean.
```

## References

-  Andrej Karpathy,  Li Fei-Fei -  "Deep Visual-Semantic Alignments for Generating Image Descriptions". Department of Computer Science, Stanford University. 2015.
- Vinyals, Oriol, et al. "Show and tell: A neural image caption generator." Proceedings of the IEEE conference on computer vision and pattern recognition. 2015.

**Pretrained VGG16 Model**
[https://github.com/fchollet/deep-learning-models](https://github.com/fchollet/deep-learning-models)
