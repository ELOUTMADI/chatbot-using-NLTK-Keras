# Chatbot Model Creation
## Introduction
This script is used to create a chatbot model. It uses the Natural Language Toolkit (NLTK), Keras, and some other utility libraries to accomplish this task. The script loads a JSON file called "intents.json" which contains patterns of text and their corresponding intents (or classifications).

## Importing Libraries
The following libraries are imported in the script:

- `nltk` for tokenizing and lemmatizing words
- `WordNetLemmatizer` from nltk.stem for lemmatizing words
- `json` for loading and parsing the intents JSON file
- `pickle` for saving the lists of words and classes
- `numpy` for working with arrays
- `Sequential` and `Dense`, `Activation`, Dropout from keras.models and keras.layers for creating the neural network model
- `SGD` from keras.optimizers for compiling the model
- `random` for shuffling the training data

## Loading and Processing the Intents Data
The script loads the `intents.json` file and uses the `json.loads()` function to parse it into a dictionary. The script then loops through the intents in the JSON file and tokenizes the patterns using NLTK's `word_tokenize()` function. These tokenized patterns are added to a list called "documents" along with their corresponding intent.

The script also creates a list of unique words called "words" and a list of unique intents called `classes`. The words are pre-processed by lemmatizing them using the `WordNetLemmatizer()` and removing duplicates. The script then saves these lists of words and classes to pickle files.

## Creating the Training Dataset
The script creates a training dataset by creating a bag of words representation for each pattern and its corresponding intent. The script also creates an output row of 0's and 1's, where a 1 corresponds to the intent of the pattern. The script shuffles this training data and turns it into a numpy array.

## Creating and Compiling the Neural Network Model
The script creates a neural network model using Keras, with 3 layers. The first layer has 128 neurons, the second layer has 64 neurons, and the third layer has the same number of neurons as the number of intents. The script then compiles the model using Stochastic Gradient Descent with Nesterov accelerated gradient.

## Fitting and Saving the Model
The script then fits the model using the training data and saves the model as "chatbot_model.h5". The script then outputs "model created" to indicate
