
# 🖼️ Image Recognition with CNN (MNIST Dataset)

## 📌 Overview
This project demonstrates **image recognition** using a **Convolutional Neural Network (CNN)** on the **MNIST dataset** (handwritten digits 0–9).  
It walks through:
- Dataset loading
- Data visualization
- CNN model creation
- Training & evaluation

## 📂 Dataset
- **Source:** [MNIST Handwritten Digit Dataset](https://www.kaggle.com/datasets/hojjatk/mnist-dataset)  
- **Classes:** Digits from `0` to `9`  
- **Shape:** 28×28 grayscale images  

## ⚙️ Requirements
Install the following dependencies before running the notebook:

```bash
pip install tensorflow matplotlib kagglehub
```

## 📜 How It Works
1. **Load Dataset**  
   Uses `tensorflow.keras.datasets.mnist` to load training & testing images.

2. **Visualize Samples**  
   Displays a 3×3 grid of sample images with their labels.

3. **Preprocess Data**  
   - Reshape images to `(28, 28, 1)` for CNN input
   - Normalize pixel values to `[0, 1]`

4. **Build CNN Model**  
   ```python
   model = Sequential([
       Conv2D(32, (3, 3), activation='relu', input_shape=(28, 28, 1)),
       MaxPooling2D((2, 2)),
       Conv2D(64, (3, 3), activation='relu'),
       MaxPooling2D((2, 2)),
       Flatten(),
       Dense(128, activation='relu'),
       Dense(10, activation='softmax')
   ])
   ```

5. **Compile Model**  
   ```python
   model.compile(optimizer='adam',
                 loss='sparse_categorical_crossentropy',
                 metrics=['accuracy'])
   ```

6. **Train & Evaluate**  
   - Train with `model.fit()`
   - Evaluate accuracy with `model.evaluate()`

## 📊 Results
- **Training Accuracy:** ~99% (varies)
- **Test Accuracy:** ~98% (varies)
- The model can accurately classify handwritten digits.

## 🚀 Usage
1. Open the `.ipynb` file in **Google Colab** or **Jupyter Notebook**.
2. Run each cell in order.
3. Modify parameters (e.g., epochs, layers) to experiment.

## 📌 Future Improvements
- Add **data augmentation** for better generalization.
- Experiment with **dropout layers** to reduce overfitting.
- Try different optimizers like `RMSprop` or `SGD`.

## 📜 License
This project is open-source and free to use.
