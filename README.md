# Content Creation Assistant using LangChain and OpenAI

A Python-based content creation tool that leverages the power of LangChain and OpenAI to automatically generate engaging TikTok video scripts. This project demonstrates how to combine modern AI technologies to streamline the content creation process for social media platforms.

## Project Overview

This project creates an AI-powered assistant that can generate creative, engaging scripts for 1-minute TikTok videos on any given topic. The assistant uses OpenAI's language model through the LangChain framework to ensure consistent, high-quality content generation.

## Features

- Generates complete TikTok video scripts with shot descriptions and dialogue
- Customizable prompt template for different content styles
- Easy-to-use function interface for content generation
- Supports various topics and themes
- Includes shot descriptions for visual guidance
- Produces engaging, social media-optimized content

## Technical Requirements

The project requires the following Python libraries:
```python
pandas
numpy
matplotlib
seaborn
langchain
openai
```

## Setup and Installation

1. Clone this repository to your local machine
2. Install the required dependencies:
```bash
pip install pandas numpy matplotlib seaborn langchain openai
```
3. Set up your OpenAI API key:
   - Create an account at OpenAI and obtain your API key
   - Set your API key as an environment variable:
```python
os.environ['OPENAI_API_KEY'] = "your-api-key-here"
```

## Usage

The core functionality is wrapped in a simple function called `create_tiktok_post`. Here's how to use it:

```python
# Initialize the prompt template
prompt_template = PromptTemplate(
    input_variables = ["topic"],
    template = "Create a short, engaging script for a 1 minute TikTok post about {topic}."
)

# Create the LangChain instance
lm = OpenAI()
llm_chain = LLMChain(prompt = prompt_template, llm = lm)

# Define the content creation function
def create_tiktok_post(topic):
    response = llm_chain.run(topic)
    return response

# Generate content
topic = "your topic here"
response = create_tiktok_post(topic)
print(response)
```

## Example Outputs

The assistant can generate scripts for various topics, such as:
- Making money with ChatGPT
- Traveling to NYC
- Climate change awareness
- Photography tips
- Personal events and experiences

Each script includes:
- Shot-by-shot descriptions
- Dialogue and voiceover text
- Scene transitions
- Visual elements and camera directions

## Project Structure

```
├── .env                  # Environment variables (create this file)
├── README.md            # Project documentation
└── content_creator.py   # Main script with content creation logic
```

## Best Practices

1. Always ensure your OpenAI API key is stored securely and never committed to version control
2. Consider implementing rate limiting for API calls
3. Add error handling for API responses
4. Test generated content for appropriateness before use
5. Review and edit generated scripts for brand consistency

## Future Improvements

Potential enhancements for the project:
- Add support for different content formats (Instagram, YouTube, etc.)
- Implement content moderation
- Add template customization options
- Include automatic hashtag generation
- Integrate with social media posting APIs

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- OpenAI for providing the language model API
- LangChain for the framework
- The open-source community for inspiration and support
