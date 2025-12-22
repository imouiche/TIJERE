🚀 TIJERE: Threat Intelligence Joint Entity & Relation Extraction
A Knowledge-Driven, State-of-the-Art Joint Extraction Framework
              <img width="637" height="434" alt="Image" src="https://github.com/user-attachments/assets/7c6fd47d-67ed-423a-a727-cd8acdfae08a" />

TIJERE is a novel joint entity and relation extraction framework designed specifically for Cyber Threat Intelligence (CTI).
It bridges the gap between unstructured threat reports and structured cybersecurity knowledge graphs by combining expert domain knowledge, multi-sequence labeling, and deep contextual embeddings.

🌟 Why TIJERE?

Modern cybersecurity operations rely on accurate, explainable, and structured intelligence.
However, most threat intelligence remains buried in unstructured text (reports, blogs, PDFs).

TIJERE solves this by:

✅ Jointly extracting entities and relations in a single unified framework

✅ Handling overlapping relations and feature confusion

✅ Reducing language ambiguity using domain-adapted embeddings

✅ Integrating human analyst expertise directly into the learning process

✅ Enabling knowledge graph construction for automated reasoning

Related Works

<img width="813" height="576" alt="Image" src="https://github.com/user-attachments/assets/f3ebe74d-8d66-45fe-9bb4-908cd05f3376" />

🧠 Key Innovations
🔹 Multi-Sequence Labeling Representation (MSLR)

Unlike traditional tagging schemes, MSLR generates a separate sequence per entity pair, allowing the model to:

Capture overlapping relations

Preserve contextual integrity

Avoid noisy sentence duplication

🔹 Analyst Expert Knowledge (EDF)

TIJERE embeds domain knowledge via:

Entity Masks (positional focus)

Entity Type Embeddings (semantic grounding)

🔹 Security-Aware Language Models

Built on SecureBERT⁺, a cybersecurity-tuned transformer that:

Reduces domain ambiguity

Improves generalization across CTI reports

🏗️ Architecture Overview

High-level pipeline:

Tokenization + Multi-Sequence Labeling

PLM Embeddings (BERT / SecureBERT⁺)

Sequential Modeling (BiGRU / BiLSTM)

NER Head (CRF for valid BIO transitions)

RE Head (Entity Pooling + Type Embeddings + Dense Classifier)

📌 The architecture explicitly separates NER-specific and RE-specific learning paths to avoid feature interference.

📊 Dataset: DNRTI-JE

📁 First publicly available joint NER+RE dataset for cybersecurity

🧩 13 entity types, 15 relation types

🧠 Expert-annotated following a domain ontology

📄 6,592 sentences from real APT reports

👉 Used for all experiments in the TIJERE paper

📌 Citation

If you use TIJERE or DNRTI-JE, please cite:

@article{mouiche2025tijere,
  title={TIJERE: A Novel Threat Intelligence Joint Extraction Model based on Analyst Expert Knowledge},
  author={Mouiche, Inoussa and Saad, Sherif},
  journal={Knowledge-Based Systems},
  year={2025},
  doi={10.1016/j.knosys.2025.114346}
}


🔗 DOI: https://doi.org/10.1016/j.knosys.2025.114346

🧪 Getting Started (Dataset Split)
```python
import json
from sklearn.model_selection import train_test_split

dataset_path = 'dnrti-je.json'

def write_to_file(dataset, filename):
    with open(filename, 'w') as file:
        json.dump(dataset, file, indent=4)

with open(dataset_path, 'r') as f:
    data = json.load(f)

train_data, temp_data = train_test_split(data, test_size=0.2, random_state=42)
val_data, test_data = train_test_split(temp_data, test_size=0.5, random_state=42)

print(f"Training data size: {len(train_data)}")
print(f"Validation data size: {len(val_data)}")
print(f"Test data size: {len(test_data)}")
```
⚖️ Class Imbalance (Important!)

⚠️ Relation Extraction is highly imbalanced

✔️ We strongly recommend:

Oversampling minority relation classes

Using class-weighted loss functions

Evaluating with macro-F1

📈 Results Highlights

🏆 NER F1 > 0.93

🏆 RE F1 > 0.98

🚀 Outperforms recent pipeline and joint extraction baselines

🔬 Validated through extensive ablation studies

<img width="835" height="234" alt="Image" src="https://github.com/user-attachments/assets/ded13bba-2333-42a8-8b24-388e836d249d" />

🔗 Code & Reproducibility

🧪 Colab notebooks with sample implementations are provided

📦 Full training and evaluation pipeline will be released after project completion

📩 Need help running the code or adapting TIJERE to your domain?
➡️ Reach out — collaboration welcome!

🌍 Beyond Cybersecurity

TIJERE’s design is domain-agnostic and applicable to:

🧬 Biomedical text mining

💰 Financial intelligence

🏥 Healthcare analytics

🔐 Safety-critical AI systems

👨‍💻 Maintainer

Inoussa Mouiche
PhD Candidate, Computer Science
Cybersecurity × AI × Knowledge Graphs

🔗 GitHub: https://github.com/imouiche

🔗 Google Scholar: https://scholar.google.com
