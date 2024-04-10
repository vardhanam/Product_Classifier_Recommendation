# Fashion Products Similarity Search

This project demonstrates a fashion image similarity search using deep learning and vector databases. It allows users to upload an image of a fashion item and find similar items in the inventory.

## Dataset

The dataset used in this project is the "Fashion Product Images (Small)" dataset from Kaggle. It contains a CSV file (`styles.csv`) with information about fashion products and their corresponding images.

To download the dataset, make sure you have the Kaggle API installed and configured. Then, run the following command:

```
kaggle datasets download -d paramaggarwal/fashion-product-images-small
```

Extract the downloaded ZIP file to obtain the `styles.csv` file and the `images` directory.

## Prerequisites

Before running the code, ensure you have the following dependencies installed:

- Python 3.x
- PyTorch
- Transformers
- Qdrant
- Gradio
- Pillow
- pandas

You can install the required packages using pip:

```
pip install torch transformers qdrant-client gradio pillow pandas
```

## Setup

1. Make sure you have downloaded the dataset and extracted the `styles.csv` file and the `images` directory.

2. Update the `csv_file_path` variable in the code to point to the location of the `styles.csv` file on your system.

3. Ensure that the Qdrant server is running on `localhost:6333`. If your Qdrant server is running on a different host or port, update the `QdrantClient` initialization accordingly.

## Usage

1. Run the provided code in a Python environment.

2. The code will read the `styles.csv` file, extract the unique item types, and create text embeddings using the CLIP model.

3. The text embeddings will be stored in a Qdrant collection named "text_embeddings".

4. The code will then process all the images in the `images` directory, generate image embeddings using the CLIP model, and store them in a Qdrant collection named "image_embeddings".

5. Finally, a Gradio interface will be launched, allowing users to interact with the fashion image similarity search.

6. Users can upload an image of a fashion item, and the system will classify the item type and display similar items from the inventory.

7. The "Clear" button can be used to reset the uploaded image, classified item type, and the image gallery.

## Customization

- If you want to use a different dataset or modify the CSV file, update the `csv_file_path` variable and ensure that the CSV file has a column named "articleType" containing the item types.

- You can adjust the number of similar items displayed in the image gallery by modifying the `limit` parameter in the `client.search` function within the `image_path_list` function.

- The code uses the "openai/clip-vit-base-patch32" model for generating embeddings. If you want to use a different model, update the `model_id` variable and ensure that the model is compatible with the CLIP architecture.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- The dataset used in this project is sourced from Kaggle: [Fashion Product Images (Small)](https://www.kaggle.com/paramaggarwal/fashion-product-images-small).
- The code utilizes the CLIP model and the Qdrant vector database for efficient similarity search.