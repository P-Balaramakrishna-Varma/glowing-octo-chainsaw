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
