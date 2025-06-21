# Aspect-Based Sentiment Analysis

## Project Overview

This project performs **Aspect-Based Sentiment Analysis (ABSA)** using **zero-shot** and **few-shot** learning with various **LLaMA models** on **SemEval datasets** (laptops and restaurants from 2014, 2015, and 2016).  
Performance is evaluated using **accuracy** and **F1-score**.

---

## Features

- **Data Preprocessing**: Converts XML SemEval datasets to CSV, extracting sentences, aspect terms, and sentiments.
- **Zero-Shot Analysis**: Direct sentiment prediction by LLaMA models.
- **Few-Shot Analysis**: Sentiment prediction enhanced with in-context examples.
- **Model Support**: Utilizes LLaMA-3-8b-Instruct, LLaMA-3-70b-Instruct, LLaMA-3.1-8b-Instruct, LLaMA-3.3-70b-Instruct via Hugging Face.
- **Evaluation**: Calculates accuracy and weighted F1-score.

---

## Data Preprocessing

XML data from SemEval (2014, 2015, 2016) is parsed into CSV files with the following columns:

- `sentence`
- `aspect_term`
- `sentiment`
- `from`
- `to`

The script automatically handles two XML structures: `<aspectTerms>` and `<Opinions>`.

---

## Sentiment Analysis

Two approaches are implemented:

- **Zero-Shot**: Models classify sentiment based on instruction and input.
- **Few-Shot**: Models classify sentiment with a few examples provided in the prompt.

Both methods use the **Hugging Face Inference Client** to interact with LLaMA models, using `temperature=0.0` for deterministic output.

---

## Evaluation Metrics

Model performance is assessed using:

- **Accuracy**: Percentage of correct predictions.
- **F1-Score (Weighted)**: Harmonic mean of precision and recall, weighted by class support.
