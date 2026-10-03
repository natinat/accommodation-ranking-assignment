# Accommodation-ranking-assignment
A machine learning assignment that is part of an AI learning module in the online university of Essex.

## Assignment Topic: Comparative Intelligence and Ethics in Machine Learning Systems
### The assignment places particular emphasis on:
- Trade-offs between classical ML and DL approaches.
- Model evaluation and validation.
- Explainability and interpretability of models.
- Ethical implications and bias.
- Considerations for real-world deployment

## Repository content:

### `Trivago_Recommender_System_Assignment_EDA.ipynb`
Performs exploratory data analysis and initial feature engineering. This
includes construction of ranking events and candidate sets, association of
preceding session behaviour with ranking events, and creation of features such
as relative price and filter-property matching. The notebook produces the
intermediate datasets required by the preprocessing notebook.

### `Trivago_Recommender_System_Preprocessing.ipynb`
Uses the datasets produced during EDA to construct the final modelling
features, including preceding session-behaviour features. It creates
session-level training, validation and test splits and prepares the final
datasets used for modelling.

### `Trivago_Recommender_System_Modelling.ipynb`
Implements and evaluates the classical and deep-learning models, performs
hyperparameter tuning, final test evaluation, explainability analysis and
the destination-representation subgroup diagnostic.Large datasets and generated model checkpoints are not included in the
repository. These files are created locally when the notebooks are run.

# Run Instructions:
Before executing the files, you need to download the original Trivago datasets:
1. Train
2. Test
3. Metadata

These can be found here: https://www.kaggle.com/datasets/pranavmahajan725/trivagorecsyschallengedata2019

After that, notebooks should be executed in the following order:

1. `Trivago_Recommender_System_Assignment_EDA.ipynb`
2. `Trivago_Recommender_System_Preprocessing.ipynb`
3. `Trivago_Recommender_System_Modelling.ipynb`

The EDA notebook performs both exploratory analysis and initial feature
engineering and generates intermediate datasets required by the preprocessing
notebook.

The preprocessing notebook subsequently generates:

- `train_preprocessed.parquet`
- `val_preprocessed.parquet`
- `test_preprocessed.parquet`

These three files are then used by the modelling notebook.
There are also checkpoints within the modelling file, which can save you re-running expensive runs, such as deep learning model training and evaluation.

Checkpoints that generate files across these 3 notebooks, will generate them in the same project directory.
Recommending using GPU for the deep learning models (MLP and Wide & Deep).

