# DL-Bench: A Benchmark Dataset for Deep Learning Code Generation

**DL-Bench** is a novel benchmark dataset designed to evaluate the code generation capabilities of Large Language Models (LLMs) specifically for deep learning (DL) tasks. Unlike existing datasets such as **DS-1000**, DL-Bench covers the full DL pipeline, diverse machine learning tasks, and multiple input types, providing a more challenging and comprehensive benchmark.

## Dataset Overview

DL-Bench contains **520 functional-level DL code samples** extracted and curated from the most popular GitHub repositories. Each instance in the dataset is categorized based on:

1. **Pipeline Stage**: Pre/Post-Processing, Model Construction, Training, Inference, Evaluation & Metrics
2. **ML Task Type**: Classification, Regression, Object Detection, Image Segmentation, Time-Series Prediction, Recommendation, and General
3. **Input Data Type**: Image, Text, Structured Array (Tabular), and Others

Each instance includes:
- A code generation **prompt**
- The corresponding **ground-truth code**
- An extensive set of **unit tests** for evaluation

## Results

We evaluated the performance of four state-of-the-art LLMs on DL-Bench using the **Pass@1** metric, which measures the likelihood that the top solution passes all test cases.

### Overall Results
| LLM Model          | DL-Bench Pass@1 (%) |
|---------------------|----------------------|
| GPT-4o             | 31                   |
| Claude 3.5 Sonet   | 28                   |
| LLaMA 3.1 70B      | 21                   |
| Mistral 7B         | 15                   |

### Results by Pipeline Stage
| Pipeline Stage        | GPT-4o | Claude 3.5 | LLaMA 3.1 | Mistral 7B |
|-----------------------|--------|------------|-----------|------------|
| Pre/Post-Processing   | 33     | 31         | 22        | 14         |
| Model Construction    | 26     | 22         | 14        | 11         |
| Training              | 31     | 28         | 21        | 16         |
| Inference             | 30     | 30         | 29        | 26         |
| Evaluation & Metrics  | 32     | 29         | 24        | 19         |

![Pipeline Stage Performance](https://via.placeholder.com/800x400.png?text=Pipeline+Stage+Performance)

### Results by ML Task Type
| ML Task Type          | GPT-4o | Claude 3.5 | LLaMA 3.1 | Mistral 7B |
|-----------------------|--------|------------|-----------|------------|
| Classification        | 30     | 32         | 28        | 24         |
| Regression            | 36     | 35         | 22        | 21         |
| Object Detection      | 28     | 30         | 17        | 11         |
| Image Segmentation    | 19     | 21         | 14        | 11         |
| Time-Series Prediction| 33     | 29         | 31        | 13         |
| Recommendation        | 58     | 47         | 40        | 29         |
| General               | 31     | 27         | 19        | 13         |

![ML Task Performance](https://via.placeholder.com/800x400.png?text=ML+Task+Performance)

### Results by Input Data Type
| Input Data Type       | GPT-4o | Claude 3.5 | LLaMA 3.1 | Mistral 7B |
|-----------------------|--------|------------|-----------|------------|
| Image                 | 25     | 25         | 18        | 8          |
| Text                  | 32     | 30         | 30        | 23         |
| Structured Array      | 29     | 24         | 19        | 13         |
| Others                | 40     | 33         | 26        | 25         |

![Input Data Performance](https://via.placeholder.com/800x400.png?text=Input+Data+Performance)

## Key Findings
1. **Pipeline Stages**: Pre/Post-Processing tasks are easier for LLMs, while Model Construction is the most challenging.
2. **Task Type**: LLMs perform best on Recommendation tasks and struggle most with Image Segmentation.
3. **Input Data Types**: Image data poses significant challenges, while Text and Structured Arrays are easier to handle.

![Overall Performance](https://via.placeholder.com/800x400.png?text=Overall+Performance)

## Dataset Statistics
- **Pipeline Stages**: 
  - Pre/Post-Processing: 210
  - Model Construction: 119
  - Training: 75
  - Inference: 58
  - Evaluation & Metrics: 58
- **ML Task Types**: 
  - Classification: 60
  - Regression: 14
  - Object Detection: 37
  - Image Segmentation: 40
  - Time-Series Prediction: 24
  - Recommendation: 17
  - General: 328
- **Input Data Types**:
  - Image: 238
  - Text: 28
  - Structured Array: 84
  - Others: 168

![Dataset Distribution](https://via.placeholder.com/800x400.png?text=Dataset+Distribution)

## Installation and Usage

1. **Clone the Repository**
```bash
git clone https://github.com/username/DL-Bench.git
cd DL-Bench
```

2. **Run Benchmark**
DL-Bench includes Docker images for easy reproducibility. Run the following to test an LLM's performance:
```bash
docker-compose up
```

3. **Leaderboard Submission**
To submit your results, open a pull request including your model's scores in the `leaderboard.md` file.

## Leaderboard
| Rank | Model            | Pass@1 (%) |
|------|------------------|------------|
| 1    | GPT-4o           | 31         |
| 2    | Claude 3.5 Sonet | 28         |
| 3    | LLaMA 3.1 70B    | 21         |
| 4    | Mistral 7B       | 15         |

## Contributing
We welcome contributions to DL-Bench. Please follow the [contributing guidelines](CONTRIBUTING.md).

## Citation
If you use DL-Bench in your research, please cite:
```bibtex
@article{dlbench2024,
  title={DL-Bench: Code Generation Benchmark Dataset for Deep Learning},
  author={Anonymous Authors},
  journal={ArXiv},
  year={2024}
}
```
