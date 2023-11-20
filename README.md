# Question_Answering_RNN
# Question Answering Model using GRU and Bilinear Similarity Layers

This repository contains code for a question-answering model implemented using a combination of GRU (Gated Recurrent Unit) layers and bilinear similarity layers. The model is designed to take paragraphs and questions as inputs and output the start and end positions of the answer within the paragraph.

## Model Architecture

The model architecture consists of the following major components:

- Word Embeddings: The words in the paragraphs and questions are embedded using the KerasLayer from TensorFlow Hub. These embeddings capture the semantic meaning of the words.

- GRU Layers: The embedded word representations are then passed through GRU layers to capture the contextual information and dependencies within the text.

- Weighted Question Representation: The model calculates the weighted average of the question embeddings to obtain a single vector representation. This representation is used in the subsequent bilinear similarity layer.

- Bilinear Similarity Layer: The bilinear similarity layer estimates the probabilities of each word in the paragraph being the start or end of the answer, based on the similarity between the question representation and each word's representation in the paragraph.

## Training and Evaluation

During training, the model is compiled with sparse categorical cross-entropy loss and sparse categorical accuracy metrics. A checkpoint is defined to save the weights of the best performing model.

The evaluation metrics used for model performance are:

- Exact Match (EM) Score: EM score measures the percentage of predicted answers that match exactly with the true answers.

- F1 Score: F1 score computes the harmonic mean of precision and recall of the predicted answers.

## Results

You can find the results of the model evaluation on the test set in the `results.txt` file. This file contains the Exact Match (EM) score and F1 score achieved by the model.


## License

This project is licensed under the [MIT License](LICENSE).

