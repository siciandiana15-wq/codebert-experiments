# An Analysis of CodeBERT Generalization Power for Detecting AI-Generated Code Across Unseen Languages and Domains

This repository contains the experimental implementation developed for my study on detecting AI-generated code using Transformer-based architectures, with a particular focus on the CodeBERT model.

Recent advances in large language models (LLMs) have enabled the generation of source code that is both syntactically correct and semantically coherent. While these developments have significantly improved developer productivity, they also introduce challenges related to code authorship, transparency, and reliability. In particular, distinguishing between human-written and machine-generated code has become an important research problem.

In this work, I investigate the effectiveness of CodeBERT for the task of AI-generated code detection and analyze its ability to generalize across different programming languages and domains. My approach is based on a series of controlled experiments that explore multiple training strategies, including fine-tuning configurations, data augmentation techniques, and cross-language evaluation settings.

The results indicate that although the model achieves strong performance when the training and evaluation data follow similar distributions, its effectiveness decreases significantly under distribution shift. These findings highlight the importance of training data diversity and reveal limitations of current approaches in handling unseen languages and domains.
