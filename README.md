# ASSIGNMENT3--Q3
Implementing an RNN for Text Generation
RNN for Text Generation with LSTM
This project implements a Recurrent Neural Network (RNN) using Long Short-Term Memory (LSTM) layers for generating text. The model is trained on a dataset of Shakespeare's sonnets (or any other text dataset you choose), and it predicts the next character in a sequence to generate coherent text based on a given prompt.
Project Overview
Objective: Train an LSTM-based RNN to predict the next character in a given text and generate new text one character at a time.

Model Architecture: The model uses LSTM layers to learn the sequential structure of text. The model is trained on character-level sequences, where each character in the input sequence influences the prediction of the next character.

Temperature Scaling: Temperature scaling is applied during text generation to control the level of randomness. A low temperature leads to more predictable, deterministic text, while a high temperature increases randomness and creativity.
Sony Pailla
Master’s Student in Computer Science
University of Central Missouri
GitHub: sonypailla
Project Structure
.
├── model.py             # Contains the LSTM model definition
├── generate_text.py     # Script to generate text from the trained model
├── data_preprocessing.py # Preprocessing the text data
├── README.md            # This file
└── shakespeare_sonnets.txt   # Example text data (or any text file for training)
Step 1: Prepare the Dataset
To train the model, use a text dataset (e.g., Shakespeare's sonnets or any other dataset). Place your text data in a .txt file (e.g., shakespeare_sonnets.txt), which will be used for training the model.

Step 2: Preprocess the Data
The text data is preprocessed into character-level sequences:

Character Encoding: Each unique character is assigned an index.

Sequence Padding: Sequences are padded to ensure that the model receives inputs of a consistent length.

python
Copy
Edit
# Example of loading and preprocessing text data
with open("shakespeare_sonnets.txt", "r") as file:
    text = file.read().lower()

chars = sorted(set(text))  # Unique characters in the dataset
char_to_idx = {char: idx for idx, char in enumerate(chars)}  # Mapping characters to indices
idx_to_char = {idx: char for idx, char in enumerate(chars)}  # Reverse mapping
Step 3: Define the LSTM Model
The model is built using an LSTM layer to predict the next character in the sequence. You can experiment with different numbers of layers and units for the LSTM.
Step 4: Train the Model
Train the model on the preprocessed data. You may need to adjust the number of epochs and batch size depending on your dataset.
Step 5: Generate Text
After training, use the generate_text function to generate new text based on a starting string. The temperature parameter controls the randomness of the output.

Temperature Scaling
The temperature parameter controls the randomness of the generated text. Lower values (e.g., 0.5) make the model more deterministic, while higher values (e.g., 1.0) introduce more variability in the output.
