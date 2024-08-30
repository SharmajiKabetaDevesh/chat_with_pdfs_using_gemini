
Steps to use this app:
1) Create a virtual environment using "python -m venv venv"
2) Activate venv using "venv/Scripts/activate
3) You need to clone this app now.
4) Install all packages using "python install -r requirements.txt"
5) Create an ".env" file and place your google api key.
6) Go to terminal and hit "streamlit run app.py"




####Explaination
1. Environment Setup:
   - The required libraries are imported, and environment variables are loaded using `load_dotenv`. The Google Generative AI API key is retrieved.

2. PDF Text Extraction:
   - `get_pdf_texts` reads and extracts text from the uploaded PDF file using `PyPDF2`.

3. Text Chunking:
   - `get_text_chunks` splits the extracted text into manageable chunks using `RecursiveCharacterTextSplitter`, with a specified chunk size and overlap.

4. Vector Store Creation:
   - `get_vector_store` creates a vector store using FAISS, where text chunks are embedded using Google's Generative AI embeddings model. The vector store is saved locally for later retrieval.

5. Conversational Chain:
   - `get_conversational_chain` initializes a chain for question-answering by loading a prompt template and the ChatGoogleGenerativeAI model. This chain is used to generate answers based on the context provided.

6. User Input Handling:
   - `user_input` processes the user's question by searching the FAISS index for similar text chunks and then passing them to the conversational chain to generate a response. The response is displayed using Streamlit.

7. Main Application:
   - `main` sets up the Streamlit UI, allowing users to upload a PDF, process it, and then ask questions. The PDF is processed to extract and chunk the text, which is then stored in a vector store. Users can query the processed PDF content, and the application returns relevant answers.

This setup allows users to interact with a PDF document through natural language queries, using the Gemini model for responses.
