# Chatbot for Automated Question Answering 🤖💬

## 1. Introduction
This project involves the development of a chatbot designed to provide automated answers to user questions based on a predefined dataset. The chatbot leverages **Natural Language Processing (NLP)** techniques to understand user queries and deliver accurate responses, enhancing user experience and efficiency in information retrieval.

## 2. Objectives
- To create a chatbot that can understand and respond to user inquiries in natural language.
- To implement preprocessing techniques to improve the model's accuracy.
- To train a classification model that can categorize user questions and retrieve relevant answers.

## 3. Methodology

### 3.1 Data Collection
The dataset used for this project was sourced from a CSV file named `AMSC.csv`, which contains:
- **Question**: The user's query.
- **Answer**: The corresponding response to the query.
- **Category**: The classification of each question.

### 3.2 Data Preprocessing
Data preprocessing is a crucial step to ensure that the chatbot can effectively interpret user queries. The following steps were performed:
- **Lowercasing**: Convert all text to lowercase to ensure uniformity.
- **Punctuation Removal**: Eliminate punctuation to simplify the text for tokenization.
- **Apostrophe Expansion**: Expand contractions to their full forms (e.g., "don't" to "do not").
- **Stopword Removal**: Remove common English stopwords that do not contribute to the meaning of the text.
- **Stemming**: Reduce words to their root forms (e.g., "running" to "run").

These preprocessing steps were implemented through a series of functions to transform the input data consistently.

### 3.3 Model Development
The model development involved several key components:
- **Vectorization**: Using `CountVectorizer`, the preprocessed text data was converted into a numerical representation (bag-of-words). A maximum of 500 features was used to limit the dimensionality.
- **Model Training**: A `Gradient Boosting Classifier` was trained on the vectorized data. The dataset was split into training and testing sets (90% for training and 10% for testing) to evaluate the model's performance.
- **Label Encoding**: The target variable (categories) was transformed into numerical labels using `LabelEncoder`, enabling effective handling of categorical data.

### 3.4 User Interaction
The user interaction module facilitates communication between the user and the chatbot:
- **Greeting**: The chatbot greets the user and asks for their name.
- **User Input**: Users can enter their questions, which are processed through the same preprocessing pipeline.
- **Prediction**: The model predicts the category of the query, and cosine similarity is used to find the most relevant answer from the dataset.
- **Response**: The chatbot responds with the appropriate answer or informs the user if no relevant information is found.
- **Termination**: The conversation continues until the user opts to exit.

## 4. Workflow
The workflow of the chatbot can be summarized as follows:
1. Load the dataset from `AMSC.csv`.
2. Preprocess the text data (lowercasing, punctuation removal, apostrophe expansion, stopword removal, and stemming).
3. Vectorize the preprocessed text using `CountVectorizer`.
4. Train the `Gradient Boosting Classifier` on the vectorized training data.
5. Implement user interaction, processing queries, predicting categories, and retrieving answers.
6. Allow the user to exit the conversation gracefully.

## 5. Conclusion
The developed chatbot effectively automates the process of answering user queries, showcasing the application of NLP and machine learning techniques. The system is adaptable to various domains, as it can be retrained with new datasets. Future improvements could involve integrating deep learning techniques for enhanced understanding and response generation.

---

### References
- [Natural Language Processing with Python](https://www.nltk.org/book/) - A comprehensive guide on NLP techniques.
- [Scikit-learn Documentation](https://scikit-learn.org/stable/documentation.html) - The official documentation for the machine learning library used in the project.

### Requirements
- **Python** (3.x)
- Libraries:
  - `pandas`
  - `nltk`
  - `sklearn`
  - `numpy`

### How to Use This Chatbot Locally
To get started, clone the repository and follow the instructions below to set up the environment and run the chatbot.

- **Setup Environment**: Use Python 3.x to create a virtual environment. You can use `virtualenv` or similar tools.
- **Install Libraries**: Use the `requirements.txt` file to install the necessary Python dependencies.
  ```bash
  pip install -r requirements.txt
