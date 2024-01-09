## Problem statement
- Classify the medical specialties based on the transcription text.  
- The assignment mentions it is Multi Label Classification, that is each transcription can have multiple specialties.   

## Dataset
- The dataset has the following fields discription, medical_specialty, sample_name, transcription, keywords.    
- But we have to only use the transcription and medical_specialty fields for classifiction.   
- Though the problem set is multi-label classification, the dataset has only one label for each transcription.
- There are only 4999 samples in the dataset. We use 1000 samples for test/validation and 3999 for training.
- The samples distribution across the classes is not unifrom. The dataset is imbalanced. Refer to the python notebook for more details.
- Data processing is done by using the hugging face bert tokenizer.


## Solution Outline
- **Iteration 1**: Implementing the standard approach for this dataset.
- **Iteration 2**: Using avarage of word embeddings and modeling as ordinary multi-class classification problem.
- **Performance Understanding**: Understanding the bottleneck in the performance of the model.
- **Iteration 3**: Making the nueral network more numerically stable.


## Iteration 1
- Standard Approach for Multi-Label sequence classification [Notebook](https://colab.research.google.com/github/abhimishra91/transformers-tutorials/blob/master/transformers_multi_label_classification.ipynb#scrollTo=n5vcDWvgK6o8).
- Use bert to generate a sentence embedding and then use a linear layer to classify the sentence embedding.
- Implement the same notebook but for our dataset.
- Accuracy achieved: 19%

## Iteration 2
- Since our dataset is essentially a ordinary classification, we can use cross entropy loss and softmax instead of binary cross entropy and sigmoid.
- One mistake done was to use the sentence embedding instead of avarage of word embeddings. [incorrect interpretation of docs] 
- Accuracy achived: 34.5%


## Performance Understanding
- When replace the generation of sentence embedding with with a vector of all 1s, the accuracy is 22-24%.
- When we increase the complexity of classification head by adding more layers, the accuracy is almost the same.
- This means that classification head is not the bottleneck but the sentence embedding is.



## Iteration 3


## Improvement scope
- Creating a bigger and more balanced dataset.
- Using a better pretained model to generate a better sentence embedding.