# Named Entity Recognition (NER) Model Training and Evaluation

This repository contains code for training and evaluating Named Entity Recognition (NER) models for English using the MultiNERD dataset. The code uses Hugging Face's Transformers library and fine-tunes a transformer-based language model for NER.

## Getting Started

### Prerequisites

- Python 3.x
- [pip](https://pip.pypa.io/en/stable/installation/)
- [virtualenv](https://pypi.org/project/virtualenv/)

### Installation

1. Clone this repository:

    ```bash
    git clone https://github.com/zoherorabe/MultiNERD_RISE_Task.git
    cd ner-model
    ```

2. Create and activate a virtual environment:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

### Dataset and Pre-trained Model

1. Download the MultiNERD dataset.

2. Choose a pre-trained language model from the [Hugging Face Model Hub](https://huggingface.co/models) (e.g., `distilbert-base-cased`).


### Training:
1. follow the ner_task.ipynb notebook to train and evaluate the `distilbert-base-cased` on the MultiNERD dataset


### Results

#### System A

- Overall Recall: 0.8967
- Overall Precision: 0.8843
- Overall F1: 0.8904

(Individual entity type metrics available in the results file)

#### System B

- Overall Recall: 0.9575
- Overall Precision: 0.9510
- Overall F1: 0.9542

(Individual entity type metrics available in the ner_task.ipynb file) 

### Major Findings
In our NER experiments using the MultiNERD dataset, we employed the "distilbert-base-cased" pretrained model for both System A and System B. System A, trained on a diverse set of entity types, demonstrated strong overall precision, recall, and F1 scores (88.4%, 89.7%, 89.0%, respectively) using this compact yet powerful language model. Notably, it excelled in recognizing people (PER), locations (LOC), and organizations (ORG).

Conversely, System B, fine-tuned on a reduced set of five entity types using the same "distilbert-base-cased" model, showed superior overall recall, precision, and F1 scores (95.7%, 95.1%, 95.4% respectively). The specialized model proved effective in recognizing specific entities such as locations and organizations.

However, it's crucial to acknowledge the limitations of using a distilled model like "distilbert-base-cased." While it offers computational efficiency, its reduced complexity may result in a trade-off in capturing intricate relationships and nuances within the data. Additionally, the model's performance heavily depends on the quality and representativeness of the training data, and variations in the dataset may impact generalization. Further exploration with more complex models and diverse datasets could provide insights into overcoming these limitations and refining the balance between model efficiency and performance.
