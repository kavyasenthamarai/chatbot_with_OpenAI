# chatbot_with_OpenAI

This project implements a chat interface using langchain, OpenAI API, and Gradio, allowing users to interact with the GPT-3.5 language model in real-time.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
  - [Setting Up OpenAI API Key](#setting-up-openai-api-key)
  - [Running the Chat Interface](#running-the-chat-interface)
  - [Interface Usage](#interface-usage)
- [Components](#components)
  - [Prompt Template](#prompt-template)
  - [Language Model Chain](#language-model-chain)
  - [Gradio Chat Interface](#gradio-chat-interface)
- [Functionality](#functionality)
- [Examples](#examples)
- [Conclusion](#conclusion)

## Installation

Make sure to install the required dependencies by running the following commands:

```bash
!pip install langchain
!pip install openai
!pip install gradio
!pip install huggingface_hub
```
## Setting Up OpenAI API Key
Before running the script, set your OpenAI API key as an environment variable:
```

OPENAI_API_KEY="___"
os.environ["OPENAI_API_KEY"] = OPENAI_API_KEY
```
## Running the Chat Interface
Run the main script to launch the Gradio Chat Interface:
## Interface Usage
The chat interface allows users to interact with the language model. Example queries can be provided, and the assistant will respond accordingly.
## Components
## Prompt Template
The script uses a template for generating responses, defined as follows:

```
template = """You are a helpful assistant to answer user queries.
{chat_history}
User: {user_message}
Chatbot:"""
```
## Language Model Chain
The language model chain is set up using the LLMChain class, incorporating the ChatOpenAI model from langchain. The temperature is set to '0.5' for controlled responses.
```
llm_chain = LLMChain(
    llm=ChatOpenAI(temperature='0.5', model_name="gpt-3.5-turbo"),
    prompt=prompt,
    verbose=True,
    memory=memory,
```
## Gradio Chat Interface
Gradio is used to create an interactive chat interface. Users can input queries, and the model responds in real-time.
```
demo = gr.ChatInterface(get_text_response)
```
## Functionality
The main functionality is encapsulated in the get_text_response function, which takes a user message and chat history as input and generates a response using the language model chain.

## Examples
Example queries for the Gradio Chat Interface include:
```
"How are you doing?"
"What are your interests?"
"Which places do you like to visit?"
```
## Conclusion
This documentation provides an overview of the Chat Interface, including installation instructions, usage guidelines, and an explanation of key components.
