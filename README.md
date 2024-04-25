Slack PDF Bot
The Slack PDF Bot is a powerful tool that enhances your Slack workspace by providing intelligent question answering capabilities based on PDF documents. Users can upload PDF files to a Slack channel, and the bot will parse the contents, store them in a vector database, and use an OpenAI language model to generate accurate and relevant answers to user queries.
Features

Listens for PDF file uploads in Slack channels
Downloads and parses the uploaded PDF files
Stores the parsed page contents in a FAISS vector database for efficient similarity search
Accepts user queries in the format ['question1', 'question2', ...]
Retrieves the most relevant pages from the PDF based on the user query
Generates answers to the questions using the OpenAI language model
Provides the answers in a structured JSON format within the Slack channel

Requirements

Python 3.6+
Slack bot token and signing secret
OpenAI API key

