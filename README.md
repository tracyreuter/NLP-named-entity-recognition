# NLP Named Entity Recognition (NER) Demo

## Overview

This project demonstrates how **Named Entity Recognition (NER)** works in Natural Language Processing (NLP). NER algorithms identify and classify named entities in text into predefined categories. NER has a wide variety of use cases, such as: search/content recommendation, knowledge graph construction, and redacting text. This demo uses **spaCy**, a leading open-source library for advanced NLP, which provides pre-trained models for entity recognition.

### Key Concepts

- **Named Entity**: A real-world object with a proper name (e.g., "Michael Jordan", "April 15", "First Amendment")
- **Entity Type**: The category of the entity (in this demo: PERSON, DATE, or LAW)
- **NER Model**: A machine learning model trained to identify and classify entities in text
- **spaCy**: An open-source NLP library with pre-trained models for multiple languages

## Dataset

This demo uses the **20 Newsgroups dataset**, a publicly available corpus of ~20,000 newsgroup documents across 20 different categories. For consistency with my NLP Topic Modeling demo, this demo uses 3 categories:

- `rec.sport.baseball` - Baseball discussions
- `talk.politics.guns` - Gun politics debates
- `sci.space` - Space exploration and astronomy

## Method

### Step 1: Load Data

- Import libraries including spaCy for NER
- Load the sklearn 20 Newsgroups dataset
- Remove headers, footers, and quotes for cleaner text

### Step 2: Load spaCy Model

- Load spaCy's pre-trained English model (`en_core_web_sm`)
- This model was trained on OntoNotes 5 corpus and recognizes multiple entity types
- For simplicity and clarity, this demo focuses on three entity types:
  - **PERSON**: People, including fictional characters
  - **DATE**: Absolute or relative dates or periods
  - **LAW**: Named laws, legal documents, or legal references

### Step 3: Perform Named Entity Recognition

- Process documents through the spaCy NER pipeline
- Extract all recognized entities with their types
- Store results in a DataFrame for analysis

**Note:** Processing is limited to a subset of documents because NER is computationally intensive.

### Step 4: Examine Entity Distributions

- Analyze the distribution of the three entity types (PERSON, DATE, LAW) across the corpus
- Show the most frequently occurring entities for each type

**Note:** SpaCy seems to confuse some PERSON entities in this corpus. Is "Moon" being treated like a fictional characters? Would this still happen if other entity types were included?

### Step 5: Visualize and Analyze Entity Distributions

- Visualization shows patterns in entity types across different categories in the corpus.
- For example (as you might reasonably expect!) LAW entities are more common in the political debates than in the baseball category.
