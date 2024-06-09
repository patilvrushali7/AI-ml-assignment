# Next Purchase Prediction

This repository contains the code for predicting the next purchase of a user based on their purchase history. The data was simulated using purchase records from GenZDealZ.ai, which includes purchases from platforms such as Amazon, Flipkart, Zomato, and Swiggy.

## Table of Contents

- [Overview](#overview)
- [Data Simulation](#data-simulation)
- [Tools and Libraries](#tools-and-libraries)
- [Data Preprocessing](#data-preprocessing)
- [Model Architecture](#model-architecture)
- [Training and Evaluation](#training-and-evaluation)
- [Insights](#insights)
- [Assumptions](#assumptions)
- [Conclusion](#conclusion)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Results](#results)
- [License](#license)

## Overview

The goal of this project is to develop a machine learning model capable of predicting the next purchase a user might make based on their historical purchase data. The data is simulated to reflect real-world scenarios using a list of purchases from GenZDealZ.ai.

## Data Simulation

Data was simulated to create realistic user purchase sequences. Each user had multiple purchase sequences, with each sequence containing purchases from a variety of platforms.

## Tools and Libraries

The following tools and libraries were used in this project:

- **Python**: The main programming language used.
- **NumPy**: For numerical operations.
- **Pandas**: For data manipulation and analysis.
- **Keras**: For building and training the neural network.
- **TensorFlow**: Backend for Keras.
- **Scikit-learn**: For data splitting and preprocessing.
- **Matplotlib**: For visualizations.

## Data Preprocessing

1. **Text Preprocessing**: Removed unnecessary characters and converted words into vectors.
2. **Tokenization**: Converted purchase sequences into numerical tokens.
3. **Padding**: Ensured uniform input length for the model by padding sequences.

## Model Architecture

The model is a Sequential neural network with the following layers:
1. **Embedding Layer**: Converts input tokens into dense vectors of fixed size.
2. **LSTM Layer**: Captures temporal dependencies in the purchase sequences.
3. **Dense Layer**: Outputs probabilities for each token in the vocabulary.

```python
model = Sequential()
model.add(Embedding(input_dim=vocab_size, output_dim=50, input_length=max_sequence_length))
model.add(LSTM(100))
model.add(Dense(vocab_size, activation='softmax'))
model.compile(loss='sparse_categorical_crossentropy', optimizer='adam', metrics=['accuracy'])
