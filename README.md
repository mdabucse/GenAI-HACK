# IITM BS IYANDRA 🤖

## Table of Contents

1. [Overview](#overview)
2. [Requirements](#requirements)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Output](#output)
6. [Example](#example)

## Overview <a name="overview"></a>

## Workflow
![Forward Workflow](assets/flow-chart.png)

This script facilitates document retrieval and querying using embeddings. It integrates PDF text extraction, sentence embedding generation, efficient indexing for retrieval, and interaction with an external API for further analysis.

### Workflow Overview

1. **PDF Text Extraction:**
   - The script utilizes `fitz` (PyMuPDF) to extract text from PDF documents. It iterates through each page of the PDF, consolidating the extracted text into a cohesive body.

2. **Sentence Embedding Generation:**
   - Extracted text is segmented into sentences or paragraphs. Using the `sentence-transformers` library, each segment is converted into a dense vector representation (embedding). This embedding captures semantic information and enables efficient comparison between text segments.

3. **Indexing for Retrieval:**
   - Embeddings are indexed using `faiss`, a library for similarity search and clustering of dense vectors. This indexing optimizes the retrieval process, enabling rapid identification of text segments that closely match a given query.

4. **Querying an External API:**
   - The script interacts with an external API (`API_URL`) to further process and analyze the retrieved text. It sends the concatenated text segments (retrieved based on similarity to the query) as input to the API, typically receiving processed insights or additional data in response (`output`).

### Use Case Scenarios

- **Document Analysis:** Users can extract text from large documents (e.g., reports, manuals) and efficiently query specific sections based on user input.
  
- **Semantic Search:** The use of sentence embeddings allows for semantic similarity search, enabling the retrieval of text segments that convey similar meaning to the query text.

- **API Integration:** The script showcases how to integrate with external APIs for advanced text analysis, leveraging the embedded representations of text segments for deeper insights.

### Customization and Extensions

- **Model Selection:** Users can experiment with different sentence embedding models (`SentenceTransformer` offers various pre-trained models) to tailor embeddings based on specific domain requirements or performance preferences.

- **API Integration:** Modify the `query()` function to accommodate different APIs or endpoints, adapting the script for varied analytical needs or data sources.

### Next Steps

Explore and adapt the provided script (`main()` function and related components) to fit specific use cases or integrate with different APIs, expanding its functionality for diverse text analysis tasks.


## Requirements <a name="requirements"></a>

- **Python 3.9.19**
- **Create a Virtual Env**
    ```python
        - python -m venv genai
        - genai/Scripts/Activate
    ```
- **Libraries:**
  - `fitz` (PyMuPDF): PDF processing
  - `sentence-transformers`: Generating sentence embeddings
  - `faiss`: Efficient similarity search using embeddings
  - `numpy`: Array operations
  - `requests`: Making HTTP requests to APIs
  - `streamlit` Frontend Framework
  
## Installation <a name="installation"></a>

1. **Install Python:**
   - If Python is not installed, download it from [Python.org](https://www.python.org/downloads/).

2. **Install Required Libraries:**
   - Open a terminal or command prompt.
   - Run the following command to install the necessary Python libraries:
     ```
        pip install -r requirments.txt
     ```

## Usage <a name="usage"></a>

1. **Extracting Text from PDF:**
   - Update the `path` variable in the `main()` function to point to your PDF file.
   - Ensure the PDF contains the text you want to analyze.

2. **Creating Embeddings:**
   - Text extracted from the PDF is split into sentences or paragraphs.
   - Each sentence is converted into a dense vector representation using pre-trained models.

3. **Indexing Embeddings:**
   - Embeddings are indexed using FAISS for fast similarity search.

4. **Querying an API:**
   - A sample API (`API_URL`) is provided for demonstration purposes.
   - Ensure you have valid credentials or access to the API.
   - The retrieved text from the PDF is sent as input to the API.

5. **Output:**
   - The script prints or processes the API response (`output`), which typically includes insights or further processed data based on the retrieved text.
   ![First](assets/1.png)
   ![Secondd](assets/2.png)
## Example <a name="example"></a>

```python
# Example usage:
value = "query input text"
output = main(value)
print(output)
