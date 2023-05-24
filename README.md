# CAFA-5-Protein-Function-Prediction
This is my code repository for the kaggle competition https://www.kaggle.com/competitions/cafa-5-protein-function-prediction. In this compettition, I take the task to predict the function of a protein given its DNA sequence. In context, the function of a protein is represented by its Gene Ontology anotation (a multi-label with nearly 40000 non-exclusive targets), while a DNA sequence is given in fasta format. 

# Models
Due to the large number of non-exclusive targets in this multi-label classification problem, it is infeasible to implement any one-vs-all strategy which build a binary classifier for each class. This leaves neural network as a reasonable choice of initial approach. My initial model consists of two layers of CNN follows by one Dense layers with sigmoid activation for classification. 

# Challenges
In my initial approach, each sequence is one-hot-encoded as an array with shape (sequence_length,27) which the CNN then process. One-hot-encoding all training data costs 50 GB of ram which my labtop doesn't have. As a resolution, I wrote a data generator which generates batches of encoded data during the training sessions to avoid overwhelming the ram.

# Current Result (Updated 05/24/2023)
The current result has a validation AUC of 0.86 which corresponds to a kaggle score of 0.25. This is my initial working model without parameter tuning and transfer learning.

# Future Work
Protein sequence embeding (transfer learning) and parameter tuning are on my plan to improve the current result.
