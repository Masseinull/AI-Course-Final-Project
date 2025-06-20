# Persian Text Classification with Naive Bayes from Scratch

This project is a final assignment for an AI & Expert Systems course that demonstrates a text classification pipeline for Persian text. The core of this project is a **Naive Bayes classifier implemented from scratch** in Python, without relying on high-level libraries for the main algorithm.

The model is designed to categorize Persian text queries into one of five predefined labels. The notebook provides detailed markdown explanations that serve as the project report.

## Project Workflow

The entire process is contained within the `AI_FinalProject.ipynb` notebook and follows these steps:

1.  **Data Loading**: The process begins by loading the training data from `train.csv`.
2.  **Text Preprocessing**: A critical step for preparing Persian text for machine learning.
    * **Normalization**: Uses the `hazm` library's `Normalizer()` to standardize characters and spacing.
    * **Tokenization**: Splits sentences into words (tokens) using `hazm.word_tokenize`.
    * **Cleaning**: A custom `clean()` function removes punctuation, numbers, and common Persian stop words defined in a hardcoded list.
3.  **Modeling (Naive Bayes from Scratch)**:
    * The project implements a **Multinomial Naive Bayes** classifier manually in the `predict` function.
    * It uses **Laplace (add-one) smoothing** to handle words that appear in the test set but not in the training data for a specific class.
4.  **Evaluation with K-Fold**:
    * The model's performance is evaluated using a custom k-fold validation process.
    * The `k_fold` function in the notebook manually splits the data into three different training and testing sets to ensure the model's performance is robust across different data partitions.
    * The model's effectiveness is measured using precision, recall, F1-score, and overall accuracy.
5.  **Inference**:
    * The trained Naive Bayes model is used to predict labels for the unseen data in `inference.csv`.
    * The final predictions are exported to `result.csv`.

## Installation

1.  Clone the repository to your local machine:
    ```bash
    git clone https://github.com/Masseinull/AI-Course-Final-Project.git
    ```
2.  Navigate to the project directory:
    ```bash
    cd <your-project-directory>
    ```
3.  Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

To run the project:

1.  **Place the following files** in the same directory as the notebook:
    * `train.csv` (the labeled training data)
    * `inference.csv` (the unlabeled data for prediction)

2.  **Open and run the `AI_FinalProject.ipynb` notebook**. Executing all the cells will perform the entire workflow and generate a `result.csv` file containing the predictions.
