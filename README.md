## GeoGPT-CoT-QA Dataset: A Large-scale Geoscience Chain-of-Thought QA Dataset for Supervised Fine-Tuning of LLMs

### 1. Dataset Description

We introduce **GeoGPT-CoT-QA Dataset**, a large-scale synthetic question–answer (QA) corpus enriched with chain-of-thought (CoT) reasoning traces, developed to support supervised fine-tuning (SFT) of geoscience reasoning models. The [GeoGPT-R1-Preview](https://huggingface.co/GeoGPT-Research-Project/GeoGPT-R1-Preview) is specifically fine-tuned using this dataset to enhance its geoscience reasoning capabilities.

The dataset was constructed from open-access geoscience publications licensed under CC BY. Using an automated data synthesis pipeline, we generated professional QA pairs with explicit reasoning steps from full-text articles. The synthesis process was powered by [DeepSeek-R1-Distill-Qwen-32B](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-32B), which generated both the questions, answers and corresponding step-by-step reasoning process. To ensure logical and semantic consistency across these components, we further employed [Qwen2.5-72B-Instruct](https://huggingface.co/Qwen/Qwen2.5-72B-Instruct) for consistency verification and quality filtering.

The dataset contains a total of **39,393** CoT QA instances, covering a wide spectrum of Earth science subfields, including geology, hydrology, atmospheric science, geophysics, ocean science, geochemistry, among others. By incorporating structured reasoning traces, the dataset enables large language models to learn not only the mapping from input to output but also the underlying thought processes necessary for scientific inference. To download the dataset, please visit: https://huggingface.co/datasets/GeoGPT-Research-Project/GeoGPT-CoT-QA

Each entry in GeoGPT-CoT-QA Dataset includes the following information:

- `index`: unique identifier of the CoT QA item

- `question`: automatically generated geoscience-related question

- `think`: synthesized chain-of-thought reasoning process

- `answer`: corresponding synthesized reference answer

- `title`: title of the source publication

- `authors`: list of publication authors

- `doi`: digital object identifier of the source publication

- `journal`: name of the publishing journal

- `volume`: volume number of the source publication

- `pages`: page range of the source publication

- `license`: usage license of the source publication (all is under CC BY)

### 2. How to download

The dataset is hosted on the [Hugging Face Hub](https://huggingface.co/datasets/GeoGPT-Research-Project/GeoGPT-CoT-QA) as an CSV file (.csv).

#### Using `wget` or `curl`
```
wget https://huggingface.co/datasets/GeoGPT-Research-Project/GeoGPT-CoT-QA/blob/main/geogpt-cot-qa.csv
```
```
curl -L -o geogpt-cot-qa.csv https://huggingface.co/datasets/GeoGPT-Research-Project/GeoGPT-CoT-QA/blob/main/geogpt-cot-qa.csv
```

#### Using 🤗`datasets` library

```python
from datasets import load_dataset

data = load_dataset("GeoGPT-Research-Project/geogpt-cot-qa")
```

### 3. Dataset Construction

GeoGPT-CoT-QA Dataset was constructed using the [zjsyn_qa_generator](https://github.com/GeoGPT-Research-Project/Foundation2Domain-LLM-Training/tree/main/src/data_tools/zjsyn_qa_generator) module from the [Foundation2Domain-LLM-Training](https://github.com/GeoGPT-Research-Project/Foundation2Domain-LLM-Training) project.

Generation code: https://github.com/GeoGPT-Research-Project/Foundation2Domain-LLM-Training

### 4. License and Intended Uses

**License**：The dataset is released under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

**Copyright**: Copyright (c) 2025 Zhejiang Lab. All rights reserved.

**Intended Use**：The dataset is intended for research, development, and educational purposes, particularly for:

- Performance evaluation: Assessing domain-specific question answering capabilities and benchmarking the performance of large language models in geoscience contexts.

- Model training: Enabling supervised fine-tuning (SFT) of geoscience-oriented large language models to enhance accuracy and reasoning ability.

- System development: Supporting the construction and evaluation of geoscience-focused QA systems and specialized datasets.

- Scientific advancement: Promoting open scientific research and contributing to improved methodologies for information retrieval, knowledge organization, and discovery in Earth sciences.

It must be used with proper attribution and in accordance with the terms of the CC BY 4.0 license.

### 5. Contact
For questions, feedback, or contributions, please open an issue in this repository or contact us at 📧 [support.geogpt@zhejianglab.org](support.geogpt@zhejianglab.org).
