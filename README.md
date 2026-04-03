# An Analysis of CodeBERT Generalization Power for Detecting AI-Generated Code Across Unseen Languages and Domains

This repository contains the experimental implementation developed for my study on detecting AI-generated code using Transformer-based architectures, with a particular focus on the CodeBERT model.

Recent advances in large language models (LLMs) have enabled the generation of source code that is both syntactically correct and semantically coherent. While these developments have significantly improved developer productivity, they also introduce challenges related to code authorship, transparency, and reliability. In particular, distinguishing between human-written and machine-generated code has become an important research problem.

In this work, I investigate the effectiveness of CodeBERT for the task of AI-generated code detection and analyze its ability to generalize across different programming languages and domains. My approach is based on a series of controlled experiments that explore multiple training strategies, including fine-tuning configurations, data augmentation techniques, and cross-language evaluation settings.

The results indicate that although the model achieves strong performance when the training and evaluation data follow similar distributions, its effectiveness decreases significantly under distribution shift. These findings highlight the importance of training data diversity and reveal limitations of current approaches in handling unseen languages and domains.

##  Experiments

The repository is organized as a collection of experiments, each corresponding to a specific training strategy or evaluation setting described in the paper.

- **exp1 – Frozen BERT Baseline**  
  This experiment evaluates a baseline where BERT is employed as a fixed feature extractor, without fine-tuning.

- **exp2 – Partial Fine-Tuning**  
  This experiment fine-tunes only the last Transformer layers, leading to a significant improvement in performance.

- **exp3 – CodeBERT Fine-Tuning and LLM Comparison**  
  This experiment fully fine-tunes CodeBERT and compares its performance with generative models.

- **exp4 – Cross-Language Generalization**  
  This experiment analyzes the ability of CodeBERT to transfer knowledge across programming languages.

- **exp5 – Language Rotation Strategy**  
  This experiment investigates whether multi-language training improves cross-language transfer.

- **exp6 – Domain Shift with GRL Augmentation**  
  This experiment evaluates model robustness under domain shift using adversarial training with a Gradient Reversal Layer (GRL).

- **exp7 – Large-Scale Domain Shift Training**  
  This experiment extends the training setup with large-scale data augmentation and stronger regularization to improve robustness under domain shift.
  
- **exp8 – Human Data Augmentation with LLRD**  
  This experiment incorporates real human-written code and applies layer-wise learning rate decay to improve robustness under domain shift.
  
All experiments are implemented as standalone notebooks in the `experiments/` directory.

  ##  How to Run

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

##  Datasets

This project uses three main data sources:

- **SemEval-2026 Task 13 (Subtask A)** – primary dataset for training and evaluation  
  https://huggingface.co/datasets/DaniilOr/SemEval-2026-Task13  

- **CodeParrot** – large-scale corpus of mostly human-written code from GitHub  
  https://huggingface.co/datasets/codeparrot/codeparrot-clean  

- **Augmentation datasets** – additional JSONL files used for data augmentation and domain shift simulation (available in `data/augmentation/`)

- **LLM Human-like datasets** – synthetic datasets generated using LLMs to mimic student-written code, capturing realistic structure, naming patterns, and minor inconsistencies(available in `data/llm_human-like/`)

For more details, see the corresponding folders in `data/`.

##  Results

The results for each experiment are reported at the end of the corresponding notebook.

While exact values may vary slightly across runs, the reported performance should remain in a similar range. Minor differences can occur due to factors such as randomness in data shuffling, stochastic training processes, and hardware variations.

##  Citation

- SemEval-2026 Task 13 Dataset  
  https://huggingface.co/datasets/DaniilOr/SemEval-2026-Task13  

- CodeParrot Dataset  
  https://huggingface.co/datasets/codeparrot/codeparrot-clean  

- CodeBERT  
  Feng et al., 2020  
  https://aclanthology.org/2020.findings-emnlp.139/

- Diana Sician, "About CodeBERT Generalization Power for Detecting AI-Generated Code
  Across Unseen Languages and Domains", submitted to 25th International Conference
  on Informatics in Economy, IE 2026

   For a complete list of references, please refer to the accompanying paper.


