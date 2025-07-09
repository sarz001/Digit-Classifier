# Digit Classifier

This project implements a simple digit classification system that operates on **3×3 grayscale images** of handwritten digits (0 and 1). Each image is converted into a binary vector, encoded as an integer, and then classified based on proximity to known training examples using a **tolerance-based probability model**.

---

## Project Title

**Digit Classifier: A Binary-Encoded Tolerance-Based Model for 3×3 Digit Recognition**

---

## Description

The goal of this project is to classify small images (resized to 3×3) into digits `0` or `1`. The classifier uses the following approach:

- Preprocess each image to 3×3 grayscale
- Binarize pixel values using a threshold
- Flatten the binary image into a 9-bit binary vector
- Convert the vector to an integer
- Estimate class membership by comparing the integer with the training distributions of digits `0` and `1`, within a user-defined **tolerance window**

This method is useful for educational demonstration of:
- Binary image encoding
- Integer-based feature extraction
- Basic probabilistic classification

---

Let me know if you'd like a full updated `README.md` or `digit_classifier.py` version based on this name.
