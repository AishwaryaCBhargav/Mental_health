The project is divided into four parts: src folder, data folder, test folder, requirements.txt file.

src folder contains the .ipynb file that contains all the analysis, model training and results.

data folder contains the data that was used for analysis and model training.

test folder contains the pickle file of test data that contains a part of original data that was hidden from the model. The optimised model was tested on this unseen data.

requirements.txt file contains names of all modules that were installed for the analysis and model training.


################################## To test the model on test data ################################################

To load the test set, saved as a pickle file in test folder, use the following commands:

pickle_file_path = '../test/x_test.pkl' 
X_test = pd.read_pickle(pickle_file_path) # Load the pickle file into a DataFrame

To load the trained model, use the following command:

with open('../model/xgboost_model.pkl', 'rb') as f:
    model = pickle.load(f)

To test the model on test data, use the following code:

y_pred_test = model.predict(X_test)
print(classification_report(y_test, y_pred_test)