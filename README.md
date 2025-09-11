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
Load training and test dataset (training_data.csv, test_data.csv).<br>

Train ML classifiers:<br>
Logistic Regression<br>
Random Forest<br>
Decision Tree<br>
KNN<br>
SVM<br>
MLP (Neural Net)<br>
Evaluate Accuracy, Precision, Recall, F1.<br>

Inject 10–30% feature noise → retrain & re-evaluate.<br>
Plot metric degradation curves.<br>

🔹 Step 2: Graph Construction & GNNs
Build bipartite graph (Patients ↔ Symptoms).
Project to Patient–Patient similarity graph.
Reduce feature space with SVD embeddings.

Train GNN models:
GCN (Graph Convolutional Network)<br>
GraphSAGE<br>
GAT (Graph Attention Network)<br>
Evaluate on both clean and noisy features.<br>

🔹 Step 3: Graph Enhancements<br>
Apply graph sparsification (top-k neighbors).<br>
Compare different GNNs for robustness.<br>
Show how GNNs outperform ML under noise.<br>

📊 Key Findings

✅ ML Models work perfectly on clean data but collapse as noise increases (Decision Tree, KNN degrade fastest).<br>

✅ GNNs remain highly accurate even under 20–30% noise, thanks to graph neighborhood aggregation.<br>

✅ Graph sparsification and weighted edges further enhance robustness.<br>

🏆 Why GNNs Win<br>
ML models treat each feature independently → noise flips directly mislead predictions.<br>
<br>
GNNs leverage graph connectivity:<br>
Patients are linked by symptom similarity.<br>
Even if some features are noisy, neighbors provide corrective context.<br>
Graph convolution smooths noise → more stable predictions.<br>
Thus, GNNs act as a noise filter and achieve state-of-the-art robustness in diagnosis tasks.<br>

 How This is Helpful
In real-world medical datasets, noise is unavoidable (human error, missing values, incorrect symptom reports).
This framework shows that Graph Neural Networks are more reliable than traditional ML when data is imperfect.
<br>
Applications:
Clinical decision support systems.
Noise-resilient patient similarity networks.
Symptom-based disease prediction under uncertainty.
