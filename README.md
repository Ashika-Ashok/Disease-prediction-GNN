-------------------------------------Graph Based Disease Prediction System------------------------------------------------

This project compares traditional Machine Learning models and Graph Neural Networks (GCN, GraphSAGE, GAT) for disease prediction under noisy data conditions. 
It demonstrates how GNNs remain robust while ML models degrade, making graph-based approaches more reliable for real-world diagnosis.

Dataset overview
----------------------------------------------------------------------------------
Source: Kaggle – Disease Prediction Using Machine Learning by KAUSHIL268
File Format: CSV (Comma-Separated Values)
File Size: Approximately 30 KB
Number of Samples: The dataset comprises 132 parameters, enabling the prediction of 42 different diseases.
https://www.kaggle.com/datasets/kaushil268/disease-prediction-using-machine-learning

Project Workflow
-----------------------------------------------------------------------------------------------------------
🔹 Step 1: Classical ML Models
Load training and test dataset (training_data.csv, test_data.csv).

Train ML classifiers:
Logistic Regression
Random Forest
Decision Tree
KNN
SVM
MLP (Neural Net)
Evaluate Accuracy, Precision, Recall, F1.

Inject 10–30% feature noise → retrain & re-evaluate.
Plot metric degradation curves.

🔹 Step 2: Graph Construction & GNNs
Build bipartite graph (Patients ↔ Symptoms).
Project to Patient–Patient similarity graph.
Reduce feature space with SVD embeddings.

Train GNN models:
GCN (Graph Convolutional Network)
GraphSAGE
GAT (Graph Attention Network)
Evaluate on both clean and noisy features.

🔹 Step 3: Graph Enhancements
Apply graph sparsification (top-k neighbors).
Compare different GNNs for robustness.
Show how GNNs outperform ML under noise.

📊 Key Findings

✅ ML Models work perfectly on clean data but collapse as noise increases (Decision Tree, KNN degrade fastest).

✅ GNNs remain highly accurate even under 20–30% noise, thanks to graph neighborhood aggregation.

✅ Graph sparsification and weighted edges further enhance robustness.

🏆 Why GNNs Win
ML models treat each feature independently → noise flips directly mislead predictions.

GNNs leverage graph connectivity:
Patients are linked by symptom similarity.
Even if some features are noisy, neighbors provide corrective context.
Graph convolution smooths noise → more stable predictions.
Thus, GNNs act as a noise filter and achieve state-of-the-art robustness in diagnosis tasks.

 How This is Helpful
In real-world medical datasets, noise is unavoidable (human error, missing values, incorrect symptom reports).
This framework shows that Graph Neural Networks are more reliable than traditional ML when data is imperfect.

Applications:
Clinical decision support systems.
Noise-resilient patient similarity networks.
Symptom-based disease prediction under uncertainty.
