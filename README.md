# RecipeGen
## NLP-Based Recipe Generation Model

**Welcome to RecipeGen! This project is all about generating recipes using advanced Natural Language Processing (NLP) techniques. We explored various models and methods to create recipe suggestions. Below, we document our approach, methodologies, and the models we used, leading up to our final selection.**

## Table of Contents
1. [Introduction](#introduction)
2. [Data Collection](#data-collection)
3. [Data Preprocessing](#data-preprocessing)
4. [Embedding Techniques](#embedding-techniques)
5. [Model Architectures](#model-architectures)
6. [Final Model](#final-model)
7. [Results](#results)
8. [Contributors](#contributors)
9. [Acknowledgements](#acknowledgements)


## Introduction

Have you ever struggled to decide what to cook with the ingredients you have at home? Traditional recipes and online searches often don't provide solutions tailored to the specific ingredients on hand, leading to food waste or repetitive meals.

We created RecipeGen, an NLP-based model, to solve this problem. Our model takes a list of ingredients and generates diverse, contextually appropriate recipes. Our goals are to:

1. **Maximize Compatibility**: Instead of trying to use all available ingredients, we create recipes with high compatibility scores.
2. **Enhance Cooking Experience**: Inspire you with new and exciting recipes, making cooking more enjoyable.


## Data Collection

We collected our dataset in two ways:
1. **Web Scraping**: We scraped recipes from foodstory.com website and stored them in a CSV file, with features like ingredients, instructions. 
2. **Kaggle Dataset**: We also used a comprehensive dataset from Kaggle, which provided rich information on Indian recipes, including ingredients and cooking instructions essential for training our models.

## Data Preprocessing

To prepare the data for model training, we:
1. Cleaned the dataset to remove any null or irrelevant entries.
2. Extracted only the features we needed and stored them in a new DataFrame.
3. Created a new column called 'Cleaned Ingredients', which standardized ingredient names, often converting regional names to their common equivalents.

## Embedding Techniques

We explored two main embedding techniques to represent the text data:

1. **Word2Vec**:
   - Captures semantic similarities between words.
   - Achieved better performance in cosine similarity scoring compared to BERT.

2. **BERT**:
   - Provides contextual word embeddings.
   - Although powerful, it did not perform as well as Word2Vec in our similarity scoring.

## Processing

1. **Finding Similarity score for the ingredients**:
   - Finding score for the embedings generated in the above step. 
   - Identifys compatable pairs that make the finaly recepie coherent.
   - Discarding the ingredient with low score to maintain balance of the dish.
  
     
## Model Architectures

We experimented with the following model architectures:

1. **LSTM (Long Short-Term Memory) with GloVe Embeddings**:
   - Implemented for recipe generation.
   - Trained for 500 epochs.
   - Results lacked coherence.

2. **T5 (Text-to-Text Transfer Transformer)**:
   - Fine-tuned using attention mask sequences.
   - Trained for 10 epochs.
   - Results were promising but not optimal.

3. **GPT-2 (Generative Pre-trained Transformer 2)**:
   - Selected for its superior text generation capabilities.
   - Fine-tuned to generate recipes based on the dataset.


## Final Model

After evaluating the performance of different models, we selected GPT-2 as our final model for recipe generation. GPT-2's ability to generate coherent and contextually accurate recipes made it the best choice for this project.

## Results

GPT-2 demonstrated excellent performance in generating recipes that were both coherent and contextually relevant. The model successfully captured the nuances of Indian cuisine, providing detailed and accurate recipes.


## Contributors

- **Greeshma Reddy**
  - **ID**: SE21UCSE067
  - **Contributions**: Model architecture design, fine-tuning models
  - **GitHub**: [Greeshma Reddy](https://github.com/Greesh-Reddy)

- **Sarvani Hemadri**
  - **ID**: SE21UCSE081
  - **Contributions**: Data preprocessing, embedding techniques, model experimentation
  - **GitHub**: [Sarvani Hemadri](https://github.com/HemadriSarvani)

- **Sathvika Pallamraju**
  - **ID**: SE21UCSE141
  - **Contributions**: Data collection, model training, evaluation
  - **GitHub**: [Sathvika Pallamraju](https://github.com/sathvikap12)

- **B Sri Vaishnavi**
  - **ID**: SE21UCSE038
  - **Contributions**: Implementation of recipe generation script, usage documentation
  - **GitHub**: [B Sri Vaishnavi](https://github.com/BSriVaishnavi)

## Acknowledgements 
1. [My Food Story](https://myfoodstory.com/)
2. [Cleaned_Indian_Dataset](https://www.kaggle.com/datasets/sooryaprakash12/cleaned-indian-recipes-dataset/code)
     
