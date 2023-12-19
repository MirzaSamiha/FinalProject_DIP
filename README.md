# FinalProject_DIP
Leaf Image Segmentation with Edge Detection and Greenness Assessment

dip_project
Leaf Image Segmentation with Edge Detection and Greenness Assessment
Segmentation subdivides an image into its constituent regions or objects. Segmentation ends when the objects of interest are isolated. Segmentation algorithms are generally based on one of the two basic properties of image intensity values, and they are discontinuity and similarity. In the first scenario, we partition the image based on abrupt changes of image intensity such as edges in an image. In the second scenario, the partitioning of the image into regions is based on a set of predefined criteria.

image
Edge detection forms the basis for segmentation algorithms. Edge detection includes different mathematical methods in identifying edges and curves in a digital image at which the image brightness changes sharply. The result of applying an edge detector to an image may lead to a set of connected curves that indicate the boundaries of objects, the boundaries of surface markings as well as curves that correspond to discontinuities in surface orientation. Thus, applying an edge detection algorithm to an image may significantly reduce the amount of data to be processed and may therefore filter out information that may be regarded as less relevant, while preserving the important structural properties of an image.


Dataset
For two datasets you can download or look for more info from the respective sites:

https://www.imageclef.org/lifeclef/2016/plant#:~:text=The%20public%20packages%20containing%20all%20the%20data%20of,can%20download%20it%20using%20the%20following%20urls%3A%20https%3A%2F%2Flab.plantnet.org%2FLifeCLEF%2FPlantCLEF2016%2FRunFilesToolAndResults.zip

https://flavia.sourceforge.net/

Data
For the project, I am utilizing two publicly available datasets, referred to as

Flavia Dataset: This dataset contains images of leaves from 32 different plant species, offering a good representation of diverse leaf shapes and colors.

PlantCLEF Dataset: The PlantCLEF (Conference and Labs of the Evaluation Forum) dataset is part of the ImageCLEF challenge and includes plant images, including leaves, from various environments, which can be more diverse.

Binarization and Color Separation:
Binarization is the process of transforming a picture into a binary representation, in which each pixel is identified as either the background (often black) or the foreground (usually white). Reducing the image's complexity and emphasizing particular aspects is frequently the aim. Binarization can be used in leaf analysis to assist distinguish the leaves—which are often green—from the backdrop.

The process of removing particular color channels from a picture is called color separation. The code that is supplied extracts the green channel and then uses the greenness difference to conduct binarization. This draws attention to the image's green areas.

To summarize, the process of binarization involves breaking down an image into its foreground and background.

Greenness Assessment:
Quantifying each pixel's "greenness" in a picture is the process of assessing its greenness. By comparing the green channel's intensity to the average intensity of the blue and red channels, the given code determines the greenness difference for each pixel. This yields a measurement of the color deviation of a pixel from a neutral gray. Although segmenting and analyzing plant leaves is the ultimate aim of both binarization and greenness evaluation, they serve distinct purposes throughout the analysis.

The greenness evaluation gives a numerical value indicating how much green is present in each pixel.

Edge detection
It forms the basis for segmentation algorithms. 
Edge detection includes different mathematical methods in identifying edges and curves in a digital image at which the image brightness changes sharply.'
I've used Pretwitt, log, canny and Sobel.

Image segmentation
This divides an image into meaningful segments with shared properties, vital for computer vision. I've used Watershed Segmentation and Marker based for optimized results.

There are 2 folders for displaying the dataset used in the experiments by name Daisy and LeavesO, the bflavia was one of the output images for looking at the binarized versions.

The greenpart and greenpart_leavesdataset are the output folders for the code applied on 2 seperate dataset.
Next edm1 and edm2dataset are the outputs of the edge detection techniques each folder containing 4 different outputs for the techniques.

The outputsegm and outputsegmleaves are the outputs for segmentation results applied.

The 3 ipynb files are the code where the Trial1 and Trial2 were just for testing the finalcode file of ipynb is the final code for the project.

While running the codes please change the filepaths as were the datasets are stored.



Citations
Janwale, Asaram. (2017). Plant Leaves Image Segmentation Techniques: A Review. INTERNATIONAL JOURNAL OF COMPUTER SCIENCES AND ENGINEERING. 5. 147-150.

Rajab, Maher. (2016). Performance Evaluation of Image Edge Detection Techniques. International Journal of Computer Science and Security (IJCSS). 10. 170-185.

H.-J. He, C. Zheng, D.-W. Sun (2016). Chapter 2 - Image Segmentation Techniques, Editor(s): Da-Wen Sun, Computer Vision Technology for Food Quality Evaluation (Second Edition) Academic Press, 2016, Pages 45-63, ISBN 9780128022320.

Description of the files in project folder:
The blavia and plantcelf folders stored the images after applying the code, logic for assesment where we need to look at the difference between the color we want and the average of the other two. Then threshold on that. We consider an RGB image. The color [0 255 0] is a green. It is calculated as follows,

greenDifference = greenChannel - (redChannel + blueChannel)/2;

The above formula was used in the initial codes which is pretty straightforward by defining the functions acoordingly.

The latter part of the code in .py file given, shows the implementation for edge detection techniques and their respected results saved in the pathtosave folder with respective names of the techniques.
