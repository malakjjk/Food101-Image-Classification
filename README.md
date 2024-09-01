# Food101-Image-Classification
Implementation of image classification on the Food101 dataset using ResNet and EfficientNet. The models are trained to recognize and classify images into 101 different categories of food. The project demonstrates data preprocessing, model fine-tuning, mixed precision training, and performance evaluation

Our Mission:

•	Data Domination: We'll conquer the entire Food101 dataset, encompassing a staggering 75,750 training images and 25,250 test images.

•	Accuracy Ascension: Our objective is to propel past the DeepFood paper's top-1 accuracy, reaching new heights in image recognition.

•	Speed Supremacy: We'll unlock the power of mixed precision training and data prefetching to streamline the training process, making it faster and more efficient.

Data: The Fuel for Success
1. Download and Explore:

•	Understanding the Enemy: After the download, we'll meticulously analyze the dataset. We'll uncover the shapes, data types, and labels associated with the images, gaining a deep understanding of their structure.

•	Visualization is Key: To solidify our understanding and ensure labels match the images, we'll leverage matplotlib.pyplot.imshow() to visually inspect sample images.

2. Preprocessing: Transforming the Raw Material
Raw data is like unrefined ore – it needs refinement! We'll create a preprocess_img() function to transform the images into a format suitable for our model:
•	Resizing for Uniformity: We'll ensure consistency by resizing all images to a uniform size, such as (224, 224). This is crucial for batch processing, as tensors within a batch must have the same shape.

•	Normalization: From 0 to 1: We'll convert the images from uint8 to float32 and then normalize the pixel values to a range of 0 to 1. This is a common practice that facilitates model training.

3. Data Pipeline with tf.data API: Building the Training Autobahn
The tf.data API is our tool for constructing an efficient data pipeline. Here's the traffic flow:
•	Map: This acts as the "preprocessing station" where our preprocess_img() function is applied to each image.

•	Shuffle: To prevent overfitting, we'll randomly shuffle the data using shuffle(). Here, choosing an appropriate buffer size is critical.

•	Batch: We'll group the preprocessed images into manageable batches using batch(). This allows the model to process multiple images simultaneously, boosting training efficiency.

•	Prefetch: To further optimize performance, we'll employ prefetch(). This overlaps data preprocessing with model training, ensuring the model doesn't have to wait for new data after each batch.

•	Cache (Optional): If your dataset fits comfortably in memory, consider using cache() to speed up subsequent training epochs. However, on standard Colab instances, memory limitations might make caching impractical.

4. Mixed Precision Training: Unlocking Speed
Mixed precision training is our secret weapon for accelerating the training process. We'll achieve this by:

•	Importing the Arsenal: We'll import tensorflow.keras.mixed_precision to equip ourselves with the necessary tools.

•	Setting the Global Policy: Finally, we'll leverage set_global_policy('mixed_float16') to activate mixed precision training.

6. Evaluation:
   
•	Conduct different evaluation metrices (Precision – Recall – F1-Score).

•	Conduct confusion matrix.
