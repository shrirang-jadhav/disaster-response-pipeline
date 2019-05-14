# Disaster Response Pipeline Project

### Project Motivation:
This is part of portfolio projects for DSND.

Figure Eight has provided distaster data for this project.
Objective of the project is to build a model for an API that classifies these disaster messages by applying Data-engineering as well as NLP skills.


### Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/

### Important Files:
1. `data/process_data.py` : File takes the file paths of the two datasets and database, cleans the datasets, and stores the clean data into a SQLite database in the specified database file path.
2. `models/train_classifier.py` : File takes the database file path and model file path, creates and trains a classifier, and stores the classifier into a pickle file to the specified model file path. It also uses a custom tokenize function using nltk to case normalize, lemmatize, and tokenize text. This function is used in the machine learning pipeline to vectorize and then apply TF-IDF to the text. File builds a pipeline that processes text and then performs multi-output classification on the 36 categories in the dataset.
3. `app/run.py` : Start the Python server for the web app and prepare visualizations. The main page includes visualizations using data from the SQLite database.
When a user inputs a message into the app, the app returns classification results for all 36 categories.
