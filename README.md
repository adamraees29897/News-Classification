# News-Classification

- Objective: The goal of this project is to build a text classification model using pre-trained model BERT or  GPT-2.
- Dataset Used: AG News Classification Dataset (from Kaggle)
- IDE Used: Google Colab
- Text Processing Steps: 
    1 Import data from drive. 
    2. Using only 2500 samples from each category.
    3. Checked the dataset for null values.
    4. The dataset contains 4 categories and 3 columns(Class Index, Title, Description)
    5. Combine ‘Title’ and ‘Description’ to form x_train as well as x_test.
    6. ‘Class Index’ to form y_train and y_test.
    7.  Create a function to remove punctuation and stop words. Also lemmatize the text.
    8. Split the dataset into training, validation and testing dataset.

- Model Building Steps:
    1. Built model and tokenizer using ‘distilbert-base-uncased-finetuned-sst-2-english’
    2. Took maximum length of the text data is equal to 128. And tokenised the data.
    3. Used the layers of Bert model up to last hidden layer.
    4. Used ‘GlobalMaxPool1D’ as pooling layer.
    5. Used a ‘Dense’ layer with 128 filters and ‘relu’  activation function.
    6. Used a ‘Dropout’ layer  and also a ‘Dense’ layer with 32 layers and ‘relu’ activation function.
    7. Output layer with 4 filters and ‘sigmoid’ activation function.

- Training the model:
    1. Used ‘Adam’ optimiser with ‘5e^-5’ learning rate and 1e^-8 epsilon.
    2. Used ‘Categorical Crossentropy’  as loss function and used ‘Catergorical Accuracy’ as metrics.
    3. Fitted the model with 5 epochs.

- Testing and Performance metrics
Tested the model using test dataset. Used ‘classification report’ as the perfomance metrics. And got about 90% accuracy.

Also tested the model with a custom snippet of text.

Suggestions to improve:
1. Can change the value of  ‘learning_rate’  and ‘epsilon’.
2. Can increase the number of epochs. And change the ‘batch_size’.
3. Can  also increase the number of layers used.
