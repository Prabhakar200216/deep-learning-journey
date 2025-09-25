# deep-learning-journey

# Diabetes Prediction using Keras Tuner

This project demonstrates how **Keras Tuner** can be used to optimize hyperparameters in a neural network for a diabetes prediction dataset.

---

## 🔎 What is Keras Tuner?
Training deep learning models is not just about building a neural network and running it. The real magic comes from **choosing the right hyperparameters** — things like:

- Optimizer (Adam, RMSprop, SGD, etc.)
- Number of layers in the network
- Number of neurons per layer
- Activation functions

Instead of guessing these values manually, **Keras Tuner** helps us automatically search and pick the best combination.

---

## 📊 My Experiment

### 1. Without Tuner
- Ran the model for 100 epochs.  
- **Accuracy:** 86%  
- **Validation Accuracy:** 74.03%  
➡️ Clearly overfitting.

---

### 2. With Tuner (step by step)
- First tuned the optimizer, then number of nodes, then number of layers.  
- Best config: **96 nodes**, **6 layers**.  
- **Accuracy:** 100%  
- **Validation Accuracy:** 70%  
➡️ Still overfitting.

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

➡️ Much better balance between train and validation.

---

## 💡 Why use Keras Tuner?
- Saves time compared to manual trial-and-error.  
- Helps reduce underfitting/overfitting by finding better balance.  
- Can discover architectures humans might not think of.  

In short: Keras Tuner = a smart assistant that tries many model designs and suggests the best one.

---

## 🚀 Future Improvements
- Add regularization/dropout to reduce overfitting further.  
- Try different search strategies (RandomSearch, Hyperband, Bayesian Optimization).  
- Test on other medical datasets.
