# An Analysis of CodeBERT Generalization Power for Detecting AI-Generated Code Across Unseen Languages and Domains

This repository contains the experimental implementation developed for my study on detecting AI-generated code using Transformer-based architectures, with a particular focus on the CodeBERT model.

Recent advances in large language models (LLMs) have enabled the generation of source code that is both syntactically correct and semantically coherent. While these developments have significantly improved developer productivity, they also introduce challenges related to code authorship, transparency, and reliability. In particular, distinguishing between human-written and machine-generated code has become an important research problem.

In this work, I investigate the effectiveness of CodeBERT for the task of AI-generated code detection and analyze its ability to generalize across different programming languages and domains. My approach is based on a series of controlled experiments that explore multiple training strategies, including fine-tuning configurations, data augmentation techniques, and cross-language evaluation settings.

The results indicate that although the model achieves strong performance when the training and evaluation data follow similar distributions, its effectiveness decreases significantly under distribution shift. These findings highlight the importance of training data diversity and reveal limitations of current approaches in handling unseen languages and domains.

## 🧪 Experiments

The repository is organized as a collection of experiments, each corresponding to a specific training strategy or evaluation setting described in the paper.

- **exp1 – Frozen BERT Baseline**  
  I evaluate a baseline where BERT is used as a fixed feature extractor without fine-tuning.

- **exp2 – Partial Fine-Tuning**  
  I fine-tune only the last Transformer layers, significantly improving performance.

- **exp3 – CodeBERT Fine-Tuning and LLM Comparison**  
  I fully fine-tune CodeBERT and compare it with generative models.

- **exp4 – Cross-Language Generalization**  
  I analyze knowledge transfer across programming languages.

- **exp5 – Language Rotation Strategy**  
  I investigate multi-language training for improved transfer.

- **exp6 – Synthetic Data Augmentation**  
  I introduce synthetic samples to increase training diversity.

- **exp7 – Domain Shift with GRL Augmentation**  
  I study robustness under domain shift using adversarial training.

- **exp8 – Large-Scale Domain Shift Training**  
  I extend the setup with large-scale augmentation and regularization.

  ## ▶️ How to Run

All experiments are implemented as Jupyter notebooks and were developed and executed in **Google Colab**.

### Running in Google Colab (recommended)

1. Open https://colab.research.google.com/
2. Upload the desired notebook from the `experiments/` directory
3. Run the notebook

### Execution Modes

- **Step-by-step execution**  
  Some notebooks are structured into multiple stages (e.g., setup, preprocessing, training, evaluation) and should be executed sequentially, cell by cell.

- **Single-cell execution**  
  Other notebooks are implemented as a single cell and can be executed in one step.

### Hardware

- GPU is recommended (Colab → Runtime → Change runtime type → GPU)
- CPU is supported but significantly slower

- **exp9 – Human Data Augmentation with LLRD**  
  I incorporate real human-written code and apply layer-wise learning rate decay.

All experiments are implemented as standalone notebooks in the `experiments/` directory.
