# NativePy

Native Language Identification using BERT state-of-the-art neural networks powered by google


# Data used and objective 

The data used consists of the following:

-	lang_id_train.csv: 6000 texts with labels used to train the model
-	lang_id_eval.csv: 2000 texts with labels used to tune the hyperparameters of the model
-	lang_id_test.csv: 2000 texts with labels for the evaluation

All of those files have 10 different categorical targets (totally balanced), and are the following: ‘Japanese’, ‘Korean’, ‘Mandarin’, ‘Vietnamese’, ‘Thai’, ‘Spanish’, ‘Arabic’, ‘Cantonese’, ‘Polish’, and ‘Russian’.

The objective of this work is to use BERT in order to obtain feature vectors from the texts, and then use those vectors to classify the texts depending on the native language of the writter.


# Steps to reproduce the results

## Preprocessing
First of all, in order to fed the texts to BERT, they have to be only text, without label. In order to get those new datasets, a preprocessing python script has to be executed. Its name is "Preprocessing.ipynb"

## Obtaining Feature Vectors
The 2nd step is to obtain the feature vectors (that are going to be used to fit the models) from the preprocessed ".csv" files, and to do this the Bert program has to be used. Several parameters and text files must be sent to the “extract_features.py” script of the program, and to do so a shell script has to be used, the “run.sh” script.
In order to run this script in any computer, four directories must be specified:
-	BERT_BASE_DIR: directory of the BERT program.
-	BERT_DATA_DIR: directory of the pre-trained data.
-	INPUT_DIR: directory of the input data. In our case this will contain the train, evaluation and test sets, which will be transformed from text into vectors. Note that this data must be preprocessed as said before, so this directory must be the one used in the preprocessing step.
-	OUTPUT_DIR: directory of the output data, the vectors. Those vectors are the ones used in the next step of building a model.

## Run the Python script

In this final step, the "Native Language Identification.ipynb" Jupyter Notebook has to be used. As said before, in order to run the Notebook adequately only the following paths should be changed:
-	ORIGINAL_DATA_DIR: Directory of the original training, eval and test data
-	BERT_FEATURE_DIR: Directory of the obtained BERT feature vectors
-	PRINT_RESULTS: Directory where the results (images and csv file) should be saved







