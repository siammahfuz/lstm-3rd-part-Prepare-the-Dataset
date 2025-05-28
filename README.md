🧪 LSTM Dataset Preparation Module
This module is the 3rd part of the LSTM series, focused on preparing raw time series data for training Long Short-Term Memory (LSTM) models. The preprocessing steps include normalization, sequence creation, and splitting the dataset—crucial for building accurate and efficient time-series models.

📊 Features
✅ Normalization – Scales data (e.g., using Min-Max scaling) for better training performance
✅ Sequence Creation – Converts raw data into sliding windows suitable for LSTM input
✅ Train-Test Split – Chronologically splits data to avoid leakage and improve generalization
✅ Flexible Configuration – Easily adjust window sizes and target shifts

🧩 Function Descriptions
normalize_data(data)
Parameter:

data: 2D NumPy array (raw time series data)

Returns:

Normalized data array

Scaler object (for inverse transformation)

create_sequences(data, time_steps)
Parameter:

data: 2D array (normalized data)

time_steps: Number of past time steps to use as input

Returns:

Tuple of (X, y) where X is 3D for LSTM and y is 2D target values

train_test_split_sequences(X, y, train_ratio=0.8)
Parameter:

X: Input sequence

y: Target sequence

train_ratio: Proportion of data to use for training

Returns:

X_train, X_test, y_train, y_test

✅ Example Usage
python
Copy
Edit
import numpy as np
from lstm_dataset_utils import normalize_data, create_sequences, train_test_split_sequences

# Sample time series data
data = np.array([[10], [12], [15], [20], [25], [30], [35], [40]])

# Normalize
normalized_data, scaler = normalize_data(data)

# Create sequences
time_steps = 3
X, y = create_sequences(normalized_data, time_steps)

# Split into train and test
X_train, X_test, y_train, y_test = train_test_split_sequences(X, y)
📁 Files Included
lstm_dataset_utils.py: Main script with all utility functions

sample_data.csv: Example input dataset (optional)

README.md: Documentation

🛠 Requirements
Python 3.x

NumPy

Scikit-learn

(Optional: TensorFlow/Keras for model development)

bash
Copy
Edit
pip install numpy scikit-learn
📌 Use Case
This module is ideal for time-series forecasting, stock price prediction, IoT sensor data analysis, and other applications where temporal patterns are essential.

📃 License
This project is licensed under the MIT License. Feel free to use, share, and modify.

🙋‍♂️ Author
Md Mahfuzur Rahman Siam
Software Tester & Programmer | Research & Community Support
📫 Email: ksiam3409@gmail.com
🔗 LinkedIn: linkedin.com/in/md-mahfuzur-rahman-siam

