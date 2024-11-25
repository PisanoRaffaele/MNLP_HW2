# 🎯 Adversarial NLI with Transformer-Based Models

This repository presents my project for the **Machine Learning for Natural Language Processing (MNLP)** course at **La Sapienza University**, focusing on the challenges of **Adversarial Natural Language Inference (NLI)**. The task demonstrates how **Large Language Models (LLMs)** like RoBERTa and DeBERTa can be fine-tuned and extended to handle adversarially constructed datasets, showcasing their adaptability and limitations in understanding semantics.

---

## 📝 Project Overview

### 📌 Why Adversarial NLI?
Natural Language Inference is a fundamental **NLP task** that evaluates whether a given **hypothesis** logically follows, contradicts, or is neutral with respect to a **premise**.  
This project pushes NLI models further by introducing **adversarial samples**—carefully crafted examples designed to challenge and "fool" models trained on standard NLI datasets. This exploration highlights how LLMs can handle nuanced and complex reasoning tasks when faced with adversarial examples.

---

## 🚀 Key Steps

### 1️⃣ Fine-Tuning a Baseline Model 
[Fine-Tuning Notebook](main.ipynb)
Using the **downsampled FEVER dataset**, I fine-tuned a **Transformer-based model** (DeBERTa) to perform standard NLI classification:
- **Input:** Premise and hypothesis pairs.
- **Output:** One of three classes:
  - **Entailment**
  - **Contradiction**
  - **Neutral**

This step establishes a baseline performance on traditional NLI data.

---

### 2️⃣ Adversarial Testing
[Adversarial Testing Notebook](main.ipynb)
After training, I evaluated the model on a provided **adversarial test set**, featuring:
- Hypotheses rephrased to increase ambiguity.
- Premises altered to subtly change their meaning.

This revealed how well the baseline model generalizes to more challenging, out-of-distribution examples.

---

### 3️⃣ Generating Adversarial Data
[Adversarial Data Generation Notebook](augment.ipynb).
To further improve robustness, I created **new adversarial training samples**:
- Focused on modifying **hypotheses** (shorter and easier to tweak).
- Leveraged semantic annotations, including:
  - **Word Sense Disambiguation (WSD)**
  - **Semantic Role Labeling (SRL)**

I ensured all modifications were **sound** (logically valid within the NLI framework) while significantly increasing their complexity.
All the modification specified in [Report](report.pdf)
---

### 4️⃣ Enhancing the Model with Semantics
[SRL embeddings](extra.ipynb).
To improve the model's reasoning capabilities, I extended the architecture by incorporating POS (Part-of-Speech) embeddings:

POS embeddings: These embeddings represent the syntactic roles of words in a sentence, helping the model capture grammatical structure and relationships between words more effectively.
---

### 5️⃣ Results
I trained the model with the full base dataset and half of the adversarial data to avoid overfitting. This approach led to significant improvements, especially on the adversarial test set, showing that combining base and adversarial data enhances the model's ability to handle complex cases.

---

## 💡An NLP Homework
This project lies at the intersection of **cutting-edge NLP research** and **real-world challenges**:
- It explores the **capabilities of LLMs** like DeBERTa, focusing on their fine-tuning and augmentation.
- It demonstrates the **power of semantics** (WSD, SRL) in improving model performance.
- It addresses the **robustness gap** in current NLI systems by generating and evaluating adversarial examples.

---

## 🔗 Key Insights
1. **LLMs Are Powerful But Not Invincible**: Transformers perform well on standard datasets but struggle with adversarial examples. 
2. **Semantics Matter**: Integrating WSD and SRL improved robustness, emphasizing the importance of external knowledge in NLP.
3. **Adversarial Training Is Essential**: Generating complex training data is crucial for building models capable of handling real-world variability.

---


## 🏛️ Academic Context
This project was completed as part of the **MNLP course** at **La Sapienza University**, demonstrating how advanced NLP techniques can address the challenges of adversarial reasoning tasks.

---

🎉 **Thank you for exploring my project! Feel free to dive into the code and experiment further.**
