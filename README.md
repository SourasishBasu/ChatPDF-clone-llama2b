# ChatPDF Clone
> Chatbot app for interactively conversing with documents

# Introduction

With the emergence of services like ChatGPT, showcasing the power of LLMs and RAG in generating contextually relevant responses, I was motivated to understand their underlying mechanics. It led to me working on this chatbot which not only converses intelligently but also interacts seamlessly with PDF documents.

# Technical Overview

We utilize LlamaIndex, enhanced with the Llama2 model API using Gradient's LLM solution, seamlessly merge it with DataStax's Apache Cassandra as a vector database and develop the frontend UI with Streamlit using Python.

![image](https://github.com/SourasishBasu/ChatPDF-clone-llama2b/assets/89185962/89c8505f-4c5a-429c-bade-03e4fdc7f7d2)
<p align="center"><strong>Architecture Diagram</strong></p>

### LlamaIndex
Serves as a powerful framework for handling embeddings, efficient document indexing and retrieval. 

![image](https://github.com/SourasishBasu/ChatPDF-clone-llama2b/assets/89185962/e6588ecf-f1ec-49ab-b354-11f23a76ea08)

![image](https://github.com/SourasishBasu/ChatPDF-clone-llama2b/assets/89185962/be5095a7-4b4c-409c-861d-1a6c33092ddd)
<p align="center"><strong>Retriever Engine</strong></p>

### GradientAI's LLM
By tapping into Gradient's LLM solution, we leverage state-of-the-art open source language models such as Meta's LLAMA 2 model specifically `llama-2b-chat`, allowing the chatbot to generate coherent and informed responses. 

### Cassandra Vector Store
Integrates Apache Cassandra as a vector database, offering a solution for storing and managing vector embeddings of the provided documents which facilitates efficient retrieval and storage of document-related information.

### Streamlit
Simplifies the creation and deployment of web applications, providing a user friendly interface to initiate conversations with chatbot, explore document-related insights, and experience immersive interactions with PDFs in a visually appealing manner.

# Prerequisites

- Python 3.9 or above
- **GradientAI Account**:
  - Create an account on GradientAI to access the LLMs required for training and deploying models.
  - Create a new workspace & generate and store your `Access token` and `Workspace ID` credentials as secrets/environment variables.

- **AstraDB Account**
  - Set up an account on AstraDB, a cloud-native database service built on Apache Cassandra and create a Vector Database.
  - Under Connect generate an App Token as `Database Administrator` and save the `app-token.json` and the `Secure-Connect-Bundle.zip`.

  ![image](https://github.com/SourasishBasu/ChatPDF-clone-llama2b/assets/89185962/50570a51-fade-485d-b747-f8ba308f16e7)

# Setup

To set up ChatPDF Clone, follow these steps:

1. **Clone the Repository**: Clone the ChatPDF Clone repository to your local machine.
   ```bash
   git clone https://github.com/your-username/ChatPDF-Clone.git
   ```

2. **Install Dependencies**: Navigate to the project directory and install the necessary dependencies.
   ```bash
   cd ChatPDF-Clone
   pip install -r requirements.txt
   ```

3. **Configure Credentials**: Add the GradientAI credentials as environment variables to your project environment. Copy the `Secure-Connect-Bundle.zip` and `app-token.json` into the project root directory.

## Open in Google Colab

Click to open the Notebook directly in Google Colab. Configure the access tokens under the Secrets section and upload PDFs into the Documents folder.

<p><a href="https://colab.research.google.com/github/SourasishBasu/ChatPDF-clone-llama2b/blob/main/ChatPDF_Clone.ipynb" target="_blank"><img height="30" src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a></p>

# Usage

Once the setup is complete, you can use ChatPDF Clone for interactive conversations. Run the script as follows and navigate to the locahost URL generated to access the webapp:

```bash
streamlit run main.py
```

In the following examples, I provided the PDF for a [summary of Merchant of Venice](https://pennstatelaw.psu.edu/_file/TheMerchantofVeniceSummary.pdf) to the service.

### Screenshots

![image](https://github.com/SourasishBasu/ChatPDF-clone-llama2b/assets/89185962/503c9af3-3f25-4b49-9a78-e4fb90444a85)

![image](https://github.com/SourasishBasu/ChatPDF-clone-llama2b/assets/89185962/3c632afd-a807-408b-80c5-1fe815d4a41e)

![image](https://github.com/SourasishBasu/ChatPDF-clone-llama2b/assets/89185962/526195de-ca55-4289-9c72-694ba6e6c2b5)


## Challenges

During the development of ChatPDF Clone, we encountered several challenges, including:

- **Integration Complexity**: Integrating GradientAI and AstraDB posed challenges in terms of authentication and data synchronization.
- **Retrieval Performance**: Retrieval Accuracy and Speed was severely affected with increase in document quantity.
- **Handling Dynamic Conversations**: Adapting the chatbot to handle dynamic and evolving conversations while maintaining coherence presented a challenge.
