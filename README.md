# NLP Named Entity Recognition (NER) Demo

## Overview

This project demonstrates how **Named Entity Recognition (NER)** works in Natural Language Processing (NLP). NER algorithms identify and classify named entities in text into predefined categories such as persons, organizations, locations, dates, and more. This demo uses **spaCy**, a leading open-source library for advanced NLP, which provides pre-trained models for entity recognition.

### Key Concepts

- **Named Entity**: A real-world object with a proper name (e.g., "NASA", "New York", "January 2026")
- **Entity Type**: The category of the entity (e.g., PERSON, ORG, GPE, DATE)
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
- This model was trained on OntoNotes 5 corpus and recognizes multiple entity types including:
  - **PERSON**: People, including fictional characters
  - **ORG**: Organizations, companies, agencies, institutions
  - **GPE**: Geopolitical entities (countries, cities, states)
  - **DATE**: Absolute or relative dates or periods
  - **MONEY**: Monetary values
  - **CARDINAL**: Numerals that do not fall under another type
  - And many more

### Step 3: Perform Named Entity Recognition

- Process documents through the spaCy NER pipeline
- Extract all recognized entities with their types
- Store results in a DataFrame for analysis

**Note:** Processing is limited to a subset of documents for performance reasons, as NER is computationally intensive compared to simpler text processing tasks.

### Step 4: Examine Entity Distributions

- Analyze the distribution of different entity types across the corpus
- Show the most frequently occurring entities for each type
- Some entity types appear more frequently depending on the topic (e.g., more PERSON entities in sports discussions, more ORG entities in political debates)

### Step 5: Visualize Entity Distributions

- Create a bar chart showing the overall distribution of entity types
- Create a heatmap showing how entity types are distributed across different documents
- Visualization reveals patterns in entity usage across different topics

## Common Entity Types in OntoNotes

- **PERSON**: Barack Obama, Michael Jordan, Einstein
- **ORG**: NASA, Microsoft, United Nations
- **GPE**: United States, California, New York, Earth
- **DATE**: Monday, last year, 1995, next week
- **TIME**: 3 PM, morning, midnight
- **MONEY**: $100, fifty dollars, 20 euros
- **CARDINAL**: one, two, 25, thousands
- **ORDINAL**: first, second, 1st, 2nd
- **PERCENT**: 50%, twenty percent
- **QUANTITY**: 100 miles, 5 kilograms

## Requirements

```bash
pip install spacy numpy pandas plotnine scikit-learn
python -m spacy download en_core_web_sm
```

## Applications

Named Entity Recognition is used in:

- **Information Extraction**: Automatically extracting structured information from unstructured text
- **Question Answering**: Identifying entities to answer "who", "where", "when" questions
- **Content Recommendation**: Understanding what entities a user is interested in
- **Search Enhancement**: Improving search by recognizing entity queries
- **Knowledge Graph Construction**: Building databases of entities and their relationships
- **Text Anonymization**: Identifying and redacting personal information
