# Text Generation using BiDirectional LSTM

This GitHub project presents a text generation model using a bidirectional LSTM (Long Short-Term Memory) with encoder-decoder layers. The model is trained on COVID-19 research corpus, and its purpose is to generate abstracts from the corpus.

## Overview

The project follows these steps:

1. Load each abstract from the JSON files.
2. Preprocess the abstracts by removing numbers, emails, punctuations, and URLs.
3. Tokenize the words and save them into a text file.
4. Prepare the datasets for training the model.
5. Define and train the model architecture.
6. Save the trained model and draw the training loss over epochs.
7. Use seed texts to predict the next 40 words.

## Data Preprocessing

The COVID-19 research corpus is first preprocessed by removing unnecessary elements such as numbers, emails, punctuations, and URLs. After preprocessing, the abstracts are tokenized and saved into a text file.

## Dataset Preparation

The dataset is prepared for training by using a sliding window approach. A window of size 10 is used to predict the $11^{th}$ word, and the window is moved across every sentence in the dataset.

## Model Architecture

The model architecture consists of the following:

- An embedding layer with an embedding size of 128.
- Two bidirectional LSTM layers.

## Training

The model is trained for 100 epochs using:

- Cross-entropy loss function.
- Adam optimizer.
- CyclicLR scheduler for adaptive learning rate.

## Results

The model was trained on the first 10,000 corpuses. Using three different seed texts, the model generated text sequences of length 40. The generated texts were not perfect but made some sense.

## Limitations and Future Work

The limitations of the current model include:

- Only 10,000 corpuses were used for training, which might not be sufficient for better results.
- The model architecture is relatively simple, with only two layers.

For better results, the following improvements can be considered:

- Use the entire COVID-19 research corpus for training.
- Implement a more complex model architecture with additional layers.

However, these improvements would significantly increase the training time. The current training time for 10,000 corpuses was around 400 minutes (4 minutes per iteration).
