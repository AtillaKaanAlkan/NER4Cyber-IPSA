# Ma 513 - Hands-on Machine Learning for Cybersecurity
Named Entity Recognition Competition for Cybersecurity at IPSA

### Dataset Description

The dataset for SemEval-2018 Task 8, titled "Semantic Extraction from Cybersecurity Reports using Natural Language Processing (SecureNLP)," focuses on extracting meaningful cybersecurity information through Named Entity Recognition (NER). It aims to automatically identify and classify critical cybersecurity-related entities in text, such as malware, attacks, and threat actors, from technical cybersecurity documents. 
As part of this Statistical Learning course at IPSA, the project aims to develop a model that will automatically recognize domain's entities.

The datasets are in JSON Lines format (each line is a json dictionary).
The datasets are formatted similarly to the CONLL2003 format. Each token is associated with an NER tag. The tags follow the "B-" and "I-" convention from the IOB2 syntax.

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

### Instructions for Participants

You can load the data as a list of dictionaries in Python:

```
import json
with open("path/to/corpus.jsonlines", 'r') as f:
    corpus_json = [json.loads(l) for l in list(f)]
```
### Evaluation

to be developed
