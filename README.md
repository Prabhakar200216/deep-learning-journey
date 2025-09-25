# deep-learning-journey

# Diabetes Prediction using Keras Tuner

This project demonstrates how **Keras Tuner** can be used to optimize hyperparameters in a neural network for a diabetes prediction dataset.

---

##  What is Keras Tuner?
Training deep learning models is not just about building a neural network and running it. The real magic comes from **choosing the right hyperparameters** — things like:

- Optimizer (Adam, RMSprop, SGD, etc.)
- Number of layers in the network
- Number of neurons per layer
- Activation functions

Instead of guessing these values manually, **Keras Tuner** helps us automatically search and pick the best combination.

---

##  My Experiment

### 1. Without Tuner
- Ran the model for 100 epochs.  
- **Accuracy:** 86%  
- **Validation Accuracy:** 74.03%  
 Clearly overfitting.

---

### 2. With Tuner (step by step)
- First tuned the optimizer, then number of nodes, then number of layers.  
- Best config: **96 nodes**, **6 layers**.  
- **Accuracy:** 100%  
- **Validation Accuracy:** 70%  
 Still overfitting.

---

### 3. With Tuner (all-in-one function)
- Tuned optimizer, layers, and nodes together.  
- Ran for 100 epochs.  
- **Accuracy:** 79.91%  
- **Validation Accuracy:** 76.62%  
- **Best Parameters found:**
  - Layers: 9  
  - Nodes per layer: 48  
  - Activation: ReLU  
  - Optimizer: Adam  

 Much better balance between train and validation.

---

##  Why use Keras Tuner?
- Saves time compared to manual trial-and-error.  
- Helps reduce underfitting/overfitting by finding better balance.  
- Can discover architectures humans might not think of.  

In short: Keras Tuner = a smart assistant that tries many model designs and suggests the best one.


# Cat vs Dog Classifier 

This project demonstrates the use of **Data Augmentation** and **Transfer Learning** with the **VGG16** model to classify cats and dogs.

---

## 🔎 Concepts Used

### Data Augmentation
Instead of collecting thousands of images, we apply transformations like rotation, flipping, zooming, and shifting to the existing dataset. This makes the model see "new" data every epoch and helps reduce overfitting.

### Transfer Learning (VGG16)
- Used **VGG16**, a CNN pre-trained on ImageNet.  
- **CNN part frozen** → keeps the powerful feature extractor intact.  
- Added my own **ANN layers** on top (Dense layers).  
- Added **Dropout after each Dense layer** to prevent overfitting.

**Dropout** → Randomly drops some neurons during training to prevent overfitting and make the model more robust.

---

## Results
- **Training Accuracy:** 92%  
- **Validation Accuracy:** 90%  
➡️ Strong generalization and balanced performance.

---

##  Why this approach?
- Training a CNN from scratch needs huge data + compute.  
- Transfer learning gives us pre-trained "knowledge" for free.  
- Data augmentation + dropout = better generalization and less overfitting.


