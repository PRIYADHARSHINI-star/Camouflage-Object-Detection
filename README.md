## Camouflage Object Detection
#### PROBLEM DEFINITION
Camouflage objects hide information physically based on the feature matching of texture or boundary line with the Background. Texture matching and similarities between the camouflage objects and surroundings maps make differentiation difficult with generic salient objects, thus making camouflage object detection more challenging. Challenging nature of camouflage objects demands more accuracy in detection and segmentation. We elaborately, collect a novel dataset called COD10K and CAMO Dataset which comprises of 10000 images covering camouflage objects in various natural scenes, over 78 object categories. Camouflage image processing can be used in military operations to help conceal military vehicles, equipment and personnel from detection by the enemy.

#### DATASET COLLECTION
* Camouflage object detection 10k images (5,066 camouflaged, 3000 background, 1934 non camouflaged)
* CAMO (Camouflaged Object) dataset, consist of 1250 images (1000 images for training set and 250 images for test set)
#### DATASET DESCRIPTION
Camouflage images contain one or more hidden figures that remain imperceptible or unnoticed for a while.
#### SAMPLE INPUT
![image](https://github.com/PRIYADHARSHINI-star/Camouflage-Object-Detection/assets/72924709/b5e4bf72-fe2a-40e5-acc9-5ac2a8cb90c7)
1. **Images**: The dataset would contain images that have objects that are difficult to see due to camouflage. These images could be captured from different environments, such as forests, deserts, or urban areas.
2. **Object annotations**: The dataset would include annotations for the objects in the images. These annotations would specify the location, size, and shape of each object in the image or video.
3. **Camouflage labels**: The dataset would also include labels that indicate whether an object is camouflaged or not. This information would be used to train a model to detect objects that are difficult to see due to camouflage.
4. **Data splits**: The dataset would typically be divided into training, validation, and testing sets. This would allow researchers to train and evaluate their models on different subsets of the data.

#### Image Processing Techniques Used
* **Normalization**: Normalization is a process of scaling the pixel values of an image to a fixed range. This can be done using the Scikit-image library in Python. The skimage. exposure.rescale_intensity() function can be used to normalize an image.
* **Thresholding**: Thresholding is a technique used to convert an image into a binary image. This can be done using the OpenCV library in Python. The cv2.threshold() function can be used to apply thresholding to an image.
* **Resizing**: It refers to changing the size of an image. This can be done using the OpenCV library in Python. The cv2.resize() function can be used to resize an image to a specific size.
* **Blurring**: Blurring is a technique used to reduce noise in an image. This can be done using the OpenCV library in Python. The cv2.GaussianBlur() function can be used to apply a Gaussian blur to an image.
#### Image Enhancement Techniques Used
* **Gamma Correction**: Gamma correction is a technique used to adjust the brightness of an image. This can be done using the OpenCV library in Python. The cv2.LUT() function can be used to apply gamma correction to an image.
* **Sharpening**: Sharpening is a technique used to enhance the edges in an image. This can be done using the Scikit-image library in Python. The skimage.filters.unsharp_mask() function can be used to apply sharpening to an image.
* **Contrast Stretching**: Contrast stretching is a technique used to adjust the contrast of an image. This can be done using the Scikit-image library in Python. The skimage.exposure.rescale_intensity() function can be used to apply contrast stretching to an image.
* **Deblurring**: Deblurring is a technique used to remove the blur in an image. This can be done using the Scikit-image library in Python. The skimage. restoration. unsupervised wiener () function can be used to apply deblurring to an image.
* **Denoising**: Denoising is a technique used to remove the noise in an image. This can be done using the Scikit-image library in Python. The skimage. restoration. denoise_tv_chambolle () function can be used to apply denoising to an image.
#### Functionality used
#### AUGMENTATION USING ROBOFLOW:
Rob flow is a tool that eases the computer vision task in the field of deep learning. It empowers developers to build their computer vision applications, no matter their skill set or experience. It supports object detection and classification models. We used RoboFlow for the following operations:
* Dataset annotation
* Merge Project/Datasets
* Dataset export
* Dataset training

#### MASK R-CNN MODEL
*	Mask RCNN, the first end-to-end model for instance segmentation, is an extension of Faster RCNN a branch was added for predicting an object mask in parallel with the existing branch for bounding box detection.
*	Mask Scoring RCNN (MS RCNN), Cascade Mask RCNN, and PANet are extensions of Mask RCNN that improve the quality of segmented instances.
*	Mask R-CNN has three outputs, for each candidate object, a class label and a bounding-box offset; third output is the object mask.
#### How MASK R-CNN WORKS
Mask R-CNN model is divided into two parts
*	Region proposal network (RPN) to proposes candidate object bounding boxes.
*	Binary mask classifier to generate mask for every class.
![image](https://github.com/PRIYADHARSHINI-star/Camouflage-Object-Detection/assets/72924709/4bcff629-5a68-4309-bd6d-5f7807854210)
* Image is run through the CNN to generate the feature maps.
* Region Proposal Network (RPN) uses a CNN to generate the multiple Region of Interest (RoI) using a lightweight binary classifier. It does this using 9 anchors boxes over the image. The classifier returns object/no-object scores.
* The RoI Align network outputs multiple bounding boxes rather than a single definite one and warp them into a fixed dimension.
* Warped features are then fed into fully connected layers to make classification using softmax and boundary box prediction is further refined using the regression model
*	Warped features are also fed into Mask classifier, which consists of two CNNs to output a binary mask for each RoI. Mask Classifier allows the network to generate masks for every class without competition among classes.
![image](https://github.com/PRIYADHARSHINI-star/Camouflage-Object-Detection/assets/72924709/baf86e81-0302-4004-8f15-74562fac1602)

#### TRAINED DATASET
![image](https://github.com/PRIYADHARSHINI-star/Camouflage-Object-Detection/assets/72924709/641e6f5c-d52b-494d-8952-9834a60563bf)
![image](https://github.com/PRIYADHARSHINI-star/Camouflage-Object-Detection/assets/72924709/4c16adb1-af4c-414c-9428-87f461e9c280)
![image](https://github.com/PRIYADHARSHINI-star/Camouflage-Object-Detection/assets/72924709/19a78892-014e-425e-9e76-e19c565421eb)

#### OUTPUT FOR TEST DATASET
![image](https://github.com/PRIYADHARSHINI-star/Camouflage-Object-Detection/assets/72924709/5ddc05cc-bccc-4c96-8565-f89c0645f98b)


