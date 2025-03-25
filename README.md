# Effective-Joint-Entity-and-Relation-Extractions-Model
- TIJERE: Threat Intelligence Joint Entity and Relation Extractions
- If you use this dataset, cite the preprint paper as: # Inoussa Mouiche, Sherif Saad. TIJERE: A Novel Threat Intelligence Joint Extraction Model based on Analyst Expert Knowledge. TechRxiv. March 25, 2025.
DOI: 10.36227/techrxiv.174286575.55673704/v1

- Split the dataset into train, test, and validation sets

+++++++++++++++++++++++++++++++++++++++++++++++++++++++
dataset_path ='dnrti-je.json'

def write_to_file(dataset, filename):
    with open(filename, 'w') as file:
        json.dump(dataset, file, indent=4)
# Load the dataset
with open(dataset_path, 'r') as f:
    data = json.load(f)

train_data, temp_data = train_test_split(data, test_size=0.2, random_state=42)
val_data, test_data = train_test_split(temp_data, test_size=0.5, random_state=42)

print(f"Training data size: {len(train_data)}")
print(f"Validation data size: {len(val_data)}")
print(f"Test data size: {len(test_data)}")
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

- For the RE, you may want to oversample the low-representative classes.
- Reach out if you need help with the code. The full code will be made available after the project is completed.
