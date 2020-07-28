# Engineering Admission Cutoff LearningSystem <br/> 
The system can be compiled and run on MAC, Linux/Unix, and Windows systems as a command line program. The implementation is written in Python, version 3.7.1. <br/> 
#### Required Modules: <br/> 
The following open source programs need to be installed on your computer using pip or anaconda: <br/> 
pip3 install -U scikit-learn scipy matplotlib  <br/> 
pip3 install pandas <br/> 
pip3 install numpy <br/> 
pip3 install tensorflow==2.0 <br/> 
pip3 install keras <br/> 

Once the required modules have been successfully installed, execute the src/run.py ﬁle. <br/> 

#### Implemented Modules: <br/> 
Below is a list of all of the Python modules included in the Code folder, along with a brief description of each.<br/> 
##### 1. postalCodeChecker.py:  <br/> 
Uses student postal codes to ﬁnd their approximate distance to the university in question. <br/> 
##### 2. data.py:  <br/> 
Parses and extracts relevant input data for storing into a data structure.  <br/> 
• prepare data() Loads the cleaned data for all 8 years of students that received an oﬀer of admission and does some additional parsing. Splits the data into 4 groups: X train (applicant features for students in the train data), y train (whether the corresponding student in the training data accepted an oﬀer), X test (applicant features for students in the test data), y test (whether the corresponding student in the test data accepted an oﬀer). The data from all 8 years are scrambled and split into 2 groups where 80% of the students in the data pool make up the training data and the remaining 20% is used to make up the test data. Note: rerunning this method will randomize and split the data amongst the 4 groups again. For this reason it should not be run, rather, the retrieve method outlined below should be used to access the saved data. <br/> 
• retrieve data() Retrieves the previously created and saved X train, y train, X test and y test data and loads it for use. <br/> 
##### 3. neural network.py:  <br/> 
• create model() The Keras library is used here to create a simple neural network model. The model is then trained using the train data. This helps determine appropriate parameters for the model. We save this model in a ﬁle.  <br/> 
• retrieve model() Retrieves the previously created and saved model and loads it for use. <br/> 
##### 4. support vector machine.py:  <br/> 
• create model() The sklearn library is used to create a simple support vector machine. The model is then trained using the train data. This helps determine appropriate parameters for the model. We save this model in a ﬁle. <br/> 
• retrieve model() Retrieves the previously created and saved model and loads it for use.  <br/> 
##### 5. test accuracy.py: <br/> 
• accuracy NN() Determines and displays the accuracy of the neural network model and algorithm. This is done for the model by predicting whether a student will accept an oﬀer for the students represented by the X train data and comparing the prediction to the y train data and for the algorithm by predicting whether a student will accept an oﬀer for the students represented by the X test data and comparing the prediction to the y test data using the saved neural network model.  <br/> 
• accuracy SVM() Determines and displays the accuracy of the support vector machine model and algorithm. This is done for the model by predicting whether a student will accept an oﬀer for the students represented by the X train data and comparing the prediction to the y train data and for the algorithm by predicting whether a student will accept an oﬀer for the students represented by the X test data and comparing the prediction to the y test data using the saved support vector machine model.  <br/> 
##### 6. predict.py:  <br/> 
• predict(model, ﬁle to path) Using the given model, predicts whether students represented by the X test data will accept an oﬀer if extended and saves the prediction to the ﬁle in the speciﬁed path. <br/> 
• predict NN() Makes the prediction for the students represented by X test using the saved neural network model.  <br/> 
• predict SVM() Makes the prediction for the students represented by X test using the saved support vector machine model.  <br/> 
• allocate students(sorted students, max capacity, model) Determines the lowest average for which an amount of students equal to max capacity will accept an oﬀer if extended (where students are represented in the sorted students data by their applicant features and their acceptance of an oﬀer is determined by making a prediction using the provided model).  <br/> 
• calculate cutoﬀ(data from path, target seat cap, model) Retrieves and parses data about students that applied to the university for a given year, where the location of the data is speciﬁed by the ﬁle path (data from path). This data is used to determine the cutoﬀ average that must be output to have an amount of students predicted to accept an extended oﬀer equal to the target seat cap. The passed model is used to make the prediction as to whether a student in the dataset will accept an oﬀer if extended.  <br/> 
##### 7. run.py  <br/> 
Runs the code to determine what the cutoﬀ GPA must be such that a number of students equal to target seat cap are predicted to accept an oﬀer of admission to the university. The predictions are made by ﬁrst using the neural network model and then the support vector machine model, the results of both are displayed. The accuracy of the neural network and the support vector machine are also displayed. The target seat cap as well as the year of students for which the code should be run on can be speciﬁed by changing the values in the input.yaml ﬁle.  <br/> 
