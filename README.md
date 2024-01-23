# JorneAI-with-OpenAI

This project implements a chat interface using langchain, OpenAI API, and Gradio, featuring a personalized travel companion named JorneAI.

## Table of Contents
1. [Installation](#installation)
2. [Usage](#usage)
3. [Setting Up OpenAI API Key](#setting-up-openai-api-key)
4. [Running the Chat Interface](#running-the-chat-interface)
5. [Interface Usage](#interface-usage)
6. [Components](#components)
   - [Prompt Template](#prompt-template)
   - [Language Model Chain](#language-model-chain)
   - [Gradio Chat Interface](#gradio-chat-interface)
   - [Tuning Input Details](#Tuning-Input-Details)
7. [Functionality](#functionality)
8. [Examples](#examples)
9. [Conclusion](#conclusion)

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
The chat interface allows users to interact with the language model. Example queries can be provided, and the assistant, named JorneAI, will respond accordingly.## Components
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
## Tuning Input Details
You can tune the input details by modifying the keywords list in the get_text_response function. The keywords are used to identify if a user message is related to travel. Add or remove keywords based on your preferences.

## Functionality
The main functionality is encapsulated in the get_text_response function, which takes a user message and chat history as input and generates a response using the language model chain.
## Examples
Example queries for the Gradio Chat Interface include:
```
"Tell me about travel destinations"
"Tell me about some tourist places"
"How can you help with travel?"
"What are the accommodation options?"
"How much does transportation cost?"
"Tell me about trip charges."
```
## Conclusion
This documentation provides an overview of the JorneAI Chat Interface, including installation instructions, usage guidelines, and an explanation of key components.
