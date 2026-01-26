---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2026-01-26T10:52
---
---

- ai vs ml vs dl: basically ai is a branch of computer science where tries to make machine which can mimic human intelligence. ML is subset of ai which tries to make machine learn patterns from the data. ML needs processed data to find patterns from the data. DL is a subset of ML which also tries to find pattern but it can work with raw data.
- gradient descent: gradient descent is a signal that goes through the network and ig tell it about loss or something and thus helps in modifying weights. 
- vanishing gradient descent: The problem which was there in rnn was that signal of gradient descent gets too small and so learning doesnt happen on the earlier parts of network so model remains too simple and hence becomes underfitting model and this weak signal is called vanishing gradient descent
- exploding gradient descent: ig this doesnt cause overfitting but what happens is that the signal to modify weights is so strong that it changes the weights too much so the model becomes very flexible and sensitive so it also creates problem
- preprocessing steps sare in ml:   
- NN vs Reinforcement learning
- activation function: sigmoid relu du and what it does and what without it
- perceptron: so perceptron is single layer neural network with no hidden layer. It has just one input layer with muliple inputs and one output neuron. The output neuron recieves all the input applies weights and activation function and then store the value. 
	- also it's a binary classifier so it gives probability which is either in favous or against it
	- for this calculation it uses activation function
- sandbox function: ig it's an activation function and how it works is it takes all the inputs from the previous inputs and then gives probability based or against it. ig it's formula is inputs * wieghts + bias
	- ig it receives nth dimentional vectors from other nodes as input and then compute those vectors somehow to get probability which we also specify if higher than this then consider positive otherwise negative
- weights: weights is the importance or significance of input. not all inputs are important and equally important 
- transformers and their major components: encoder only models and decoder only models
- nlp: natural language processing has it's own preprocessing steps:
	- first is remove the phone numbers and email address
	- then remove all stopwords
	- then lemmatize or stemming
	- then creating vector embeddings of it
		- we have multiple ways of that
			- bag of words
			- tf-idf
			- word2vec
	- and ig after it we give these embeddings to some model and then use it to find outcome
- cnn: convolutional neural network or cnn is a type of neural networks which works well with image generation. It works well with grid data and produces output
- rnn: recurral neural network is better for text generation is it generates text one at a time and then take the genereated text as an input to generate new text. ig it cant keep context for long sentences
- lstm: or long short term memory: don't know if this is even a nn. It can keep short term memory
- attention:
- transformers: came in 2017 with the paper "attention is all you need" with proposed a new concept called self-attention
	- now we removed the recurrence and taking input one by one instead it did:
		- tokenize ( tokenization method depends on different transformers or models)
		- embeddings as well as positional embeddings gets created
		- all these embeddings goes parelily into model as input so shows parellilism 
- bias: is the number we add in activation function with goal to reduce loss but too high bias creates the model unable to learn patterns as weights are what should be used so model underfits and doesnt perform well even on training data
- variance: variance is ig model having ig weights or something ig that makes it remember the data instead of learning the pattern and hence overfitts the model
- right skewed database
- left skewed database
- evaluation
	- on regression model
		- mean square error
		- mean absolute error
		- mean error
	- on classification model
		- with the help of confusion matrix
		- precision
		- recall
		- accuracy score 
		- f1 score
		- r2 score
- neural network: while training a neural network we came accross many terms:
	- epoch: how many times we train the model with data
	- feed forward: how many times input goes inside model and output comes.
	- batch size: size of data we give model with each input
	- backword propogation: ig how optimizer helps re-train the model with new set of weights to reduce error
	- optimizer: helps model learn by changing the weights on each feedforward
- niave bayes: finding probability based on considering that our assumption is correct
- regularization:
	- l1
	- l2
- prompting: types
	- one shot prompting
	- few shot prompting
	- multi shot prompting
- ml: types
	- supervised learning: have two types of model prediction
		- classification: classifies a category
		- regression: predicts a continuous series of number
	- unsupervised
	- renforcement learning
- Ml pipeline:
	- importing the data and converting to dataframe
	- analyzing the database
	- feature selection: dropping the unnecessary column/features
	- removing/filling null values:
		- for object type column: mode
		- for numeric: mean  or some other cases
	- encoding:
		- one hot encoding
		- label encoding
	- scaling
		- min-max scaler
		- standard scaler



