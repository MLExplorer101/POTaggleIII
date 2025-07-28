# 📊 Earnings Call Transcript Summarization — Po Taggle III
Automated extraction and summarization of financial insights from earnings call transcripts.


## 🧠 Project Overview
This application processes earnings call transcripts to extract key financial information. It identifies participants, differentiates between Presentation and Q&A sections, and captures relevant financial sentences for structured output in both table and bullet-point formats.

## ✨ Features
* Named Entity Recognition (NER) powered by a fine-tuned Distilled BERT model with custom entities:

    * REPORTED VALUE

    * MULTIPLIER

    * CURRENCY

    * GRANULAR CONCEPT
   
    * UMBRELLA CONCEPT (dictionary-based NER approach) 

* Speaker and paragraph extraction

* Sentence segmentation using punctuation (. and ;)

* Presentation vs Q&A categorization

* Document generation in .docx format

* Financial table and summary bullet list generation

## 🧪 Model Training
Training was performed using spaCy and custom annotated datasets. See train_model.ipynb for the training pipeline.

Fine-tuned entities allow high-precision extraction of financial information from natural language.


## 📄 How It Works
    1. Parse transcript and identify participants (excluding Operator)

    2. Split transcript into sentences per speaker

    3. Run each sentence through the NER model

    4. Extract and validate sentences containing relevant financial entities

    5. Map Granular Concept to Umbrella Concept using dictionary (model-based classification planned)

    6. Export results to a .docx summary with:

    7. Financial Table

    8. Bullet-Point Summary

## 🧭 Caveats & Future Work
Umbrella Concept Mapping is currently static and rule-based.

Future enhancement: Build a classifier to dynamically infer Umbrella Concepts from Granular Concepts.

## 📚 Resources
Custom NER with spaCy v3 — Tutorial

## 📂 Files
| File  | Description |
| ------------- | ------------- |
| POTaggleIII_Antonio_Del_Trionfo.ipynb  | Main summarization notebook  |
| train_model.ipynb  | NER training pipeline |
| data/  | Annotated training data  |
| model/  | Fine-tuned spaCy model  |
| model/  | Generated .docx summaries  |


## 🚀 Usage
```bash
# Launch notebook
jupyter notebook POTaggleIII_Antonio_Del_Trionfo.ipynb
```
