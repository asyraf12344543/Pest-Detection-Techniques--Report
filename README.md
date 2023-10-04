# Pest Detection Techniques: Report  
 
# Abstract
Malaysia is blessed with a land that is suitable for planting plants such as palm trees, paddies, rubber trees and others. In fact, Malaysia is the second largest palm oil producer and exporter in the world. Therefore, researchers have conducted various solutions with the help of deep learning techniques that follow the advancement of technology nowadays such as image processing solely to detect pests damaging our plant before it gets out of hand. For example, we can use image acquisition to capture an image then run on through phases of segmentation, classification and others. In this literature review,we aim to differentiate all the methods by  discussing the research background of our scope first and  then analyzing the methods with listing out their advantages and disadvantages.

Keywords- Pest detection, image processing, acquisition,segmentation, classification.

# Introduction
The art and science of cultivating the land, growing crops, and raising livestock is known as agriculture. It entails preparing plant and animal goods for human consumption as well as their delivery to markets. Agriculture was the beginning of civilization, and agriculture is still highly essential today, despite the fact that mankind has evolved greatly. Its importance is more visible in certain nations, but the fact is that agriculture is important to every country in the globe for one reason or another. Agriculture is crucial since it is the country's primary source of raw resources, a component of international trade, and a contributor to its growth.

However, one of the most deadly organisms capable of destroying the entire agricultural process will inevitably find its way into the field. Pest species are a major source of worry, not only because of the potential loss of money due to crop damage, but also because, if left untreated, they can severely destroy machinery, equipment, and property. Insects, birds, and rodents are examples of pest species.

Image processing technologies can help in this situation. The goal of this literature review is to look at the methods utilized by researchers and computer scientists to design an algorithm for detecting insect presence in the agriculture sector. The purpose of object detection in computer vision is to determine not only whether items from generic categories are present in a picture, but also to return the spatial location and extent of each object using a bounding box [1].

# Methodology
A.	Technique: Cropping
Cropping is the process of removing unnecessary exterior parts from an image. Many of the images above included black pixels, which you can simply remove by cropping. Images in OpenCV are essentially Numpy arrays. As a result, we can use Numpy array slicing to crop an image and delete the parts we don't want. The first dimension of a Numpy array represents the array's rows (which are the image's height or y-coordinates), while the second dimension represents the array's columns (which is the width of the image or the x-coordinates). First, we'll read the "pest.jpg" input image and convert it from BGR to RGB so that we can plot it using matplotlib. Then we deactivate the x and y axes, resulting in 1700 pixels on the x-axis and 2390 pixels on the y-axis, which we save as "pest cropped.jpg" in the same directory as the input file.

B.	Technique: Foreground Subtraction
In our application, we applied the GrabCut Foreground Detection algorithm to remove the background of the input image and detect the subject of that image. Carsten Rother, Vladimir Kolmogorov, and Andrew Blake of Microsoft Research Cambridge, UK, developed the GrabCut method in their article "GrabCut": interactive foreground extraction with iterated graph cuts. GrabCut was created as a consequence of the necessity for a foreground algorithm that required minimum user intervention. The GrabCut algorithm works by accepting an input image with either a bounding box that specified the location of the object in the image we wanted to segment or a mask that approximated the segmentation Iteratively performing the following steps:
●	Estimating the color distribution of the foreground and background via a Gaussian Mixture Model (GMM)
●	Constructing a Markov random field over the pixels labels (i.e., foreground vs. background)
●	Applying a graph cut optimization to arrive at the final segmentation
OpenCV has an implementation of GrabCut via the cv2.grabCut function that makes applying GrabCut a breeze (once you know the parameters to the function and how to tweak them, of course). 
