# Binary Image Classifier using Probability and Integer Encoding

## Overview

This project is a simple yet effective classifier for small binary images of digits (`0` and `1`). Instead of using traditional machine learning techniques, it relies purely on **probability theory** and **binary-to-integer encoding** to classify images based on their similarity to known samples.

The classifier works on 3×3 grayscale images by thresholding them into binary format, converting the result into an integer, and then using a **tolerance-based probabilistic model** to determine the most likely class.

---

## How It Works

### 1. Image Preprocessing

Each image is:
- **Converted to grayscale** using OpenCV.
- **Resized to 3×3** to reduce dimensionality and complexity.
- **Thresholded** to binary (0 or 1) using a cutoff (default = 252).
- **Flattened** to a 9-element binary vector.
- **Converted to an integer** by interpreting the binary vector as a binary number.

For example, this binary vector:
[0, 1, 0, 1, 1, 0, 0, 1, 0]


is interpreted as the binary string `010110010`, which equals **178** in decimal.

---

### 2. Integer Histogram and Probability Density Function (PDF)

Once the training images for each class (`0` and `1`) are processed into integer values, we create a **histogram** (PDF) for each class:
- We count how often each integer appears.
- Normalize it to get probability density.
- Plot the distribution using a bar graph.

This allows us to **visualize** how likely a particular binary pattern (integer) is for each class.

---

### 3. Classification using Tolerance-Based Probability

For each test image:
- Convert it into an integer value as described above.
- Compare it to all training values within a specified **tolerance range**.
- Count how many training integers lie within this range for each class.
- Compute:
  
P(value | class) = (# of training values within tolerance) / (total training values)


- The class with the **higher conditional probability** is chosen as the prediction.

---

### 4. No Machine Learning Libraries

This project **does not use any machine learning frameworks**. The classification is purely based on:
- Binary transformation
- Integer encoding
- Classical probability theory (frequency-based estimation)
- Threshold-based similarity

---

## Why This Works

This method works well for **very small binary images** where patterns can be uniquely or near-uniquely encoded as integers. By using a tolerance-based model, we introduce flexibility to account for small variations (noise, artifacts, or thresholding differences) between similar digits.

---

## Limitations

- Only works on small (3×3) images.
- Assumes good thresholding can separate digits meaningfully.
- Classification accuracy is sensitive to the tolerance value.

---

## Example Results

For a test image:
- Integer value: 179
- P(value | zero) = 0.13
- P(value | one) = 0.05

Hence, it is classified as a **zero**.

---

## Folders
- /0s - Training images for class '0'
- /1s - Training images for class '1'
- /test_kaggel_mix - Unlabeled test images

