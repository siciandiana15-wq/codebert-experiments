# CodeParrot Dataset

The CodeParrot dataset is used as an additional source of large-scale code data for augmentation and domain generalization. generalization.

The dataset is publicly available on Hugging Face:

https://huggingface.co/datasets/codeparrot/codeparrot-clean

This dataset consists of a large collection of source code extracted from public GitHub repositories, primarily representing human-written code across multiple programming languages.

To load the dataset:

```python
from datasets import load_dataset
ds = load_dataset("codeparrot/codeparrot-clean")
