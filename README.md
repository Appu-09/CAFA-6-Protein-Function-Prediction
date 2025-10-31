🧬 CAFA 6 Protein Function Prediction

This project was developed for the CAFA 6 Kaggle competition — a community challenge to predict the biological functions of proteins using machine learning.
Proteins are essential molecules that drive nearly all biological processes. Understanding their functions helps in disease research, drug discovery, and molecular biology.

🎯 Objective

Predict the Gene Ontology (GO) terms for a given protein based on its amino acid sequence.
Each protein can have multiple functions, making this a multi-label classification problem.

📁 Dataset

The dataset is provided by CAFA 6 and includes:

train_sequences.fasta – protein amino acid sequences

train_terms.tsv – experimentally validated GO term annotations

train_taxonomy.tsv – species/taxon information

go-basic.obo – ontology structure of GO terms

testsuperset.fasta – test sequences for prediction

All files were obtained from Kaggle’s competition data portal.

⚙️ Approach

Data Preprocessing

Cleaned protein IDs and merged training files

Filtered top 200 most frequent GO terms

Encoded multi-label outputs using MultiLabelBinarizer

Feature Engineering

Extracted 3-mer (tri-peptide) features from protein sequences

Applied TF-IDF vectorization to convert them into 3000-dimensional numerical vectors

Model Training

Baseline: Logistic Regression (One-vs-Rest multi-label)

Improved Model: Random Forest trained on TF-IDF features

Evaluation

Metrics: Micro and Macro F1-scores

Best Validation Scores:

Micro F1 = 0.1651

Macro F1 = 0.0071

📊 Results

A submission file submission.tsv was generated containing:

Protein_ID    GO_ID       Score
P9WHI7        GO:0009274  0.931
P9WHI7        GO:0071944  0.540


Final Kaggle Public Leaderboard Score: 0.102