# Machine Learning & Deep Learning Study Notes (Corrected)

## Fundamental Concepts

### AI vs ML vs DL

- **AI (Artificial Intelligence)**: A branch of computer science that aims to create machines capable of mimicking human intelligence
- **ML (Machine Learning)**: A subset of AI that enables machines to learn patterns from data without explicit programming. ML requires preprocessed/structured data
- **DL (Deep Learning)**: A subset of ML using neural networks with multiple layers. Can work with both raw and processed data, and automatically learns features

### Gradient Descent

Gradient descent is an optimization algorithm that iteratively adjusts model weights to minimize the loss function. It calculates the gradient (derivative) of the loss with respect to weights and updates weights in the opposite direction of the gradient.

### Vanishing Gradient Problem

Occurs primarily in deep neural networks (including RNNs) when gradients become extremely small during backpropagation. This causes:

- Earlier layers learning very slowly or not at all
- Model underfitting
- Poor capture of long-term dependencies (especially in RNNs)

### Exploding Gradient Problem

Occurs when gradients become extremely large during backpropagation, causing:

- Unstable training
- Weights changing too drastically
- Model divergence and inability to converge
- **Solution**: Gradient clipping, proper weight initialization, batch normalization

---

## Preprocessing Steps in ML

### General ML Preprocessing:

1. **Handling Missing Values**: Imputation (mean, median, mode) or removal
2. **Handling Outliers**: Detection and treatment using IQR or Z-score
3. **Feature Scaling**: Normalization or standardization
4. **Encoding Categorical Variables**: One-hot encoding, label encoding, ordinal encoding
5. **Feature Engineering**: Creating new features from existing ones
6. **Feature Selection**: Removing irrelevant or redundant features
7. **Data Splitting**: Train-test-validation split

### NLP Preprocessing:

1. **Text Cleaning**: Remove special characters, URLs, emails, phone numbers
2. **Lowercasing**: Convert all text to lowercase
3. **Removing Stopwords**: Filter out common words (the, is, are, etc.)
4. **Tokenization**: Split text into words or subwords
5. **Lemmatization/Stemming**: Reduce words to root form
6. **Vectorization**: Convert text to numerical representations
    - **Bag of Words (BoW)**: Counts word frequency
    - **TF-IDF**: Term frequency-inverse document frequency weighting
    - **Word2Vec**: Dense word embeddings capturing semantic meaning
    - **BERT/Transformer Embeddings**: Contextual embeddings

---

## Neural Network Components

### Perceptron

- Single-layer neural network with no hidden layers
- Components: Input layer (multiple inputs) → Single output neuron
- Process: Weighted sum of inputs + bias → Activation function → Output
- **Binary classifier**: Produces output for binary classification
- Formula: `output = activation(Σ(weights × inputs) + bias)`
- **Limitation**: Can only learn linearly separable patterns

### Activation Functions

Transform the weighted sum of inputs to introduce non-linearity

**Common Activation Functions:**

1. **Sigmoid**:
    
    - Formula: `σ(x) = 1 / (1 + e^(-x))`
    - Output range: (0, 1)
    - Use: Binary classification output layer
    - Issue: Vanishing gradient problem
2. **ReLU (Rectified Linear Unit)**:
    
    - Formula: `f(x) = max(0, x)`
    - Output range: [0, ∞)
    - Use: Hidden layers in deep networks
    - Advantages: Computationally efficient, reduces vanishing gradient
3. **Tanh (Hyperbolic Tangent)**:
    
    - Formula: `tanh(x) = (e^x - e^(-x)) / (e^x + e^(-x))`
    - Output range: (-1, 1)
    - Use: Hidden layers, zero-centered output
4. **Softmax**:
    
    - Converts logits to probability distribution (sums to 1)
    - Use: Multi-class classification output layer
    - Formula: `softmax(x_i) = e^(x_i) / Σe^(x_j)`

**Why Activation Functions?**

- Without activation functions, neural networks would only learn linear relationships
- They enable networks to approximate complex, non-linear functions

