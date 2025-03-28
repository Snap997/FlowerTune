# FlowerTune Competition - Federated Fine-Tuning with Flower

## Introduction
This repository contains my submission for the **FlowerTune Challenge**, a federated learning competition aiming to fine-tune Large Language Models (LLMs) in a federated environment using the [Flower framework](https://flower.ai).  
The challenge leaderboard can be found [here](https://flower.ai/benchmarks/llm-leaderboard/nlp/).

Flower is an open-source framework designed to simplify federated learning tasks, allowing seamless orchestration and aggregation of machine learning models trained collaboratively across multiple decentralized clients.

## Results
Below are the accuracy scores obtained in the evaluation of my federated fine-tuned model:

| Domain           | Accuracy (%) |
|------------------|--------------|
| STEM             | 44.49        |
| Social Sciences  | 63.89        |
| Humanities       | 49.92        |
| **Average**      | **52.77**    |



## Technical Details

- **Base Model**: [`Qwen2.5-1.5B-Instruct`](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)
- **Fine-Tuning Technique**: DoRA (Dynamic Low-Rank Adaptation)
  - Rank (`r`) = 8
  - Alpha (`α`) = 16
- **Training Parameters**:
  - Per-device train batch size: `4`
  - Federated aggregation algorithm: **FedProx** (`μ` = 0.05)
  - Total federated training rounds: `15`
- **Communication Budget**: `2116.00 MB`

## Repository Structure

The structure of this repository is organized as follows:

- [`general_nlp/peft_model`](general_nlp/peft_model)  
  Directory containing the federated fine-tuned model weights obtained using PEFT (Parameter-Efficient Fine-Tuning) techniques.

- [`general_nlp/training`](general_nlp/training)  
  Directory including the training scripts and configuration files for federated fine-tuning with the Flower framework.

- [`general_nlp/flowertune-eval-general-nlp`](general_nlp/flowertune-eval-general-nlp)  
  Directory containing the scripts used for evaluating and validating the fine-tuned federated model's performance across the benchmark domains.

## Training Progress

The graph below illustrates the improvements in model performance across the training rounds.  
At the end of round 15, the training loss was `1.2206`.




