# NLP Named Entity Recognition (NER) Demo

## Overview

This project demonstrates how **Named Entity Recognition (NER)** works in Natural Language Processing (NLP). NER algorithms identify and classify named entities in text into predefined categories. This demo uses **spaCy**, a leading open-source library for advanced NLP, which provides pre-trained models for entity recognition.

### Key Concepts

- **Named Entity**: A real-world object with a proper name (e.g., "Michael Jordan", "April 15", "First Amendment")
- **Entity Type**: The category of the entity (in this demo: PERSON, DATE, or LAW)
- **NER Model**: A machine learning model trained to identify and classify entities in text
- **spaCy**: An industrial-strength NLP library with pre-trained models for multiple languages

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
- Entity patterns vary by topic: sports discussions contain more PERSON entities (athletes, teams), while political debates reference more LAW entities (legislation, acts, amendments)

### Step 5: Visualize Entity Distributions

- Create a bar chart showing the overall distribution of the three entity types
- Create a heatmap showing how PERSON, DATE, and LAW entities are distributed across different documents
- Visualization reveals patterns in entity usage across different topics

## Applications

Named Entity Recognition is used in:

- **Information Extraction**: Automatically extracting structured information from unstructured text
- **Question Answering**: Identifying entities to answer "who", "where", "when" questions
- **Content Recommendation**: Understanding what entities a user is interested in
- **Search Enhancement**: Improving search by recognizing entity queries
- **Knowledge Graph Construction**: Building databases of entities and their relationships
- **Text Anonymization**: Identifying and redacting personal information