### Weights

- Parameters that determine the importance/significance of each input
- Learned during training through backpropagation
- Different inputs have different impacts on the output

### Bias

- Additional parameter added to the weighted sum before activation
- Allows the model to fit data that doesn't pass through the origin
- **Too high bias**: Model is too simple (underfitting) - can't learn patterns even from training data
- **Too low bias**: Model may be too complex (overfitting risk)

### Variance

- Measures how much model predictions vary for different training datasets
- **High variance**: Model is too sensitive to training data (overfitting) - memorizes rather than learns patterns
- **Low variance**: Model predictions are consistent but may miss patterns

**Bias-Variance Tradeoff**: Balance between underfitting (high bias) and overfitting (high variance)

---

## Neural Network Architectures

### CNN (Convolutional Neural Network)

- Specialized for processing grid-like data (images, videos)
- **Key components**:
    - **Convolutional layers**: Extract spatial features using filters
    - **Pooling layers**: Reduce spatial dimensions (max pooling, average pooling)
    - **Fully connected layers**: Final classification
- **Applications**: Image classification, object detection, image segmentation

### RNN (Recurrent Neural Network)

- Designed for sequential data (text, time series)
- Processes input one element at a time, maintaining hidden state
- **Limitation**: Difficulty capturing long-term dependencies (vanishing gradient)
- **Applications**: Text generation, sequence prediction

### LSTM (Long Short-Term Memory)

- Special type of RNN architecture designed to handle long-term dependencies
- **Components**:
    - **Forget gate**: Decides what to discard from cell state
    - **Input gate**: Decides what new information to store
    - **Output gate**: Decides what to output
- Solves vanishing gradient problem of vanilla RNNs
- **Applications**: Machine translation, speech recognition, time series forecasting

### Attention Mechanism

- Allows models to focus on relevant parts of input when producing output
- Assigns different weights to different parts of the input sequence
- **Self-attention**: Relates different positions of a single sequence to compute representation

### Transformers

- Introduced in 2017 paper "Attention is All You Need"
- **Key innovation**: Self-attention mechanism, removes recurrence entirely
- **Architecture**:
    1. **Tokenization**: Convert text to tokens
    2. **Embeddings**: Token embeddings + positional embeddings (since no recurrence)
    3. **Encoder-Decoder structure**:
        - **Encoder**: Processes input using self-attention and feed-forward layers
        - **Decoder**: Generates output using self-attention, encoder-decoder attention, and feed-forward layers
- **Advantages**: Parallelization, better long-range dependencies
- **Types**:
    - **Encoder-only models**: BERT (for understanding tasks)
    - **Decoder-only models**: GPT (for generation tasks)
    - **Encoder-decoder models**: T5, BART (for translation, summarization)

---

## ML vs Reinforcement Learning

### Traditional ML (Supervised/Unsupervised)

- Learns from labeled (supervised) or unlabeled (unsupervised) data
- Direct input-output mapping

### Reinforcement Learning

- Agent learns by interacting with environment
- Learns through trial and error using rewards and penalties
- **Components**: Agent, Environment, State, Action, Reward
- **Goal**: Maximize cumulative reward
- **Applications**: Game playing, robotics, autonomous vehicles

---

## Training Neural Networks

### Key Terms:

**Epoch**: One complete pass through the entire training dataset

**Batch Size**: Number of samples processed before updating weights

**Feed Forward**: Forward pass where input propagates through network to produce output

**Backpropagation**: Backward pass where gradients are calculated and weights are updated to minimize loss

**Optimizer**: Algorithm that updates weights based on gradients

- **Common optimizers**: SGD, Adam, RMSprop, AdaGrad
- Determines how weights change during training

---

## Data Distribution

### Right-Skewed (Positively Skewed)

- Tail extends to the right
- Mean > Median > Mode
- Most data concentrated on the left

### Left-Skewed (Negatively Skewed)

- Tail extends to the left
- Mean < Median < Mode
- Most data concentrated on the right

---

## Model Evaluation

### Regression Metrics:

