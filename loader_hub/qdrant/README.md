# Qdrant Loader

The Qdrant Loader returns a set of texts corresponding to embeddings retrieved from a Qdrant Index.
The user initializes the loader with a Qdrant index. They then pass in a query vector.

## Usage

Here's an example usage of the QdrantReader.

```python
from gpt_index import download_loader
import os

reader = QdrantReader(host="localhost")
# the query_vector is an embedding representation of your query_vector
# Example query vector:
#   query_vector=[0.3, 0.3, 0.3, 0.3, 0.3, 0.3, 0.3, 0.3]

query_vector=[n1, n2, n3, ...]

# NOTE: Required args are collection_name, query_vector.
# See the Python client: https://github.com/qdrant/qdrant_client
# for more details. 
documents = reader.load_data(
    collection_name="demo",
    query_vector=query_vector,
    limit=5
)

```