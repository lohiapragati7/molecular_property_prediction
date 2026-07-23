MOLECULAR PROPERTY PREDICTION USING GRAPH NEURAL NETWORKS



\## Overview



This project explores the use of Graph Neural Networks (GNNs) for molecular property prediction. Traditional machine learning models often struggle to capture the complex relationships present in molecular structures. By representing molecules as graphs, Graph Neural Networks can directly learn from atomic interactions and chemical bond connectivity.



The project was developed as part of the **'OpenAImer Hackathon, Track A'**, where the objective was to predict multiple molecular properties from molecular graph data.



\-----



\## Problem Statement



Molecules are naturally structured as graphs:



\- **Atoms** → Nodes

\- **Chemical Bonds** → Edges



The goal is to learn meaningful graph representations of molecules and use them to predict multiple molecular properties simultaneously.



This project tackles the problem as a **multi-label classification task**, where a single molecule can be associated with multiple target properties.



\-----



\## Dataset



The dataset consists of molecular information along with corresponding molecular property labels.



\- train.csv

\- test.csv

\- sample\_submission.csv



The data is transformed into graph representations before being passed to the Graph Neural Network.



\-----



\## Key Concepts



A graph is a data structure consisting of:



\- Nodes (vertices)

\- Edges (connections)



Graph Neural Networks(GNNs) are deep learning models designed specifically for graph-structured data.



Unlike traditional neural networks, GNNs learn from:



\- Node features

\- Graph connectivity

\- Neighbor relationships



This makes them highly effective for molecular modeling, social networks, recommendation systems, and knowledge graphs.



\---



\### Atomic Features



Each atom is represented using a set of node-level features extracted from the molecular structure.



Examples of atomic features include:



\- Atomic Number

\- Degree (number of bonded neighbors)

\- Formal Charge

\- Hybridization State

\- Aromaticity

\- Number of Attached Hydrogens



These features provide chemical information that helps the model learn meaningful molecular representations.



\---



\### SMILES Notation



Molecules in the dataset are represented using **SMILES (Simplified Molecular Input Line Entry System)**, a text-based format that encodes molecular structures as character sequences.



Example: CCO represents Ethanol.



SMILES provides a compact way to describe molecular structures and serves as the starting point for graph construction.



\---



\### Molecular Graph Representation



Each molecule is converted into a graph where:



| Molecular Component | Graph Component |

|---------------------|-----------------|

| Atom                | Node            |

| Bond                | Edge            |

| Atomic Properties   | Node Features   |



This representation allows the model to learn structural information directly from molecular interactions.



\---



\### Message Passing



A core idea behind GNNs is **message passing**.



Each node gathers information from its neighboring nodes and updates its representation.



This process enables the model to learn both:



\- Local atomic interactions

\- Global molecular structure



\-----



\## Model Architecture



The model follows the workflow shown below:



Molecular Dataset

&#x20;       ↓

Graph Construction

&#x20;       ↓

Node Feature Encoding

&#x20;       ↓

Graph Neural Network Layer 1

&#x20;       ↓

Graph Neural Network Layer 2

&#x20;       ↓

Global Mean Pooling

&#x20;       ↓

Fully Connected Layer

&#x20;       ↓

Multi-Label Predictions (P1–P5)

&#x20;       ↓

MCC Evaluation



\-----



**Components Used**



\- Molecular Graph Construction

\- Node Feature Encoding

\- Graph Neural Network Layers

\- Global Mean Pooling

\- Fully Connected Classification Head



\-----



\## Training Techniques



The model is trained and optimised using:



1. BCEWithLogitsLoss - This loss function is commonly used for multi-label classification tasks because each target property is predicted independently.



2\. Adam Optimizer - The Adam optimizer was used to update model parameters during training.



Advantages:

\- Faster convergence

\- Adaptive learning rates

\- Widely used in deep learning applications



3\. Global Mean Pooling - After learning node-level representations, the node embeddings are aggregated into a single graph-level embedding.

&#x20;                        This graph embedding summarizes the entire molecule and is used for final prediction.



\-----



\## Evaluation Metric



**### Matthews Correlation Coefficient (MCC)**



The model is evaluated using the Matthews Correlation Coefficient (MCC).



Unlike simple accuracy, MCC considers:



\- True Positives

\- True Negatives

\- False Positives

\- False Negatives



making it a more reliable metric for imbalanced classification problems.



\### **MCC Range**



| MCC Value | Meaning               |

|-----------|-----------------------|

| +1        | Perfect Prediction    |

| 0         | Random Prediction     |

| -1        | Complete Disagreement |



\-----



\## Results



\### Property-wise MCC Scores



| Property  | MCC Score |

|-----------|-----------|

| P1        | 0.5156    |

| P2        | 0.4132    |

| P3        | 0.3541    |

| P4        | 0.2948    |

| P5        | 0.4202    |



\### Final Performance



**Average MCC = 0.3996**



The model achieved positive MCC scores across all molecular properties, indicating successful learning of meaningful molecular graph representations.



\-----



\## Visualizations



&#x20;- Model Architecture



&#x20;- Molecular Graph Example



&#x20;- Training Loss



&#x20;- MCC Performance



\-----



\## Key Learnings



Through this project, I gained exposure to:



\- Graph-based machine learning

\- Molecular data representation

\- Graph Neural Networks

\- Multi-label classification

\- Scientific AI applications

\- Model evaluation using MCC

\- PyTorch Geometric workflows

\- End-to-end machine learning experimentation



\-----



**Tech Stack**



\### Languages



\- Python



\### Libraries



\- PyTorch

\- PyTorch Geometric

\- NumPy

\- Pandas

\- Scikit-learn

\- Matplotlib



\### Tools



\- Google Colab

\- Git

\- GitHub



\-----



\## Conclusion



This project demonstrates how molecular structures can be transformed into graph representations and analyzed using Graph Neural Networks for molecular property prediction.



By leveraging graph-based learning techniques, the model was able to learn meaningful structural patterns from molecular data and achieve an average MCC score of **0.3996** across five target properties.



Beyond the final score, this project provided valuable experience in graph machine learning, molecular representation learning, deep learning workflows, and scientific AI applications.



\-----------------------------------------------------------------------------------------------------------------



Developed for the **OpenAImer Molecular Property Prediction Challenge**.



\-----------------------------------------------------------------------------------------------------------------

