# Lluma: Large Language Understanding Mental Assistant

## Description

Lluma is a mental health assistant that leverages a specialized ontology and a Retrieval-Augmented Generation (RAG) system to provide context-aware and empathetic support for individuals facing mental health challenges. This project is particularly focused on addressing the mental health gap in under-resourced countries like Morocco.

The primary goal of this project is twofold:

1.  To create a comprehensive mental health ontology that models a wide range of concepts and their relationships.
2.  To integrate this ontology into a RAG-powered Large Language Model (LLM) to create a real-world assistant.

## Features

  * **Specialized Mental Health Ontology**: A detailed knowledge base covering mental health conditions, symptoms, treatments, and more.
  * **Retrieval-Augmented Generation (RAG)**: The system uses RAG to ground the LLM's responses in factual and verifiable information from the ontology, which helps to mitigate hallucinations and improve accuracy.
  * **Context-Aware Support**: Lluma is designed to provide precise and relevant answers to user queries about mental health.
  * **Open Source**: The project is open source and can be used by researchers and developers to build upon this work.

## Ontology

The mental health ontology is a core component of this project. It is written in the Turtle language and defines the following key classes:

  * **MentalHealthCondition**: Represents various mental health disorders.
  * **Symptom**: Describes the symptoms associated with mental health conditions.
  * **Treatment**: Covers different treatment approaches, including `PharmacologicalTreatment` and `PsychotherapyApproach`.
  * **CopingStrategy**: Defines strategies for managing mental health, categorized into `BehavioralCoping`, `CognitiveCoping`, and `EmotionalCoping`.
  * **Trigger**: Represents factors that can initiate or exacerbate mental health conditions.
  * **Drugs**:  Describes medications used in treatment.
  * **SideEffect**:  Represents potential side effects of medications.

The ontology also defines a rich set of object and data properties to represent the relationships between these classes, such as `alleviatesSymptom`, `causeSymptom`, `isRecommendedFor`, and `hasDescription`.

## Getting Started

### Prerequisites

You will need Python 3 and Jupyter Notebook installed to run the project.

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/lluma.git
    cd lluma
    ```
2.  Install the required dependencies:
    ```bash
    pip install -U langchain langchain-community rdflib sentence-transformers faiss-cpu ctransformers~=0.2.27
    ```

### Usage

1.  Open the `lluma.ipynb` notebook in Jupyter.
2.  Make sure the `lumaOnto.ttl` ontology file is in the same directory.
3.  Run the cells in the notebook to load the ontology, initialize the RAG model, and interact with the Lluma assistant.

## Citation

If you use this work in your research, please cite the following paper:

OUIDANI Ahmed, OUCHEN Chihab, CHEKRY Abderrahman. "Introducing Lluma: Large language understanding mental assistant."

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
