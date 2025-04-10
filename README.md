# Renesas Applications Chatbot

This repository contains a comprehensive notebook that demonstrates how to build an intelligent chatbot for Renesas applications. The chatbot is designed to answer questions related to Renesas's applications across multiple domains including automotive, consumer electronics, industrial, and communications infrastructure. It leverages web scraping, document embedding, and large language models (LLMs) to extract, store, and interactively retrieve relevant information.

---

## Table of Contents

- [Objective](#objective)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Workflow](#workflow)
  - [Web Scraping](#web-scraping)
  - [Document Embedding and Storage](#document-embedding-and-storage)
  - [Chatbot Implementation](#chatbot-implementation)
  - [Gradio Interface](#gradio-interface)
- [Usage](#usage)
- [Contact](#contact)

---

## Objective

The notebook aims to build a chatbot that can answer questions about Renesas's applications, focusing on:
- **Automotive**
- **Consumer Electronics**
- **Industrial**
- **Communications Infrastructure**

It combines web scraping, document embedding, and LLMs to build a robust and interactive question-answering system. Interactive diagrams and images from the Renesas website are processed and analyzed to enrich the responses provided by the chatbot.

---

## Features

- **Web Scraping:**  
  Scrapes specific application data from the Renesas website using:
  - `cloudscraper`
  - `requests_html`
  - `BeautifulSoup`
  
  Extracts section titles, descriptions, application categories, and interactive diagrams; converts SVG diagrams to PNG images; and stores the data in a structured JSON format.

- **Document Embedding and Storage:**  
  - Converts scraped data into LangChain documents.
  - Uses `HuggingFaceEmbeddings` to embed the documents.
  - Stores embedded documents in a Chroma vector store for efficient retrieval.

- **Chatbot Implementation:**  
  - Utilizes ChatOpenAI (GPT models) for question-answering.
  - Creates a RetrievalQA chain with the Chroma vector store to retrieve relevant context.
  - Maintains conversation history for contextualized responses.
  - Integrates OpenAI’s Vision model for diagram component analysis and description.

- **Gradio Interface:**  
  - Builds a user-friendly Gradio interface for interacting with the chatbot.
  - Allows users to input questions and receive responses.
  - Supports image uploads and displays interactive diagrams.
  - Enables image analysis triggered by specific user prompts.

---

## Technology Stack

- **Web Scraping:**  
  `cloudscraper`, `requests_html`, `BeautifulSoup`
- **Large Language Models:**  
  ChatOpenAI (GPT-3.5-turbo, GPT-4)
- **Document Embedding:**  
  `HuggingFaceEmbeddings`
- **Vector Store:**  
  Chroma
- **User Interface:**  
  Gradio
- **Image Processing:**  
  `cairosvg`, `PIL`
- **Others:**  
  `langchain`, `asyncio`, `nest_asyncio`

---

## Workflow

### Web Scraping

1. **Scrape Renesas Website:**  
   Uses `cloudscraper`, `requests_html`, and `BeautifulSoup` to extract data from Renesas's website.  
   - Focuses on specific application categories.
   - Extracts section titles, descriptions, application details, and interactive diagrams.
   
2. **Data Storage:**  
   - Stores structured data as JSON.
   - Saves SVG diagrams as PNG images.

### Document Embedding and Storage

1. **Convert to Documents:**  
   Transforms scraped data into LangChain documents.

2. **Generate Embeddings:**  
   Creates embeddings using `HuggingFaceEmbeddings`.

3. **Store in Chroma:**  
   Embedded documents are saved in a Chroma vector store for efficient retrieval.

### Chatbot Implementation

1. **LLM Initialization:**  
   Utilizes ChatOpenAI (GPT models) for natural language processing.

2. **RetrievalQA Chain:**  
   Combines the Chroma vector store with a retrieval-based QA chain to fetch relevant context and generate accurate answers.

3. **Conversational Chain:**  
   Maintains chat history to ensure responses are context-aware.

4. **Diagram Analysis:**  
   Integrates OpenAI’s Vision model to analyze and describe components in the scraped diagrams.

### Gradio Interface

1. **User Interface:**  
   Implements a Gradio-powered chatbot interface where users can:
   - Input questions.
   - Receive answers.
   - Upload images for further analysis.
   
2. **Interactive Diagrams:**  
   Displays interactive diagrams and images as part of the answer generation process.

---

## Usage

1. **Clone the Repository:**
   
   ```bash
   git clone https://github.com/yourusername/renesas-applications-chatbot.git
   cd renesas-applications-chatbot
   
2. **Install Dependencies:**
   
   ```bash
   pip install -r requirements.txt

2. **Run the Notebook:**

   Open the Jupyter or Colab notebook (`Capstone_2.ipynb`) and run the cells sequentially to build the complete pipeline.

3. **Launch the Chatbot:**

   The notebook will start a Gradio interface where you can interact with the chatbot by asking questions and uploading images as needed.

---

Contact
-------

For questions or contributions, please contact nkarvindkumar@gmail.com.
