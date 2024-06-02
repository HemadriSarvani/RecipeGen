# RecipeGen
## NLP-Based Recipe Generation Model


**This project focuses on generating recipes using advanced Natural Language Processing (NLP) techniques.
We explored several models and methodologies to achieve high-quality recipe generation. 
Here, we document our approach, methodologies, and the models we utilized, leading to our final model.**


## Table of Contents
1. [Introduction](#introduction)
2. [Data Collection](#data-collection)
3. [Data Preprocessing](#data-preprocessing)
4. [Embedding Techniques](#embedding-techniques)
5. [Model Architectures](#model-architectures)
6. [Final Model](#final-model)
7. [Results](#results)
8. [Usage](#usage)
9. [Contributors](#contributors)
10. [Acknowledgements](#acknowledgements)

## Introduction

Deciding what to cook with the ingredients on hand can be a challenge. Traditional recipes and online searches may not offer solutions tailored to the specific ingredients you have, leading to food waste or repetitive meals.

We propose an NLP-based recipe generation model to solve this problem. This model will take a list of ingredients as input and generate diverse, contextually appropriate recipes. The goals are to:

    1. Maximize Ingredient Use: Minimize food waste by suggesting recipes that use available ingredients effectively.
    2. Enhance Cooking Experience: Inspire with new and exciting recipes, making cooking more enjoyable.
    
Using advanced NLP techniques, including T5, LSTM with GloVe embeddings, and GPT-2, this model will generate relevant and appealing recipes to transform the cooking experience into a creative and efficient process.

## Data Collection

We collected our dataset in two ways. 
We performed wescarping Kaggle due to its comprehensive information on Indian recipes. The Kaggle dataset provided a rich source of ingredients and cooking instructions that were essential for training our models.

## Data Preprocessing

To prepare the data for model training, we performed the following preprocessing steps:
1. Cleaned the dataset to remove any null or irrelevant entries.
2. Tokenized the text data for model compatibility.
3. Split the data into training and validation sets.

## Embedding Techniques

We explored two main embedding techniques to represent the text data:

1. **Word2Vec**: 
   - Utilized for capturing semantic similarities between words.
   - Achieved better performance in cosine similarity scoring compared to BERT.

2. **BERT**:
   - Used for its contextual word embeddings.
   - Although powerful, it did not perform as well as Word2Vec in our similarity scoring.

## Model Architectures

We experimented with the following model architectures:

1. **T5 (Text-to-Text Transfer Transformer)**:
   - Fine-tuned using attention mask sequences.
   - Trained for 10 epochs.
   - Results were promising but not optimal for our use case.

2. **LSTM (Long Short-Term Memory) with GloVe Embeddings**:
   - Implemented for recipe generation.
   - Trained for 500 epochs.
   - Results were not as expected, with generated recipes lacking coherence.

3. **GPT-2 (Generative Pre-trained Transformer 2)**:
   - Selected for its superior text generation capabilities.
   - Fine-tuned to generate recipes based on the provided dataset.

## Final Model

After evaluating the performance of different models, we selected GPT-2 as our final model for recipe generation. GPT-2's ability to generate coherent and contextually accurate recipes made it the best choice for this project.

## Results

GPT-2 demonstrated excellent performance in generating recipes that were both coherent and contextually relevant. The model successfully captured the nuances of Indian cuisine, providing detailed and accurate recipes.

## Usage

To use the recipe generation model, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/recipe-generation.git
   cd recipe-generation
