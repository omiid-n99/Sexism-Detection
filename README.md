# Sexism Detection with Large Language Models (LLMs)

This repository contains the solution for **Assignment 2** of the NLP course. The project addresses the **EDOS Task B** (Explainable Detection of Online Sexism) using open-source Large Language Models (LLMs) through prompting techniques.

**Credits:** Federico Ruggeri, Eleonora Mancini, Paolo Torroni

## 👥 Authors
* **Omid Nejati**
* **Alireza Shahidiani**

## 📋 Project Overview

The goal of this project is to perform **multi-class classification** on textual data to detect and categorize sexism. Unlike traditional fine-tuning approaches, this assignment explores the capabilities of pre-trained LLMs using **Zero-Shot** and **Few-Shot** prompting strategies.

### Task:
Given an input sentence, the model must classify it into one of the following 5 categories:
1.  **Not Sexist**
2.  **Threats** (Intent or desire to harm)
3.  **Derogation** (Derogatory description)
4.  **Animosity** (Slurs or insults)
5.  **Prejudiced Discussion** (Support for mistreatment/stereotypes)

##  Methodology

The project is structured into several tasks:

1.  **Model Setup**: Loading models from the Hugging Face Hub using 8-bit quantization (`bitsandbytes`) to fit within GPU memory constraints.
2.  **Prompt Engineering**: Designing structured system and user prompts to instruct the LLM on the definitions of the sexist categories.
3.  **Inference**:
    * **Zero-Shot**: Asking the model to classify text without seeing examples.
    * **Few-Shot**: Providing balanced demonstration examples (2 per class) in the context window to improve performance.
4.  **Evaluation**: Computing metrics (Accuracy, Macro F1-Score) and generating confusion matrices.

   
**Prompting Strategies Explored**:
   * Zero-Shot Inference: The models are provided with the category definitions and the input text, forcing them to rely solely on their pre-trained knowledge to classify the content.
   * Few-Shot Inference: The prompts are dynamically augmented with balanced demonstration examples (2 per class) to guide the model's reasoning and output formatting.
### Models Evaluated
The following open-source models were implemented and tested in this notebook:
* **Microsoft Phi-3-mini-4k-instruct**
* **Mistral-7B-Instruct-v0.3**

##  Dataset

The project uses a subset of the EDOS dataset provided by the course instructors:
* `a2_test.csv`: Test set (300 balanced samples).
* `demonstrations.csv`: Pool of examples used for few-shot prompting.

## Observations
* Mistral-7B demonstrated a significant performance boost (~10% accuracy increase) when transitioning from Zero-Shot to Few-Shot prompting, indicating strong in-context learning abilities.

* Phi-3-mini showed impressive baseline performance for its size in Zero-Shot scenarios but benefited less from the specific few-shot examples provided, suggesting a different sensitivity to prompt context.

## Project Structure
The notebook nlp2.ipynb is organized into the following tasks:
* Task 1: Model Setup - Downloads and loads quantized models (Phi-3 & Mistral-7B).

* Task 2: Prompt Setup - Defines templates for instructing the LLMs.

* Task 3: Zero-Shot Inference - Runs the models on test data without examples.

* Task 4: Metrics - Parses responses and computes Accuracy and F1-Score.

* Task 5: Few-Shot Inference - Builds prompts with dynamic examples and re-evaluates models.

* Task 6: Error Analysis - Generates confusion matrices and summarizes model behaviors.

* Task 7: Report - Guidelines for summarizing the experiment.


## Academic Context
This project was developed as part of the Natural Language Processing (NLP) course.
* Instructors/Credits: Federico Ruggeri, Eleonora Mancini, Paolo Torroni.
* Dataset Source: A subset of the official EDOS dataset (SemEval-2023 Task 10)

## License
This project is created for academic purposes. The dataset and task definition are based on the EDOS Challenge.








