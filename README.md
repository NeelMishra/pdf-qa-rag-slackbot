# Slack PDF Bot

The Slack PDF Bot is an RAG powered PDF question answer slack bot. Users can upload PDF files to a Slack channel, and the bot will parse the contents, store them in a vector database, and use an OpenAI language model to generate accurate and relevant answers to user queries.

## Features

- Listens for PDF file uploads in Slack channels
- Downloads and parses the uploaded PDF files
- Stores the parsed page contents in a FAISS vector database for efficient similarity search
- Accepts user queries in the format `['question1', 'question2', ...]`
- Retrieves the most relevant pages from the PDF based on the user query
- Generates answers to the questions using the OpenAI language model
- Provides the answers in a structured JSON format within the Slack channel

## Requirements

- Python 3.6+
- Slack bot token and signing secret
- OpenAI API key

## Installation

1. Clone the repository:

   ```
   git clone https://github.com/your-username/slack-pdf-bot.git
   ```

2. Navigate to the project directory:

   ```
   cd slack-pdf-bot
   ```

3. Install the required dependencies:

   ```
   pip install -r requirements.txt
   ```

4. Set up the environment variables:

   - Create a `.env` file in the project root directory.
   - Add the following lines to the `.env` file, replacing the placeholders with your actual values:

     ```
     SLACK_TOKEN=your-slack-bot-token
     SIGNING_SECRET=your-slack-signing-secret
     OPENAI_KEY=your-openai-api-key
     ```

5. Run the bot:

   ```
   python app.py
   ```

## Usage

1. Invite the Slack PDF Bot to the desired Slack channel(s).

2. Upload a PDF file to the channel where the bot is present.

3. The bot will acknowledge the PDF upload and start processing the file.

4. Once the PDF is parsed and stored in the vector database, the bot will confirm that it's ready to accept user queries.

5. To ask a question, send a message in the format `['question1', 'question2', ...]` followed by attaching your pdf in the Slack channel.

6. The bot will retrieve the most relevant pages from the PDF, generate answers using the OpenAI language model, and provide the answers in a structured JSON format within the Slack channel.

## Code Structure

- `app.py`: The main application file that sets up the Slack bot, handles events, and integrates the PDF parsing and question answering functionalities.
- `pdf_parser.py`: Contains functions for parsing PDF files, storing page contents in a FAISS vector database, and searching for similar pages based on a query.
- `llm_caller.py`: Handles the interaction with the OpenAI API to generate answers to questions based on the provided context.
- `.env`: Environment file to store the Slack bot token, signing secret, and OpenAI API key.

## To-Do

- [ ] Implement support for multiple PDF files and allow users to specify which file to query.
- [ ] Add error handling and user-friendly error messages for common issues.
- [ ] Enhance the PDF parsing functionality to handle complex layouts and extract images. Potentially Videos?
- [ ] Explore optimizations for the vector database to improve search performance.
- [ ] Implement a feedback mechanism for users to provide feedback on the generated answers.
- [ ] Integrate with other Slack features, such as slash commands and interactive messages.
- [ ] Explore options for deploying the bot to a production environment (e.g., using Docker, serverless functions).
- [ ] Provide support for other LLMs, including finetuned ones.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.
