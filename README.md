# LangGraph Integration with ChatGroq and Custom Tools

This project demonstrates the integration of LangGraph with ChatGroq for creating AI-powered workflows that interact with external APIs, such as fetching search results, generating charts, and performing other complex tasks. The system utilizes a multi-agent architecture where each agent handles specific tasks and can communicate with others to achieve the final goal.

## Features

- **Multi-agent Workflow**: The system is based on LangGraph's stateful graphs that control the flow between different agents and tools.
- **Custom Tools**: A Python REPL tool and a Tavily search tool are included to allow dynamic task handling, such as executing code and fetching search results.
- **Memory Integration**: Memory-saving features are implemented to store the state of the conversation across steps.
- **Routing Logic**: A flexible routing mechanism ensures that tasks are passed to the correct agents based on their capabilities and progress.
- **Graph Visualization**: The workflow graph can be visualized using Mermaid diagrams, helping you understand how tasks flow through the system.

## Installation

To get started with the project, follow these steps:

### Step 1: Clone the repository


git clone https://github.com/yourusername/your-repository.git
cd your-repository


###Step 2: Install dependencies
Install the necessary Python packages with:

pip install -r requirements.txt



###Step 3: Set up environment variables
Create a .env file in the root of the project and set up your API keys as follows:

GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key
GROQ_API_KEY=your_groq_api_key
LANGCHAIN_API_KEY=your_langchain_api_key
These keys are required to interact with the Google, Tavily, Groq, and LangChain APIs.

###Step 4: Run the application
Once the dependencies are installed and environment variables are set, you can run the application using:

python app.py
Architecture
Workflow
The system is designed with multiple agents that collaborate to fulfill user queries. The flow is controlled using a stateful graph, with nodes representing different tasks. Agents work together to:

Fetch relevant data from the web (via Tavily search).

Execute Python code (via a Python REPL).

Generate final results (such as charts or answers) based on the processed data.

Nodes and Agents
Researcher Agent: Handles search queries using the TavilySearchResults tool.

Chart Generator Agent: Handles Python code execution to generate charts or process data.

Tool Node: Invokes external tools such as Python REPL or search tools based on the current workflow.

Routing Logic
The routing logic ensures that tasks are passed correctly between agents. For example, the Researcher Agent fetches the data, then passes the data to the Chart Generator Agent for further processing.
