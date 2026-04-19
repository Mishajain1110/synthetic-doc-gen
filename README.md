# synthetic-doc-gen

Synthetic document generation pipeline for creating large-scale training datasets using structured document templates such as passports, visas, and other text-based documents.  

The system leverages **OCR, image processing, signature detection, and language models** to generate realistic synthetic document data that can be used for training and evaluating document understanding systems.

The repository provides separate pipelines for different document types, implemented using Jupyter notebooks.

---


### Folder Description

- **passport_files/**  
  Contains all the templates, images, and supporting files required to run the **synthetic_passport_pipeline.ipynb**.

- **visa_files/**  
  Contains the necessary files required to run the **synthetic_visa_pipeline.ipynb**.

- **text_based_docs_files/**  
  Contains supporting files and templates used for generating **synthetic_text_based_doc_pipeline.ipynb**.

Each pipeline notebook expects the corresponding folder to be present with the required files before execution.

---

## API Requirements

This project uses external APIs for document processing and text generation.  
Before running the pipelines, you must configure the required API credentials.

### 1. Azure Document Intelligence (DocumentClient API)

The pipelines use **Azure Document Intelligence** to analyze and extract document fields.

To run the notebooks, you must provide:

- **Azure Endpoint**
- **Azure API Key**

These credentials can be obtained by creating a **Document Intelligence resource** in the Azure Portal.

Example configuration in the notebook:

```python
endpoint = "YOUR_API_ENDPOINT_HERE"
api_key = "YOUR_API_KEY_HERE"
```

### 2. GPT API Access

This project uses **GPT-3.5-Turbo** for text generation during the synthetic document creation process.

To access the model, the project uses the following free GPT API wrapper:

https://github.com/chatanywhere/GPT_API_free

Follow the instructions in the repository to obtain your **GPT API key**.

Once you obtain the API key, add it to the notebook before running the pipeline.

Example configuration in the code:

```python
GPT_API_KEY = "YOUR_API_KEY_HERE"
model_name = "gpt-3.5-turbo"
```
---

## How to Run the Pipelines

The pipelines are implemented using **Jupyter Notebooks (.ipynb)**. Each notebook corresponds to a different document generation pipeline.

### Step 1: Clone the Repository

```bash
git clone https://github.com/<your-username>/synthetic-doc-gen.git
cd synthetic-doc-gen
```

### Step 2: Configure API Credentials

Before running the pipelines, configure the required credentials in the notebook:

- **Azure Document Intelligence Endpoint**
- **Azure API Key**
- **GPT API Key (for GPT-3.5-Turbo)**

### Step 3: Run the Pipelines

Open the corresponding notebook and run all cells.

| Pipeline | Notebook |
| --- | --- |
| Passport Synthetic Generation | `synthetic_passport_pipeline.ipynb` |
| Visa Synthetic Generation | `synthetic_visa_pipeline.ipynb` |
| Text-based Document Generation | `synthetic_text_based_doc_pipeline.ipynb` |

Each notebook will generate synthetic document data using the files from the corresponding folder.
