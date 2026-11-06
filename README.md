# project_ML
Network Protocol Classification Using Machine Learning

## Project overview

This beginner-level machine learning project uses packet information to predict the network protocol. It follows the workflow in the project guidance: inspect and clean the data, prepare features, train classification models, compare their results, and try a prediction for a sample packet.

## Dataset

The project uses `YouTube_Live_Merged.csv`. In the supplied file, the first four data values appear to represent source IP, destination IP, protocol, and packet length, while the CSV header does not match those values. Check the loading and column-renaming cell in the notebook before running the project.

The supplied data does not appear to include a usable timestamp. Therefore, this beginner version uses packet `Length` as its feature and `Protocol` as its prediction target. It does not use the `Info` field, source IP, or destination IP as model features.

## Models used

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest

The models are compared using test accuracy. The notebook also shows a classification report and confusion matrix for the best-performing model.

## Requirements

Install these Python libraries if they are not already available:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

The notebook can be run in Google Colab or Jupyter Notebook.

## How to run

1. Open the project notebook in Google Colab or Jupyter Notebook.
2. Upload or place `YouTube_Live_Merged.csv` where the notebook can access it.
3. If using Colab, run the upload cell and select the CSV file.
4. Run each notebook cell in order, from the imports through the final prediction.
5. Review the printed protocol counts, model comparison, classification report, confusion matrix, and sample prediction.

## Project workflow

1. Load and inspect the CSV file.
2. Rename the columns to match the actual row contents.
3. Clean invalid protocol and packet-length values and remove duplicate rows.
4. Limit the data to at most 100,000 rows and remove protocol classes with fewer than five examples.
5. Encode protocol labels and split the data into training and test sets.
6. Scale packet length for Logistic Regression and KNN.
7. Train and compare four classification models.
8. Evaluate the best model and predict a protocol for a sample packet.

## Note on results

The accuracy and sample prediction depend on the dataset and the notebook run. Record the actual values shown by your notebook; they are not fixed in this README. Since this version uses only packet length, its results should be interpreted as a simple classroom demonstration.
