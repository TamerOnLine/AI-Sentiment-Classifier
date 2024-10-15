
# Sentiment Analysis System Using LangChain and Ollama

## Overview
This project implements a **Sentiment Analysis System** using the LangChain framework and Ollama models. The system classifies text inputs such as product reviews or social media posts into **positive**, **negative**, or **neutral** sentiments. It leverages a pre-trained Ollama model for text embedding and sentiment classification, integrated into a flexible LangChain pipeline.

## Features
- **Sentiment Classification**: Classifies input text into positive, negative, or neutral categories.
- **Ollama Integration**: Uses Ollama's pre-trained `llama3.2` model for efficient sentiment analysis.
- **LangChain**: The LangChain framework manages the sentiment analysis workflow.
  
## Requirements

- Python 3.8 or higher
- The following Python packages are required:
  
  ```bash
  pip install langchain ollama
  ```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/sentiment-analysis-langchain-ollama.git
   cd sentiment-analysis-langchain-ollama
   ```

2. Install the necessary dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure that you have access to the pre-trained Ollama model (`llama3.2`).

## How to Use

1. **Input**: Provide a list of text inputs (e.g., reviews, comments) that you wish to analyze for sentiment.

2. **Run the analysis**: Execute the script `main.py` to analyze the sentiment of your input text:

   ```bash
   python main.py
   ```

3. **Sample Output**:
   The system will output the sentiment for each input text:

   ```
   Text: "The product was amazing and easy to use."
   Sentiment: Positive

   Text: "The experience was terrible. I do not recommend this."
   Sentiment: Negative

   Text: "The product is okay but could be improved."
   Sentiment: Neutral
   ```

## Project Structure

```bash
├── main.py               # Main script for running sentiment analysis
├── README.md             # This README file
├── requirements.txt      # Python dependencies
└── sentiment_analysis.py # Contains the LangChain and Ollama implementation
```

## Example Code

Here’s a simplified code snippet showing how to integrate LangChain with Ollama for sentiment analysis:

```python
from langchain import PromptTemplate, LLMChain
from langchain.llms import Ollama

# Prompt for sentiment analysis
prompt_template = PromptTemplate(
    input_variables=["text"],
    template="Analyze the sentiment of the following text and classify it as positive, negative, or neutral:

{text}"
)

# Ollama model
llm = Ollama(model="llama3.2")

# LangChain setup
llm_chain = LLMChain(llm=llm, prompt=prompt_template)

# Sample input
texts = ["The product was fantastic!", "I had a bad experience.", "The service was decent."]

# Process and output results
for text in texts:
    result = llm_chain.run(text)
    print(f"Text: {text}
Sentiment: {result}
")
```

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing
Feel free to submit issues or pull requests. Contributions are welcome!

## Contact
For any questions or feedback, reach out at [info@tameronline.com](mailto:info@tameronline.com).
