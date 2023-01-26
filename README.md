# Chatbot Model Creation

This script is used to create a chatbot model using the Natural Language Toolkit (nltk) library and the Keras deep learning library. The script performs the following steps:

1. Imports the necessary libraries: nltk, json, pickle, numpy, keras, and random.
2. Initializes the WordNetLemmatizer from nltk to lemmatize words.
3. Opens and reads the intents.json file, which contains the patterns and tags for the chatbot.
4. Tokenizes the words in each pattern and adds them to the "words" list.
5. Adds the tokenized pattern and corresponding tag to the "documents" list.
6. Adds the tag to the "classes" list if it is not already present.
7. Lemmatizes and lowercases the words in the "words" list, removes duplicates, and sorts the list.
8. Sorts the "classes" list.
9. Prints the number of documents, classes, and unique lemmatized words.
10. Saves the "words" and "classes" lists to words.pkl and classes.pkl files using pickle.dump().
11. Creates the training data by initializing an empty "training" list and creating a bag of words for each pattern in the "documents" list.
12. Shuffles the training data and converts it to a numpy array.
13. Creates the train and test lists (X - patterns, Y - intents).
14. Initializes a sequential model with three layers: the first layer has 128 neurons, the second layer has 64 neurons, and the third output layer has the number of neurons equal to the number of intents to predict the output intent with softmax.
15. Compiles the model using categorical_crossentropy as loss function, sgd as optimizer, and accuracy as metrics.
16. Fits the model on the training data and saves it as chatbot_model.h5 file.
17. Prints "model created" upon completion.
