# 🔎 langchain-multiagent-chatbot

A powerful Streamlit-based chatbot that combines the capabilities of LangChain with multiple search tools to provide comprehensive answers from various sources including arXiv papers, Wikipedia articles, and general web search.

## Features

- **Multi-Source Search**: Integrates arXiv, Wikipedia, and DuckDuckGo search capabilities
- **Real-time Streaming**: Uses Groq's Llama3 model with streaming responses
- **Interactive UI**: Built with Streamlit for a clean, user-friendly interface
- **Agent-Based Architecture**: Utilizes LangChain's ZERO_SHOT_REACT_DESCRIPTION agent
- **Conversation History**: Maintains chat history throughout the session
- **Transparent Processing**: Shows agent thoughts and actions in real-time

## Prerequisites

- Python 3.8 or higher
- Groq API key (get one from [Groq Console](https://console.groq.com/))

## Installation

1. **Clone the repository** (or save the code to a file):
```bash
git clone <[your-repo-url](https://github.com/Muhammad-Yousaf09/langchain-multiagent-chatbot)>
cd langchain-search-chatbot
```

2. **Install required packages**:
```bash
pip install streamlit langchain-groq langchain-community python-dotenv
```

3. **Set up environment variables** (optional):
Create a `.env` file in the project root:
```
GROQ_API_KEY=your_groq_api_key_here
```

## Usage

1. **Run the application**:
```bash
streamlit run app.py
```

2. **Enter your Groq API key** in the sidebar (if not set in environment variables)

3. **Start chatting!** Ask questions like:
   - "What is machine learning?"
   - "Find recent papers on quantum computing"
   - "Tell me about the history of artificial intelligence"
   - "What are the latest developments in renewable energy?"

## How It Works

The chatbot uses a **LangChain agent** that can intelligently choose between three different tools:

- **🔬 arXiv Search**: Searches academic papers and research publications
- **📚 Wikipedia Search**: Queries Wikipedia for encyclopedic information
- **🌐 DuckDuckGo Search**: Performs general web searches for current information

The agent uses a **ZERO_SHOT_REACT_DESCRIPTION** approach, meaning it:
1. **Reasons** about which tool to use based on the question
2. **Acts** by calling the appropriate search tool
3. **Observes** the results and decides if more information is needed
4. **Responds** with a comprehensive answer

## Configuration

### Search Tools Configuration

- **arXiv**: Returns top 1 result with max 200 characters
- **Wikipedia**: Returns top 1 result with max 200 characters
- **DuckDuckGo**: General web search with standard results

### Model Settings

- **Model**: Llama3-8b-8192 via Groq
- **Streaming**: Enabled for real-time responses
- **Error Handling**: Parsing errors are handled gracefully

## File Structure

```
langchain-search-chatbot/
├── app.py                 # Main application file
├── requirements.txt       # Python dependencies
├── .env                  # Environment variables (optional)
└── README.md             # This file
```

## Dependencies

```txt
streamlit
langchain-groq
langchain-community
python-dotenv
```

## Troubleshooting

### Common Issues

1. **API Key Error**: Make sure your Groq API key is valid and entered correctly
2. **Module Import Error**: Ensure all required packages are installed
3. **Search Tool Timeout**: Some searches may take time; the app will show progress
4. **Rate Limiting**: Groq API has rate limits; wait a moment if you hit them

### Debug Tips

- Check the Streamlit callback handler output to see agent reasoning
- Verify your API key has proper permissions
- Ensure you have a stable internet connection for search tools

## Contributing

Feel free to contribute by:
- Adding new search tools
- Improving the UI/UX
- Enhancing error handling
- Adding more language model options

## License

This project is open source and available under the MIT License.

## Acknowledgments

- **LangChain** for the agent framework
- **Streamlit** for the web interface
- **Groq** for the language model API
- **arXiv, Wikipedia, DuckDuckGo** for search capabilities

---

**Note**: This application requires an active internet connection and a valid Groq API key to function properly.