1. **Mean Squared Error (MSE)**: Average of squared differences between predicted and actual values
2. **Mean Absolute Error (MAE)**: Average of absolute differences
3. **Root Mean Squared Error (RMSE)**: Square root of MSE
4. **R² Score (R-squared)**: Proportion of variance explained by model (0 to 1, higher is better)

### Classification Metrics:

**Confusion Matrix**: Table showing TP, TN, FP, FN

1. **Accuracy**: (TP + TN) / Total
2. **Precision**: TP / (TP + FP) - Of all positive predictions, how many were correct?
3. **Recall (Sensitivity)**: TP / (TP + FN) - Of all actual positives, how many did we catch?
4. **F1 Score**: Harmonic mean of precision and recall: 2 × (Precision × Recall) / (Precision + Recall)
5. **Specificity**: TN / (TN + FP)
6. **AUC-ROC**: Area Under Receiver Operating Characteristic curve

---

## Machine Learning Algorithms

### Naive Bayes

- Probabilistic classifier based on Bayes' Theorem
- **Assumption**: Features are conditionally independent given the class (naive assumption)
- Formula: P(Class|Features) = P(Features|Class) × P(Class) / P(Features)
- **Applications**: Text classification, spam detection

### Regularization

Techniques to prevent overfitting by adding penalty terms:

**L1 Regularization (Lasso)**:

- Adds absolute value of weights to loss: `Loss + λΣ|w|`
- Can drive some weights to exactly zero (feature selection)

**L2 Regularization (Ridge)**:

- Adds squared value of weights to loss: `Loss + λΣw²`
- Shrinks weights but doesn't zero them out

**Elastic Net**: Combination of L1 and L2

---

## Prompting Techniques

### Zero-Shot Prompting

- No examples provided, just the task instruction

### One-Shot Prompting

- One example provided before the task

### Few-Shot Prompting

- Multiple examples (typically 2-10) provided before the task

### Chain-of-Thought Prompting

- Encourages step-by-step reasoning

---

## Machine Learning Types

### Supervised Learning

Learns from labeled data (input-output pairs)

**Subtypes**:

- **Classification**: Predicts discrete categories (binary or multi-class)
    - Examples: Logistic Regression, Decision Trees, SVM, Random Forest
- **Regression**: Predicts continuous numerical values
    - Examples: Linear Regression, Polynomial Regression, Ridge, Lasso

### Unsupervised Learning

Learns patterns from unlabeled data

**Subtypes**:

- **Clustering**: Groups similar data points (K-Means, DBSCAN, Hierarchical)
- **Dimensionality Reduction**: Reduces features (PCA, t-SNE, UMAP)
- **Association**: Finds rules (Apriori, FP-Growth)

### Reinforcement Learning

Agent learns optimal actions through trial and error with rewards

---

## ML Pipeline

1. **Data Collection**: Gather data from various sources
2. **Data Loading**: Import data and convert to DataFrame
3. **Exploratory Data Analysis (EDA)**:
    - Understand data distribution
    - Identify patterns and relationships
    - Detect outliers and anomalies
4. **Data Cleaning**:
    - Handle missing values (imputation or removal)
    - Remove duplicates
    - Handle outliers
5. **Feature Engineering**:
    - Create new features
    - Feature selection (drop unnecessary columns)
6. **Handling Missing Values**:
    - **Categorical columns**: Mode or create 'Unknown' category
    - **Numerical columns**: Mean, median, or forward/backward fill
7. **Encoding Categorical Variables**:
    - **One-Hot Encoding**: Creates binary columns for each category
    - **Label Encoding**: Assigns numerical labels (for ordinal data)
    - **Ordinal Encoding**: For ordered categories
8. **Feature Scaling**:
    - **Min-Max Scaler**: Scales to range [0, 1]
    - **Standard Scaler**: Standardizes to mean=0, std=1
    - **Robust Scaler**: Uses median and IQR (robust to outliers)
9. **Train-Test Split**: Split data into training and testing sets
10. **Model Selection**: Choose appropriate algorithm
11. **Model Training**: Fit model on training data
12. **Model Evaluation**: Assess performance on test data
13. **Hyperparameter Tuning**: Optimize model parameters (Grid Search, Random Search)
14. **Model Deployment**: Deploy to production environment