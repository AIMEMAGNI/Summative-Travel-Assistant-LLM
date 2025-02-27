# Travel Assistant Chatbot

This project implements a travel assistant chatbot that uses the T5 model to generate responses to travel-related queries. The model has been fine-tuned on a dataset designed for training travel-related chatbots, and the interface is built using Gradio, allowing users to interact with the chatbot in real-time.

## Features
- **Preprocessing**: The input text is normalized to improve the model's response generation accuracy.
- **Model**: A T5-small model fine-tuned on the Bitext Travel Dataset.
- **Fine-tuning**: The model has been fine-tuned for better performance with a learning rate adjustment.
- **Gradio Interface**: The chatbot can be accessed through a web interface where users can enter their queries and receive responses from the model.

## Setup and Installation

To run this project locally, follow these steps:

### 1. Clone the repository:
```bash
git clone https://github.com/AIMEMAGNI/Summative-Travel-Assistant-LLM.git
cd your-repository-directory
```

### 2. Download and process the dataset:
The dataset is automatically loaded using `load_dataset("bitext/Bitext-travel-llm-chatbot-training-dataset")`. Make sure you have internet access to download the dataset.

### 3. Training the model:
The model is trained using the `T5-small` model from Hugging Face. The training uses the `Trainer` API and is optimized for memory efficiency, which makes it suitable for environments like Google Colab.

### 4. Running the Gradio interface:
Once the model is trained, you can run the Gradio interface with the following Python script:
```python
import gradio as gr

def generate_response(query):
    """Generate chatbot response for a given query."""
    return test_query(query)  # Use the test_query function defined earlier

iface = gr.Interface(
    fn=generate_response,
    inputs=gr.Textbox(label="Enter your query", placeholder="Ask something...", lines=2),
    outputs=gr.Textbox(label="Response"),
    title="Travel Assistant Chatbot",
    description="This is a chatbot that helps with travel-related queries. Ask anything!",
    theme="default"
)

iface.launch()
```

This will launch a Gradio web interface where you can chat with the assistant.

## Training Results
- **Initial Loss**: 0.63
- **Tuned Loss**: 0.36

These results indicate that the fine-tuning process improved the model's ability to generate relevant responses.

## Contributing
Feel free to open an issue or submit a pull request if you'd like to contribute to the project.


