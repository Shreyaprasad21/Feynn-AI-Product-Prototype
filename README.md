# AI-Product-Service-Prototype-Development_DNA_classification app 

This repository contains project for classifying DNA sequences to identify E. coli bacteria.

**Project Structure**        

* **data.py** (not included): Script to download and pre-process the DNA sequence data.
* **model.py** (content displayed above): Script for training and evaluating a machine learning model for E. coli classification.
* **EColi-encoder.pickle**: Saved OneHotEncoder object for encoding DNA sequences.
* **E-Coli_model.pickle**: Saved machine learning model for E. coli classification.

**Requirements**

* Python 3.x              
* numpy
* matplotlib.pyplot
* pandas
* seaborn
* scikit-learn
* pickle

**Usage**

1. Install the required libraries.
2. Run `model.py` to train and evaluate the model. 
3. The saved model (`E-Coli_model.pickle`) and encoder (`EColi-encoder.pickle`) can be used to classify new DNA sequences.

**Example**

```python
from sklearn.preprocessing import OneHotEncoder
from sklearn.neural_network import MLPClassifier
import pickle

# Load the encoder and model
encoder = pickle.load(open("EColi-encoder.pickle", "rb"))
model = pickle.load(open("E-Coli_model.pickle", "rb"))

# Define a new DNA sequence
genome = "ttactagcaatacgcttgcgttcggtggttaagtatgtataatgcgcgggcttgtcg"
genome_list = list(genome)

# Encode the sequence
df_test = pd.DataFrame(genome_list)
df_test = df_test.transpose()
data_test = encoder.transform(df_test).toarray()

# Predict the class
prediction = model.predict(data_test)[0]

![image](https://github.com/Shreyaprasad21/Feynn-AI-Product-Service-Prototype-Development-DNA-classification-app/assets/142075353/bf7631ba-0189-49af-8422-9268be6720e0)
