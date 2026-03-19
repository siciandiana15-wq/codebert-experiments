# SemEval-2026 Task 13 (Subtask A)

The official SemEval-2026 Task 13 dataset for Subtask A is used, which focuses on detecting whether a given code snippet is human-written or machine-generated.

The dataset is publicly available on Hugging Face:

https://huggingface.co/datasets/DaniilOr/SemEval-2026-Task13

Configuration "A" is used, which provides the following splits:
- train
- validation
- test

To load the dataset:

```python
from datasets import load_dataset
ds = load_dataset("DaniilOr/SemEval-2026-Task13", "A")
