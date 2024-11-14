# Ma 513 - Hands-on Machine Learning for Cybersecurity
As part of the Statistical Learning course at IPSA, this project focuses on developing a system that automatically recognizes domain-specific entities. The project is framed as a Named Entity Recognition (NER) Competition for Cybersecurity at IPSA.

For more detailed background information on Named Entity Recognition and to explore relevant resources, you can refer to my dedicated [GitHub repository](https://github.com/AtillaKaanAlkan/Named-Entity-Recognition.git).


### Dataset Description

The dataset for [SemEval-2018 Task 8](https://aclanthology.org/S18-1113/), titled "Semantic Extraction from Cybersecurity Reports using Natural Language Processing (SecureNLP)," focuses on extracting meaningful cybersecurity information through Named Entity Recognition (NER). It aims to automatically identify and classify critical cybersecurity-related entities in text, such as malware, attacks, and threat actors, from technical cybersecurity documents. 

 The datasets are in JSON Lines format (each line is a json dictionary). The datasets are formatted similarly to the CONLL2003 format. Each token is associated with an NER tag. The tags follow the "B-" and "I-" convention from the IOB2 syntax.

Each entry consists of a dictionary with the following keys:

- "**unique_id**": An Integer, corresponding to the unique identifier of the sentence;
- "**tokens**": The list of tokens (strings) that form the text of this sample. Must be included in the predictions.;
- "**ner_tags**": the list of NER tags (in IOB2 format);

Example of an entry:

```

{"unique_id": 4775,
 "tokens": ["This", "collects", ":", "Collected", "data", "will", "be", "uploaded", "to", "a", "DynDNS", "domain", "currently", "hosted", "on", "a", "US", "webhosting", "service", "."], 
 "ner_tags": ["B-Entity", "B-Action", "O", "B-Entity", "I-Entity", "O", "B-Action", "I-Action", "B-Modifier", "B-Entity", "I-Entity", "I-Entity", "I-Entity", "I-Entity", "I-Entity", "I-Entity", "I-Entity", "I-Entity", "I-Entity", "O"]
}

```

You can load the data as a list of dictionaries in Python:

```
import json
with open("path/to/corpus.jsonlines", 'r') as f:
    corpus_json = [json.loads(l) for l in list(f)]
```

### NER Task Submission Instructions

Your submissions will be evaluated based on the F1-Score for named entity recognition (NER) at the entity level, using the CoNLL-2000 shared task metric via the `seqeval` library.

##### Baseline Model
A baseline model will be provided soon for reference in this NER task.

##### Evaluation
You will be ranked according to your predictions on the `NER-TESTING.jsonlines` file.

###### Steps for Submission

1. **Training and Development:**
   - Use the `NER-TRAINING.jsonlines` and `NER-VALIDATION.jsonlines` datasets for training and development.

2. **Model Predictions:**
   - After training your model, generate a prediction file that follows the same format as the `NER-TESTING.jsonlines` file.

3. **Submission:**
   - Send your predictions file to the following email:  
     **atilla1.alkan@ipsa.fr**

### System Description Instructions

You must provide a system description report (.pdf format) presenting your work and the experiments/models that gave the best results. This involves explaining the problem, the possible solutions, and those you have chosen by presenting the strengths and weaknesses. Particular attention should be paid to the explanation of the considered algorithms. The report should consist of the following sections:

#### Data Exploration and Preprocessing 
Please familiarize yourself with the dataset, i.e., examine it and understand the class distribution. Perform necessary preprocessing steps to prepare the texts for training a machine learning model. 

#### Model Selection and Experimental Settings
Identify an appropriate architecture for this NER task. You can experiment with established architectures like Logistic Regression, Support Vector Machine, and Naive Bayes or propose a custom design. It would help if you justified your choice by providing reasoning for your choice of architecture. 

#### Results Analysis
Interpret the results, identifying strengths and potential weaknesses in the model's prediction of different categories. You should Perform an error analysis by examining cases where the model makes incorrect predictions. This will help you understand if specific categories are more challenging to classify.

#### GitHub Repository
Please provide a GitHub repository containing your code for this project. The repository should be organized and include a README.md explaining the project, setup instructions, and how to run the code. Ensure the code is executable, documentation is clear, and experiments are reproducible (use fixed random seeds to save any essential model checkpoints or outputs).

#### Timeline

The project will end with the system report submission on Monday, December 16th (11:59 pm). Make sure to finalize and upload your GitHub repository by this date, ensuring all code is executable, well-documented, and reproducible. 
