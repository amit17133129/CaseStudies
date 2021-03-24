# What are Neural Networks?
![image](https://user-images.githubusercontent.com/55508548/112291963-9f54bf80-8cb6-11eb-809a-14fa0d714f35.png)

## Machines have brains. This, we already know. But increasingly, their brains are able to solve the sorts of problems that, until recently, humans were uniquely good at. Neural networks, as the name suggests, are modeled on neurons in the brain. They use artificial intelligence to untangle and break down extremely complex relationships.
<p align="center">
<img width="800" height="400" src="https://www.verypossible.com/hs-fs/hubfs/neural-networks-layers.jpg?width=1800&name=neural-networks-layers.jpg">
</p>


<p align="center">
<img width="600" height="400" src="https://media-exp1.licdn.com/dms/image/C5612AQH9DeCtMMeQWA/article-inline_image-shrink_1000_1488/0/1589089462283?e=1622073600&v=beta&t=9E98FjZoWZSA5g2WId86dokd0AD3mgFfyLO409ciZaA">
</p>

## Convolutional Neural Network (CNN) is an algorithm from which we can train our machine(models) to predict output.
Our eyes is so smart that they look the complete photograph and start finding main features from that photograph. Our eyes keep on rotating on the photograph continuously and it finds some similarities(patterns) in the photograph and groping of that similarities will form new photograph. This is clearly shown in the below gif.

Eye keeps on seeing the image while rotating. When it find some important feature in one of the box then it stores that feature and move ahead and this process runs completely and at last our mind merges all the features together and generates one images in mind. Same thing happens with the models also. The rotation of box on the image is known as **filter**, **kernel** or **Feature detector**. The information/objects detects in kernels/filters are selected as a feature. This task of feature selection is done by neural network. Here one thing to note that feature extraction and feature selection is two different thing.
**Feature Extraction**  : Combining multiple features without loosing the information is known as feature extraction.
**Feature Selection** : From those feature which is extracted by kernels which feature will be important to predict the output known as feature selection. This is done automatically by neural network
**Feature extraction**is done in Convolution layer. But what is convolution ? Convolution is just a multiplication of image pixels with kernel values and in result it will extract the important features.
From above example, in the third figure some important features is extracted. Behind the scene, edge detection plays vital role in detecting the features. In the above third figure only edges are extracted. Below is an example of edge detection.
<p align="center">
<img width="600" height="400" src="https://media-exp1.licdn.com/dms/image/C5612AQG0HyhNVrRgGw/article-inline_image-shrink_1000_1488/0/1589092408863?e=1622073600&v=beta&t=VFjWTZhw5KUPwQ6IcNAKVOjwpBuxQlV6hCIyVCPeaLQ">
</p>
Below is a visualization, where you will understand the complete picture.
<p align="center">
<img width="600" height="400" src="https://media-exp1.licdn.com/dms/image/C5612AQEv_ElRXDIOIA/article-inline_image-shrink_1000_1488/0/1589092613986?e=1622073600&v=beta&t=n1Z51yzr7SmGUtvr7VA3SgTJoFDNZjW6ziPBHWyf74o">
</p>
In the above gif the new image is extracted after rotation of kernel/filter = 3*3 on image of pixel size = 5 * 5.

But you will say where is convolution applied.see in the below gif.
<p align="center">
<img width="600" height="400" src="https://media-exp1.licdn.com/dms/image/C5612AQHvirc-1NBoHw/article-inline_image-shrink_1000_1488/0/1589092767308?e=1622073600&v=beta&t=v_7vTJeRe7Oo6kcPvCu2_YQfCs54IbAwvH5pYsRMb08">
</p>


The calculation between the image pixel and kernel values is known as convolve. New image extracted by convolution is always small because after some important feature extraction the pixels are reduced in the new image therefore the new image is always small compare to original image. But this image include more pixels of same information (color, objects) as there are more pixels in the convolved image then for training this image there's requirement of high processing power as well as cost. To reduce this requirement we can reduce the pixel of the same information and merge them into one pixel. This can be achieved by Pooling. There are three types of pooling 
1) Max Pooling 
2) Average Pooling 
3) Sum Pooling 
We use Max pooling in many of the cases but it depends on requirements. Below is an example of *Max pooling*.

<p align="center">
<img width="600" height="400" src="https://media-exp1.licdn.com/dms/image/C5612AQEzoU6Hzg8sAw/article-inline_image-shrink_1000_1488/0/1589093536923?e=1622073600&v=beta&t=CxSyz1pEgpM0NG_KHAWVElod_NS2bKuPCOw1fgwsYas">
</p>


As you can in the above figure the big image of pixel( 4 * 4) in which *kernel* of size *2 * 2* is rotating in the big big image and extracting the values and forming one new image. This **kernel** of *2 * 2* will only extract maximum value from the big pixel with their respective box. That is why it is know as **Max pooling** [ [ 0 50], [ 0 80] ] Here 0 means black pixel and 50, 80 are some colors. if you prediction doesn't have black color then it will be removed from here by *max pooling* and only the maximum value is extracted from this matrix with their respective colors.

Now we have two layers i.e Convolution and **Max pooling**. Sequence of this layers will give a good image in the output.

<p align="center">
<img width="600" height="400" src="https://media-exp1.licdn.com/dms/image/C5612AQHg3OJiKCBfKg/article-inline_image-shrink_1000_1488/0/1589094375857?e=1622073600&v=beta&t=zd1UYwb0Zwvs_wQQo-ywGzz6X4ePeW5aeZMGehVn9Qg">
</p>

As you can see in the above fig, the sequence of Convolution and **pooling** is followed. There is a layer of activation function `'relu'`. This relu activation will give only positive value to next convolutional layer i.e if first convolutional layer transfers negative value to next convolutional layer then relu will send only positive value and will convert the negative value to zero. Because there cannot be negative prediction. This layers are in 2D and machine learning model not understand higher dimensional inputs there we have to flatten these layers value and convert this into 1D and then this flatten values will acts as a input to neural network i.e is to send flatten values to Fully connected layer.

Hope you'll find this article interesting.

Thank You !
