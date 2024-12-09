#Zero-Shot and Attention-Based Offensive Language Detection with Differential Privacy-Enhanced Word Replacement System
This repository provides the implementation and details of our research on Zero-Shot and Attention-Based Offensive and Inappropriate Language Detection combined with a Differential Privacy-Enhanced Word Replacement System.

Abstract
With the widespread adoption of social media, individuals are increasingly exposed to inappropriate language, such as offensive expressions and hate speech. This not only disrupts communication but also causes psychological harm. To address these issues, we propose a novel system that:

Utilizes Zero-shot learning to classify harmful sentences into fine-grained categories.
Detects offensive keywords using an Attention mechanism.
Replaces harmful words with contextually appropriate alternatives while ensuring randomness and privacy through Differential Privacy (DP).
Our approach preserves contextual integrity while mitigating harmful content, promoting safer and more inclusive online communication environments.

Key Features
Fine-Grained Harmfulness Classification:

Classifies sentences into six toxicity categories:
Toxic
Severe Toxic
Obscene
Threat
Insult
Identity Hate
Attention-Based Important Word Detection:

Identifies key offensive words using attention mechanisms from transformer models (e.g., RoBERTa, BERT).
Focuses on core contributors to sentence harmfulness.
Differential Privacy-Enhanced Neutralization:

Applies Differential Privacy to introduce randomness during word replacement, enhancing privacy and unpredictability.
Utilizes GloVe embeddings to identify contextually similar and neutral substitutes.
Scalable and Flexible Framework:

Incorporates Zero-shot learning for adaptability to new categories without additional training.
Minimizes the need for extensive labeled datasets.
System Architecture
1. Sentence-Level Labeling
Input: Sentences from the Kaggle Toxic Comment Classification dataset.
Process: Classifies sentences into predefined labels using Zero-shot learning.
Output: Sentences labeled as one of the six toxicity categories.
2. Important Word Detection
Input: Harmful sentences identified in the previous step.
Process:
Extracts attention scores from transformer models to detect offensive words.
Penalizes stopwords using SpaCy's stopword list and prioritizes explicitly harmful terms.
Output: List of offensive words contributing to the sentence's harmfulness.
3. Neutralization
Input: Offensive words identified in the previous step.
Process:
Generates semantically similar substitutes using GloVe embeddings.
Applies Differential Privacy to select replacements.
Re-evaluates modified sentences to ensure reduced harmfulness.
Output: Contextually neutralized sentences or masked sentences for unresolved cases.
Dataset
We use the Kaggle Toxic Comment Classification Challenge dataset, consisting of over 150,000 labeled text samples categorized into six toxicity types. This dataset enables comprehensive testing of both detection and neutralization capabilities.

Evaluation Metrics
Detection Accuracy:
Precision, Recall, F1-score.
Contextual Preservation:
Cosine similarity and BLEU score between original and modified sentences.
Neutralization Success Rate:
Percentage of harmful sentences successfully neutralized.
Results
High detection accuracy for harmful sentences using Zero-shot learning.
Effective neutralization of offensive words while preserving contextual meaning.
Robustness ensured through Differential Privacy, balancing privacy and contextual utility.
Limitations and Future Work
Current Limitations:
Subtle grammatical inconsistencies introduced during substitution.
Cultural nuances in offensive language require further exploration.
Future Directions:
Extending the system for multilingual detection and replacement.
Deploying the framework for real-time applications in dynamic environments like social media and chat systems.
Citation
If you find this work helpful, please cite:

sql
코드 복사
@article{seo2024zero-shot,
  title={Zero-Shot and Attention-Based Offensive Language Detection with Differential Privacy-Enhanced Word Replacement System},
  author={Seo, Jihee and Baek, Soyeon and Kim, Hanna and Hwang, Jihye and Zhu, Xiuyan},
  journal={Ewha Womans University Research Initiative},
  year={2024}
}
Contact
For further inquiries, please contact:

Jihee Seo: jiheeseo@ewhain.net
Soyeon Baek: soyeonbaek@ewhain.net
Hanna Kim: 241bag156@ewha.ac.kr
Jihye Hwang: jihh1745@ewha.ac.kr
Xiuyan Zhu: xiuyan.zhu@ewha.ac.kr
