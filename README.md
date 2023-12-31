# Chat with Multiple PDFs

This Python code implements a chat application that allows users to ask questions about multiple PDF documents. The application is built using the Streamlit framework and utilizes several libraries and modules for document processing, natural language understanding, and conversational retrieval.

## Features

- Upload multiple PDF documents
- Enter questions about the documents
- Receive relevant responses based on the questions asked

## Installation

To run this application, follow these steps:

1. Clone the repository:

```
git clone <repository_url>
cd <repository_directory>
```

2. Install the required dependencies using pip:

```
pip install -r requirements.txt
```

3. Set up the environment:

```
# Load environment variables
dotenv.load_dotenv()
```

## Usage

Run the following command to start the application:

```
streamlit run app.py
```

Once the application is running, you can access it through the provided URL. The application interface will allow you to upload PDF documents and ask questions about them. The system will process the documents, generate text chunks, and build a conversational retrieval chain to provide relevant answers to your questions.

## Code Structure

The code consists of the following main parts:

- **Document Processing**: The `get_pdf_text` function extracts text from PDF documents using the `PyPDF2` library. The `get_text_chunks` function splits the extracted text into smaller chunks using the `CharacterTextSplitter` from the `langchain` package.

- **Vector Store Creation**: The `get_vectorstore` function generates text embeddings using the `HuggingFaceInstructEmbeddings` model and creates a vector store using the `FAISS` library to map the text chunks to their respective embeddings.

- **Conversation Chain**: The `get_conversation_chain` function initializes a language model (LLM) from the `HuggingFaceHub` repository and creates a conversational retrieval chain using the LLM, the vector store as a retriever, and a conversation memory.

- **User Input Handling**: The `handle_userinput` function handles user questions, retrieves responses using the conversation chain, and displays the conversation history.

- **Main Function**: The `main` function sets up the Streamlit application, including page configuration and user interface components. It also manages the conversation state, handles user input, and triggers document processing when the "Process" button is clicked.

## Dependencies

The code relies on the following dependencies:

- `streamlit`: A Python framework for building interactive web applications.
- `dotenv`: A library for loading environment variables from a `.env` file.
- `PyPDF2`: A library for extracting text from PDF documents.
- `langchain`: A custom package providing text processing, embeddings, vector stores, and conversational retrieval capabilities.
- `htmlTemplates`: Custom HTML templates for displaying user and bot messages.
- `HuggingFace Hub`: A model repository from Hugging Face for accessing pre-trained language models.

## Contributing

Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This code is released under the [MIT License](LICENSE). Feel free to modify and use it for your own projects.

## Acknowledgments

This project utilizes various open-source libraries and models. We acknowledge the developers and contributors of the following projects:

- Streamlit: https://www.streamlit.io/
- dotenv: https://github.com/theskumar/python-dotenv
- PyPDF2: https://github.com/mstamy2/PyPDF2
- Hugging Face Transformers: https://github.com/huggingface/transformers
- FAISS: https://github.com/facebookresearch/faiss

We express our gratitude to the

 open-source community for their valuable contributions.
