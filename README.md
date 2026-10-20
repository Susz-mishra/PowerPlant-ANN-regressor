# ANN Regression for Power Plant Energy Output Prediction

## 📌 Project Overview

This project uses an **Artificial Neural Network (ANN)** built with **PyTorch** to predict electrical energy output from a power plant based on environmental conditions.

The model learns the relationship between ambient temperature, exhaust vacuum, ambient pressure, and relative humidity to estimate power plant energy output.

This is a supervised machine learning project that uses a neural network for **regression**, where the goal is to predict a continuous numerical value.

## 🎯 Problem Statement

Power plant energy output can vary depending on environmental and operating conditions. Predicting the output accurately can help analyze the relationship between these conditions and power generation.

The objective of this project is to train an ANN model that predicts electrical energy output using four input features.

## 📊 Dataset Information

The project uses the `Powerplant_dataset.csv` dataset.

The dataset contains **9,568 rows and 5 columns**.

| Feature | Description |
|---|---|
| `AT` | Ambient Temperature |
| `V` | Exhaust Vacuum |
| `AP` | Ambient Pressure |
| `RH` | Relative Humidity |
| `PE` | Electrical Energy Output (Target Variable) |

The four input features are used to predict `PE`, the target variable.

## 🧠 Model Used: Artificial Neural Network (ANN)

The project implements a fully connected Artificial Neural Network using PyTorch.

### Model Architecture

- **Input Layer:** 4 input features
- **Hidden Layer 1:** 6 neurons with ReLU activation
- **Hidden Layer 2:** 6 neurons with ReLU activation
- **Output Layer:** 1 neuron for predicting electrical energy output

### How the Model Works

1. The model receives four numerical input features: `AT`, `V`, `AP`, and `RH`.
2. The input features are standardized before being passed to the network.
3. The first hidden layer learns patterns and relationships among the input features.
4. The second hidden layer learns more complex nonlinear relationships.
5. ReLU activation functions introduce nonlinearity into the network.
6. The output layer produces a continuous numerical prediction for `PE`.
7. Mean Squared Error (MSE) measures the difference between predicted and actual values.
8. Backpropagation calculates gradients to update the network's weights.
9. The Adam optimizer updates the model parameters during training.
10. The trained model is evaluated using test MSE and the R² score.

## ⚙️ Technologies and Libraries

- **Python** — Programming language
- **PyTorch** — Neural network implementation and training
- **Pandas** — Data loading and manipulation
- **NumPy** — Numerical operations
- **Scikit-learn** — Data splitting, feature scaling, and evaluation metrics
- **Matplotlib** — Visualizing training and validation losses
- **Jupyter Notebook** — Development and experimentation

## 🔄 Project Workflow

1. Load the dataset using Pandas.
2. Inspect the dataset and check for missing values.
3. Separate the input features and target variable.
4. Split the data into training and testing sets using an 80:20 ratio.
5. Standardize the input features using `StandardScaler`.
6. Convert the prepared data into PyTorch tensors.
7. Create `TensorDataset` and `DataLoader` objects for batch processing.
8. Define the ANN architecture using PyTorch.
9. Train the model using Adam optimization and MSE loss.
10. Track training and validation losses across epochs.
11. Save the model weights with the lowest recorded validation loss.
12. Evaluate the trained model using MSE and R².

## 📈 Model Performance

The notebook's saved output reports the following results:

| Evaluation Metric | Reported Value |
|---|---:|
| Training MSE | 20.3809 |
| Test MSE | 18.6832 |
| Test R² Score | 0.9347 |

An R² score of **0.9347** indicates that the model explains approximately 93.47% of the variance in the target values under the notebook's evaluation setup.

A lower MSE indicates smaller squared prediction errors. These results are the values reported in the notebook and may change when the model is retrained.

## 💾 Model Saving

The notebook saves the trained model weights in the following file:

`best_model.pt`

This file can be loaded later to restore the learned neural network parameters for inference.

Note that the weights alone do not include the fitted feature scaler. The scaler should also be saved and reused when making predictions on new, unscaled input data.

## 🛠️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Susz-mishra/YOUR-REPOSITORY-NAME.git
```

Replace `YOUR-REPOSITORY-NAME` with the actual repository name.

### 2. Navigate to the Project Directory

```bash
cd YOUR-REPOSITORY-NAME
```

### 3. Install the Required Libraries

```bash
pip install pandas numpy scikit-learn torch matplotlib jupyter
```

### 4. Prepare the Dataset

Place `Powerplant_dataset.csv` in the location expected by the notebook.

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `ANN_REGRESSION.ipynb` and execute the cells in order.

## 📁 Project Structure

```text
YOUR-REPOSITORY-NAME/
│
├── ANN_REGRESSION.ipynb
├── Powerplant_dataset.csv
├── best_model.pt
└── README.md
```

`best_model.pt` is generated when the notebook saves the trained model. Include the dataset and model file in the repository only if you have permission to distribute them and they fit GitHub's file-size limits.

## 🔍 Possible Improvements

- Fit `StandardScaler` only on the training data and use the fitted scaler to transform the test data.
- Use a separate validation set for model selection and reserve the test set for final evaluation.
- Experiment with the number of hidden layers and neurons.
- Compare ANN performance with regression algorithms such as Linear Regression and Random Forest Regression.
- Save and reuse the fitted scaler alongside the trained model.
- Build a simple web interface where users can enter input features and receive predicted power output.

## ⚠️ Limitations

- The model's predictions depend on the quality and representativeness of the training data.
- Evaluation results may vary with different training settings and random seeds.
- The model is intended for educational and analytical use, not safety-critical power plant control.

## 👨‍💻 Author

**Anuj Kumar Mishra**

GitHub: [Susz-mishra](https://github.com/Susz-mishra)

---

⭐ If you find this project useful, consider starring the repository.
