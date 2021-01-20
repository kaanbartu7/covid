# Disaster Response Project - Multioutput NLP Classifier

In this project, we will build a model to classify messages that are sent during disasters. There are 36 pre-defined categories, and examples of these categories include Aid Related, Medical Help, Search And Rescue, etc. By classifying these messages, we can allow these messages to be sent to the appropriate disaster relief agency. This project will involve the building of a basic ETL and Machine Learning pipeline to facilitate the task. This is also a multi-label classification task, since a message can belong to one or more categories. We will be working with a data set provided by [Figure Eight](https://www.figure-eight.com/) containing real messages that were sent during disaster events.

Finally, this project contains a web app where you can input a message and get classification results.


## File Descriptions
~~~~~~~
        disaster_response_pipeline
          |-- app                            
                |-- templates                //contains html file for the web application
                        |-- go.html
                        |-- master.html
                |-- run.py                   //Flask file to run the web application
          |-- data
                |-- messages.csv     // text data for messages
                |-- categories.csv   // category data for messages
                |-- messages.db      // output of the ETL pipeline
                |-- data_preparation.py  // ETL pipeline scripts
                |-- ETL Pipeline Preparation.ipynb  //ipynb notebook for preparation processes
          |-- models
                |-- classifier.pkl    //machine learning model's best estimator prameters in a pickle file
                |-- train_classifier.py  //machine learning pipeline scripts to train and create a classifier model pickle
                |-- ML Pipeline Preparation.ipynb  ////ipynb notebook for modelling processes

          |-- README
          |-- Screenshots
~~~~~~~

### Installing
To clone the git repository:
```
git clone https://github.com/canaveensetia/udacity-disaster-response-pipeline.git
```
<a name="execution"></a>
### Executing Program:
1. You can run the following commands in the project's directory to set up the database, train model and save the model.

    - To run ETL pipeline to clean data and store the processed data in the database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/disaster_response_db.db`
    - To run the ML pipeline that loads data from DB, trains classifier and saves the classifier as a pickle file
        `python models/train_classifier.py data/disaster_response_db.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/
