# Arabic-POS-NetworkX
# Arabic POS Tagging Project

## Overview
This project focuses on developing accurate Part-of-Speech (POS) tags for Arabic, a language known for its rich morphology and diverse syntactic structures. By utilizing a Bidirectional Long Short-Term Memory (BiLSTM) model, the project aims to capture contextual dependencies between words in sentences and predict POS tags with high accuracy. Additionally, the relationships between tokens and their respective POS tags are visualized using NetworkX.
![image](https://github.com/user-attachments/assets/428d17a1-e61e-4cb4-9298-7f1c0da933f6)

## Table of Contents
- [Introduction](#introduction)
- [Data Description](#data-description)
- [Preprocessing](#preprocessing)
- [Visualizing POS Tags with NetworkX](#visualizing-pos-tags-with-networkx)
- [Modeling](#modeling)
- [Model Results](#model-results)
- [Error Analysis](#error-analysis)
- [Conclusion](#conclusion)
- [Tools Used](#tools-used)

## Introduction
Part-of-Speech (POS) tagging is a vital task in natural language processing, where each word in a sentence is assigned a syntactic category (e.g., noun, verb, adjective). This project aims to accurately tag Arabic text by leveraging state-of-the-art machine learning techniques.

## Data Description
The dataset used in this project is **UD_Arabic-PADT** from the Universal Dependencies (UD) project. It provides syntactic and morphological analysis of Arabic texts and is organized in CoNLL format, which is effective for handling annotated linguistic data.

## Preprocessing
To ensure clean and consistent data, the following preprocessing steps were performed:
- **Remove Duplicates**: Eliminated redundant sentences.
- **Text Standardization**: 
  - Removed diacritical marks (Tashkeel).
  - Reduced excessive character elongations (e.g., "ووو" → "وو").
  - Unified Arabic characters (e.g., "أ", "إ", "آ" to "ا").

## Visualizing POS Tags with NetworkX
**NetworkX** is employed to visualize and analyze the relationships between tokens and their POS tags. 

### Graph Construction
- **Graph Type**: Directed graph (DiGraph) for sequential relationships.
- **Nodes**: Each token is represented as a node with its POS tag.
- **Edges**: Directed edges connect consecutive tokens.
![image](https://github.com/user-attachments/assets/2ef003f1-448b-4622-9634-f92ae0c24cde)


## Modeling
The project utilizes a **Bidirectional LSTM** model, well-suited for sequence labeling tasks.

### Data Preparation for Modeling
1. **Tokenization**: Unique IDs assigned to each word and POS tag.
2. **POS Tag Encoding**: Encoded and one-hot encoded for model input.
3. **Padding**: Sequences padded to ensure uniform input size.

### Model Architecture
- An embedding layer for dense vector representations.
- A BiLSTM layer for context awareness.
- A TimeDistributed dense layer for POS tag predictions.

## Model Results
The model achieved high accuracy across training, validation, and testing, with a training accuracy of **99.20%**.
![image](https://github.com/user-attachments/assets/d651f1fd-5be2-44d9-b8c3-d106a2d3b3a0)


## Error Analysis
![image](https://github.com/user-attachments/assets/28ee291e-c5b2-4a7c-a88f-8ea28f45ba9a)

Error analysis indicated that:
- **NOUN** was the most misclassified tag.
- **ADJ** (Adjective) and **X** (Unknown) tags showed notable misclassification rates.
- Tags like **NUM** (Number), **PUNCT** (Punctuation), and **AUX** (Auxiliary) had minimal misclassifications.

## Conclusion
This project demonstrates the effectiveness of BiLSTM models for POS tagging in Arabic, providing a strong foundation for future enhancements and adaptations to other NLP tasks.

## Libraries/Frameworks: 
  - Data Handling: `pandas`, `pyconll`
  - NLP: `spaCy`, `NLTK`, `arabic_reshaper`
  - Modeling: `TensorFlow`, `Keras`, `scikit-learn`
  - Visualization: `NetworkX`, `matplotlib`, `seaborn`
  - Additional: `numpy`, `re`

## Dataset: https://github.com/UniversalDependencies/UD_Arabic-PADT
