# hog-descriptor-for-vehicle-detection
![Portion-Watermarking](https://socialify.git.ci/suva007/hog-descriptor-for-vehicle-detection/image?description=1&descriptionEditable=Detecting%20vehicles%20on%20road%20using%20hog%20and%20SVM%20%5Bsimplest%20approach%5D.&font=Bitter&pattern=Circuit%20Board&theme=Dark)

- <a href="https://github.com/suva007/hog-descriptor-for-vehicle-detection/blob/main/carhog.ipynb" title="Link to notebook" style="background-color:#FFFFFF;color:#000000;text-decoration:none">📚 Link to notebook </a>

## Intro
> In this section, we will take a look at one such feature extraction technique, the <a href="https://en.wikipedia.org/wiki/Histogram_of_oriented_gradients" title="Link to notebook" style="background-color:#FFFFFF;color:#000000;text-decoration:none">The Histogram of oriented Gradients </a>, which transforms image pixels into a vector representation that is sensitive to broadly informative image features regardless of confounding factors like illumination. We will use these features to develop a simple vehicle detection pipeline, using machine learning algorithms .

## Reading all Vehicale images and converting them to Grayscale
> GTI_Far : contains all the zoomed version of vehicles that are far.

> GTI_Left : contains all the left and zoomed version of vehicles that are far.

> GTI_Right : contains all the right and zoomed version of vehicles that are far.

> GTI_MiddleClose : contains all the middle and zoomed version of vehicles that are far.

> KITTI_extracted : contains images extracted from publically available kitty dataset , these images contains distinguished orientations.

![image](https://user-images.githubusercontent.com/38084433/148696864-a1b618cb-fa01-4f1b-97b5-a29bc3746a05.png)

## Visualization of HOG features
![image](https://user-images.githubusercontent.com/38084433/148696872-e00b0ab3-d644-46ee-b616-8f54b01c95d0.png)

## HOG in Action: A Simple Vehicle Detector
> Using these HOG features, we can build up a simple Vehicle detection algorithm with any Scikit-Learn estimator; here we will use a linear support vector machine. The steps are as follows:

- Obtain a set of image thumbnails of Vehicles to constitute "positive" training samples.
- Obtain a set of image thumbnails of non-Vehicles to constitute "negative" training samples.
![image](https://user-images.githubusercontent.com/38084433/148696915-00efa25c-a651-439c-a1eb-93141ff8b28e.png)

- Extract HOG features from these training samples.
- Train a linear SVM classifier on these samples.
- For an "unknown" image, pass a sliding window across the image, using the model to evaluate whether that window contains a Vehicle or not.
![image](https://user-images.githubusercontent.com/38084433/148696934-25d30098-b331-4c17-aa4b-40401c35e4b3.png)

- If detections overlap, combine them into a single window.
![image](https://user-images.githubusercontent.com/38084433/148696935-6735d31e-fa82-4bca-9b4e-662314a76fb0.png)

All of the detected patches overlap and found the Vehicle in the image!
## :wink: Thanks
