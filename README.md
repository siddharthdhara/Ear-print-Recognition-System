# Abstract:
**In recent years, there has been significant interest in accurately identifying individuals by their ears. This research plays a crucial role in biometrics, particularly as a supplement to face recognition systems, which often face challenges in real-world conditions due to variations in shapes, lighting, and profile changes. Our approach introduces an ear recognition system utilizing convolutional neural networks (CNNs) to identify individuals based on input images.**


# Identify your problem
In this project, a dataset comprising left ear images from individuals of various identities was provided. Each person contributed four images: two "in the wild" (captured without specific constraints) and two taken with a background-controlling "donut device" to manage lighting. The dataset contains a total of 4*195 (individual ear) images. (Data source: http://cs-people.bu.edu/wdqin/earImageDataset.zip)

Ear biometrics refers to automatic human identification based on ear anatomical features, calculated from 2D or 3D ear images using pattern recognition and image processing techniques.

Automated ear identification holds significant implications, finding applications in areas such as criminal investigations, child identification, and medical research.

**This project tackles a challenging classification problem with 195 categories, each containing 4 sample ear images. The objective is to identify the person to whom a given ear belongs and display all other ears belonging to that individual.**

Addressing this complex problem involves several key steps:
- **Thorough Research:** Investigate and compare various methods to select the most suitable approach.
- **Model Development:** Build a model based on the chosen method.
- **Data Input:** Input all available ear image data.
- **Training:** Train the model to achieve a high accuracy, preferably above 0.8, in identifying images.


# Background Survey

## Possible Solutions:

<li>1. Neural Network
<li>2. Hidden Markov Model
<li>3. Edge Detection

## Choice of Method
Our ultimate selection is a Neural Network, specifically the Convolutional Neural Network (CNN), for several reasons:

- **HMM Limitation:** Hidden Markov Models (HMM) are generative, probabilistic models designed to capture the process generating training sequences. However, for our task of categorizing hundreds of images, a deterministic model like CNN is more suitable.
  
- **Edge Detection Constraints:** While edge detection is valuable for extracting ear shape features, it lacks comprehensive feature information essential for accurate identification and categorization.
  
- **CNN Versatility:** CNNs are extensively used in image-related tasks, including classification, detection, and generation, making them a proven and effective choice for our image categorization problem.

## About CNN
### How CNN works:
- **Convolutional Neural Networks (CNNs)** are widely used in image recognition due to their effectiveness.
- CNNs consist of three main types of layers: **convolutional**, **pooling**, and **fully connected** layers.
- In the **convolutional layer**, filters scan an image, detecting signals in horizontal, vertical, and diagonal directions to create feature maps.
- Filters identify specific features and map their locations, allowing the CNN to capture different directional features.
- Nonlinear transformations like **ReLU or tanh** are applied after the convolutional layer to compress input within a range.
- **Pooling layers**, such as maxPooling, downsample feature maps by processing them slice by slice.
- During pooling, slices are compressed, retaining key features (e.g., max values) while discarding other information.
- The **fully connected layer** classifies output based on learned weights, enabling accurate image categorization.


## Final Solution

Despite our implemented improvement methods, the challenge persisted. Yet, we found satisfaction in the network's strong performance on the training set. To overcome this hurdle and align with our objective, we devised a compromise: **we utilized the entire dataset as the training set**. Consequently, **all images could be accurately identified and categorized**. Moreover, **when provided with a random image from this dataset, we could showcase all other ear images belonging to the same individual.**


## Comment
## Limited by the given time constraints and our knowledge and experience in machine learning, certain improvements were made to expand the training dataset. However, a fundamental issue remains: the validation accuracy decreases while training accuracy increases. This problem arises due to the dataset's small size, with only 4 pictures per class. Splitting these limited images into training, validation, and test sets exacerbates overfitting during validation and testing.

## Additionally, although Keras is user-friendly, its encapsulated layers lack detailed verbosity, hindering our understanding of the generated CNN features. Given more time, we could explore further enhancements. Some potential options we considered include:

### 1. **CNN-HMM Hybrid Model:**
   Combining Convolutional Neural Networks (CNN) with Hidden Markov Models (HMM) for a more robust approach.

### 2. **Edge Detection:**
   Utilizing edge detection techniques to extract ear images from original photographs, reducing noise and improving data quality.


