# What are Neural Networks?

In many countries routine vital statistics are of poor quality, and often incomplete or unavailable. In countries where vital registration and routine health information systems are weak, the application of verbal autopsy (VA) in demographic surveillance systems or cross-sectional surveys has been suggested for assessing cause-specific burden of mortality. The technique involves taking an interviewer-led account of the symptoms and signs that were present preceding the death of individuals from their caretakers. Traditionally the information obtained from caretakers is analysed by physicians and a cause(s) of death is reached if a majority of physicians on a panel agreed on a cause(s). The accuracy of physician reviews has been tested in several settings using causes of death assigned from hospital records as the ‘gold standard’. Although physician reviews of VA gave robust estimates of cause-specific mortality fractions (CSMF) of several causes of death, the sensitivity, specificity and predictive values varied between causes of death and between populations1,2 and had poor repeatability of results.3

Arguments to introduce opinion-based and/or data-derived algorithm methods of assigning cause of death from VA data are based on both the quest for accuracy and consistency, as well as the logistical difficulties in getting together a panel of physicians to review what are often large numbers of records. However, physician review performed better than set diagnostic criteria (opinion-based or data-derived) given in an algorithm to assign a cause of adult death.4 One promising approach to diagnose disease status has been artificial neural networks (ANN) which apply non-linear statistics to pattern recognition. For example, ANN predicted outcomes in cancer patients better than a logistic regression model.5 Duh et al. speculate that ANN will prove useful in epidemiological problems that require pattern recognition and complex classification techniques.6 In this report, we compare the performance of ANN and logistic regression models and physician review for reaching causes of adult death from VA.



## An overview of neural networks
Although often referred to as black boxes, neural networks can in fact easily be understood by those versed in regression analysis techniques. In essence, they are complex non-linear modelling equations. The inputs, outputs and weights in a neural network are analogous to the input variables, outcome variables and coefficients in a regression analysis. The added complexity is largely the result of a layering of ‘nodes’ which provides a far more detailed map of the decision space. A single node neural network will produce a comparable output to logistic regression, where a function will combine the weights of the inputs to produce the output (Figure 1).

Combining these nodes into multiple layers adds to the complexity of the model and hence the discriminatory power. In so doing, a number of elements, each receiving all of the inputs and producing an output, have these outputs sent as inputs to a further element(s). The architecture is called a multi-layer perceptron (Figure 2).

The study population and field procedures of the VA data used in this analysis are described elsewhere.1 In brief, data were collected at three sites (a regional hospital in Ethiopia, and two rural hospitals in Tanzania and Ghana). Adults dying at these hospitals who lived within a 60-km radius of the institution were included in the study. A VA questionnaire was administered by interviewers with at least 12 years of formal education. The reference diagnoses (gold standard) were obtained from a combination of hospital records and death certificates by one of the authors (DC) together with a local physician in each site. A panel of three physicians reviewed the VA data and reached a cause of death if any two agreed on a cause (physician review).

The method used to derive algorithms from the data using logistic regression models has been described elsewhere.4 Each subject was randomly assigned to the train dataset (n = 410) or test dataset (n = 386), such that the number of deaths due to each cause (gold standard) was the same in both datasets. If a cause of death had odd numbers, the extra subject was included in the train dataset. Symptoms (includes signs) with odds ratio (OR) ≥2 or ≤0.5 in univariate analyses were included in a logistic model and then those symptoms that were not significant statistically (P > 0.1) were dropped from the model in a backward stepwise manner. Coefficients of each symptom remaining in the model were summed to obtain a score for each subject i.e. Score = b1×1+b2×2+…, where bixi are the log OR bi of symptoms xi in the model. A cut-off score was identified for each cause of death (included 16 primary causes of adult death) that gave the estimated number of deaths closest to the true number of cause-specific deaths, such that the sensitivity was at least 50%.

We used the same train and test datasets used by Quigley et al. for training and testing an ANN. The data were ported to Microsoft Excel™ and analysed using NeuroSolutions 3.0™ (Lefebvre WC. NeuroSolution Version 3.020, Neurodimension Inc.1994. [www.nd.com]). All models were multi-layer perceptrons with a single hidden layer and trained with static backpropogation. The number of nodes in the hidden layer were varied according to the number of inputs and network performance. A learning rate of 0.7 was used throughout with the momentum learning rule. A sigmoid activation function was used for all processing elements.

Model inputs were based on those used in the logistic regression study, with further variables added to improve discrimination in instances when they improved the model performance. Sensitivity analysis provided the basis for evaluating the role of the inputs in the models.

For each diagnosis, the first 100 records of the training subset were used in the first training run of each model as a cross-validation set to determine the optimal number of hidden nodes and the training point at which the cross-validation mean squared error reached a trough. Thereafter the full training set was used to train the network to this point.

The output weights were then adjusted by a variable factor until the CSMF was as close as possible to 100% of the expected value in testing runs on the training set. At this point the network was tested on the unseen data in the test subset.

Weighted (by number of deaths) averages for sensitivity and specificity were calculated for each method. A summary measure for CSMF was calculated for each method by summing the absolute difference in observed and estimated number of cases for each cause of death, dividing by the total number of deaths, and converting to a percentage.

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
